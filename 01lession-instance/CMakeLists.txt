cmake_minimum_required(VERSION 3.12)
project(vulkanLearning-1)

set(CMAKE_CXX_STANDARD 17)

aux_source_directory(. DIRSRCS)

include_directories(
SYSTEM ${CMAKE_CURRENT_SOURCE_DIR}/../../glm/glm/
SYSTEM ${CMAKE_CURRENT_SOURCE_DIR}/../../glfw-3.3.8.bin.WIN64/include
SYSTEM ${CMAKE_CURRENT_SOURCE_DIR}/../../VulkanSDK/1.3.250.1/Include
)

link_directories(
SYSTEM ${CMAKE_CURRENT_SOURCE_DIR}/../../glfw-3.3.8.bin.WIN64/lib-mingw-w64
SYSTEM ${CMAKE_CURRENT_SOURCE_DIR}/../../VulkanSDK/1.3.250.1/Lib
)

add_subdirectory(vulkanWrapper)

add_executable(vulkanLearning-1  ${DIRSRCS})

target_link_libraries(vulkanLearning-1 vulkanLib vulkan-1.lib glfw3.lib)