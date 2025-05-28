cmake_minimum_required(VERSION 4.0)
project(rnew LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


if(UNIX)
set(SHELL_CMD bash)
set(SEP ":")
set(STATIC_LIB_EXT a)
else()
set(SHELL_CMD pwsh)  #powershell 7
#set(SHELL_CMD powershell) #default for windows 
set(EXT ".exe")
set(SEP ";")
set(STATIC_LIB_EXT lib)
endif()

file(GLOB PROJECT_SOURCES "src/main.cpp" "src/*/*.cpp")

add_executable(rnew ${PROJECT_SOURCES})
