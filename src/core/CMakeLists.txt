set(c_options "")
if(MSVC)
  list(APPEND c_options "/wd5030;/wd4251")
endif()

Ubpa_AddTarget(
  MODE STATIC
  RET_TARGET_NAME tname
  SOURCE
    "${PROJECT_SOURCE_DIR}/include/UDRefl"
  INC
    "${PROJECT_SOURCE_DIR}/include"
  C_OPTION
    ${c_options}
  LIB
    Ubpa::UContainer_core
    Ubpa::UTemplate_core
)

target_precompile_headers(${tname} PRIVATE "${PROJECT_SOURCE_DIR}/include/UDRefl/UDRefl.h")