cmake_minimum_required(VERSION 3.10)
project(simple_checker LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS NO)

find_package(LLVM REQUIRED CONFIG)

add_library(simple_checker SHARED
	SimpleChecker.cpp
)

target_link_libraries(simple_checker PRIVATE
	LLVM
)

target_include_directories(simple_checker PRIVATE
	${LLVM_INCLUDE_DIRS})

