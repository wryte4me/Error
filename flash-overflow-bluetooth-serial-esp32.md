https://community.platformio.org/t/greater-than-maximum-allowed-1310720-bytes-ram-18-1-used-59404-bytes-from-327680-bytes-checkprogsize-explicit-exit-status-1-flash-103-0/32008/5

```ini
[env:esp-wrover-kit]
platform = espressif32
board = esp-wrover-kit
framework = arduino
lib_deps = GitHub - gilmaimon/ArduinoWebsockets: A library for writing modern websockets applications with Arduino (ESP8266 and ESP32) 25

build_flags =
-DBOARD_HAS_PSRAM
-mfix-esp32-psram-cache-issue
-DCONFIG_MBEDTLS_DYNAMIC_BUFFER=1
-DCONFIG_BT_ALLOCATION_FROM_SPIRAM_FIRST=1
-DCONFIG_SPIRAM_CACHE_WORKAROUND=1

board_build.partitions = huge_app.csv
;no_ota.csv
extra_scripts = pre:build_script_versioning.py

monitor_speed = 115200
upload_port = COM5

```
