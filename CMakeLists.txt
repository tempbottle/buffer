cmake_minimum_required(VERSION 2.8)
project(buffer)

if( ${CMAKE_GENERATOR} MATCHES "Visual" )
    add_compile_options( -W3 -EHsc )
else()
    add_compile_options( -Wall -Wno-missing-braces -std=c++11 )
endif()

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

file(GLOB SOURCES "src/*.cpp")
include_directories("src")
add_library(buffer ${SOURCES})
