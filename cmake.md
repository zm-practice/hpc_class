# CMake
一个跨平台的自动化构建系统，用于管理软件编译过程。通过生成标准构建文件(makefile,visual stdio项目等)，再由底层工具(make,ninja等)执行实际编译
- CMakeLists.txt
  项目的构建规则文件，通常放在项目根目录
```shell
cmake_minimum_required(VERSION 3.10) #最低cmake版本
project(MyProject) #项目名称

# 定义一个选项，用于控制是否启用调试模式
option(ENABLE_DEBUG "Enable debug mode" OFF)

# 根据选项的值，设置不同的编译选项
if(ENABLE_DEBUG)
    add_definitions(-DDEBUG)
    set(CMAKE_BUILD_TYPE Debug)
else()
    set(CMAKE_BUILD_TYPE Release)
endif()

# 添加可执行文件
add_executable(myapp main.cpp) #myapp是生成的可执行文件名称，main.cpp是编译所需的源代码文件（可以指定多个文件）
```