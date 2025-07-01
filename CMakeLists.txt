# This file is only used for basic testing/debugging.
# It is not actually needed for downstream use.
#

cmake_minimum_required(VERSION 3.10)
project(UseLatexMk VERSION 1.0 LANGUAGES NONE)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})
include(UseLatexMk)

if (PROJECT_IS_TOP_LEVEL)
  option(UseLatexMk_BUILD_TESTS "Is test should be build?" ON)

  if (UseLatexMk_BUILD_TESTS)
    install(CODE "message(\"This is only here, to trigger the existence of an installation target for the test project\")")
    add_subdirectory(test)
  endif()
endif(PROJECT_IS_TOP_LEVEL)
