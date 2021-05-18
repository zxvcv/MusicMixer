# Copyright (c) 2021 Paweł Piskorz
# Licensed under the Eclipse Public License 2.0
# See attached LICENSE file

cmake_minimum_required(VERSION 3.16.3)
project(MusicMixer VERSION 0.0.1)



#####################################   LANGUAGE AND STANDARD   ###################################
enable_language(CXX)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)



#####################################   LOCAL VARIABLES   #########################################
set(LOCAL_TARGET ${PROJECT_NAME})
set(DRIVERS_DIR Drivers)



#####################################   SEARCHING LIBRARIES #######################################
find_library(AQUILA_LIB Aquila "${DRIVERS_DIR}/aquila_build/lib")



#####################################   EXECUTABLE   ##############################################
add_executable(${LOCAL_TARGET}
    Source/main.cpp
)

target_include_directories(${LOCAL_TARGET} PUBLIC
    ${DRIVERS_DIR}/aquila_build/include
)

target_link_libraries(${LOCAL_TARGET}
    ${AQUILA_LIB}
)
