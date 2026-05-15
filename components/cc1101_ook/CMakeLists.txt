set(srcs cc1101.cc)
set(platform_srcs "") 
include("${CMAKE_CURRENT_LIST_DIR}/../../source_filter.cmake" OPTIONAL)

idf_component_register(
    SRCS ${srcs} 
    INCLUDE_DIRS "./include" 
  #  REQUIRES utils_misc utils_debug
    PRIV_REQUIRES utils_misc freertos 
                  esp_driver_spi esp_driver_gpio #PRIV_ESP_IDF
     )

component_compile_options(${comp_compile_opts})
component_compile_features(${comp_compile_feats})
