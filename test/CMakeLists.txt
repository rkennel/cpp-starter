cmake_minimum_required(VERSION 3.23)
project(test)

set(CMAKE_CXX_STANDARD 20)

#Automatically Fetch Google Test
include(FetchContent)
FetchContent_Declare(
        googletest
        GIT_REPOSITORY https://github.com/google/googletest.git
        GIT_TAG release-1.12.1
)

FetchContent_MakeAvailable(googletest)
include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})

add_executable(runTests test1.cpp)
target_link_libraries(runTests gtest gtest_main)

include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})
