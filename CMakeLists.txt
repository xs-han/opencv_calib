cmake_minimum_required(VERSION 2.8)

project(VirtualView)
# The version number.
set (TESTS_VERSION_MAJOR 1)
set (TESTS_VERSION_MINOR 0)

find_package(OpenCV 3.2.0 REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})


# VirtualView Compilation
aux_source_directory(${PROJECT_SOURCE_DIR}/src calib_src)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)
add_executable(calibration ${calib_src})
target_link_libraries(calibration ${OpenCV_LIBS})
