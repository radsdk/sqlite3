cmake_minimum_required(VERSION 3.10)

project(sqlite3 LANGUAGES C)

option(BUILD_SHELL "Build shell" OFF)

add_library(sqlite3
    sqlite3.h
    sqlite3.c
    sqlite3ext.h
)

if (${BUILD_SHELL})
add_executable(sqlite3-shell
    sqlite3.h
    sqlite3.c
    sqlite3ext.h
    shell.c
)
endif()
