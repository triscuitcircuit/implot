cmake_minimum_required(VERSION 3.19)

project(implot)


find_package(OpenGL REQUIRED)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include_directories("external/imgui")
add_subdirectory(external/imgui)


add_library(implot STATIC
        implot.h
        implot.cpp

        implot_demo.cpp
        implot_internal.h

)

target_link_libraries(implot PUBLIC
        OpenGL::GL
        imgui
)
