# micropython-ESP32-SOLO-1
micropython ESP32 SOLO-1
micropython ESP32 SOLO-1 firmware binary
E (469) cpu_start: Running on single core chip, but application is built with dual core support.
E (478) cpu_start: Please enable CONFIG_FREERTOS_UNICORE option in menuconfig.
microPython Enable dual core support by default.
Single core is still supported, just by adding CONFIG_FREERTOS_UNICORE=y to
a custom sdkconfig file.

for ESP32 SOLO-1 you may do this.

modify file ports/esp32/boards/sdkconfig.base and add:

# FreeRTOS
CONFIG_FREERTOS_UNICORE=y

it should be ok to run in unicore mode on a dual core.
or Download this binary file.

build-GENERIC.zip
https://www.strongd.net/dl/build-GENERIC.zip

#esptool.py -p {PORT} -b 460800 --before default_reset --after hard_reset --chip esp32 write_flash --flash_mode dio --flash_size detect --flash_freq 40m 0x1000 build-GENERIC/bootloader/bootloader.bin 0x8000 build-GENERIC/partition_table/partition-table.bin 0x10000 build-GENERIC/micropython.bin
