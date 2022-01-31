#
# bzlib features written in Rust
#
# Copyright (C) 2022 Micah Snyder
#

# bzlib rust static library
add_rust_library(TARGET bzlib_rust WORKING_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}")
if (WIN32)
    target_link_libraries(bzlib_rust PUBLIC INTERFACE Userenv)
endif()

add_library(BZip2::bzlib_rust ALIAS bzlib_rust)
