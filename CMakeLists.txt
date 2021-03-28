cmake_minimum_required(VERSION 3.9)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "")

message(STATUS "Magnum include dir: ${Magnum_DIR}")

project(magnumSandbox VERSION 1.0.0)
set(Magnum_DIR "${PROJECT_SOURCE_DIR}/dependencies/Magnum/modules")
set(Corrade_DIR "${PROJECT_SOURCE_DIR}/dependencies/corrade/modules")

add_subdirectory("dependencies/corrade")
add_subdirectory("dependencies/Magnum")

include_directories("dependencies/Magnum/src")
include_directories("dependencies/corrade/src")


find_package(Magnum REQUIRED)
find_package(Corrade REQUIRED)

add_executable(magnumSandbox src/main.cpp)