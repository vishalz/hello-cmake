cmake_minimum_required(VERSION 3.16)
project(vtest)
set(CMAKE_CXX_STANDARD 14)
add_library(vmath complex.cpp)

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
)

FetchContent_MakeAvailable(googletest)
enable_testing()


add_executable(vtest test.cpp )
target_link_libraries(vtest gtest_main vmath)

