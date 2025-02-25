# arduino-ethernet-ota

## Description

This examples showcases the usage of Over-The-Air (OTA) updates with the WIZnet W5500-EVB-Pico (and similiar Wiznet Ethernet) board.

For more details, see the documentation:
* https://github.com/maxgerhardt/platform-raspberrypi/blob/develop/examples/arduino-ota
* https://arduino-pico.readthedocs.io/en/latest/platformio.html
* https://arduino-pico.readthedocs.io/en/latest/ota.html

## Usage

For the initial firmware update, use the wiznet_5500_evb_pico_via_usb environment.

Then, open the serial monitor and note down the IP of the board that it outputs.

Use this IP as the upload_port in the wiznet_5500_evb_pico_via_ota environment and use the "Upload" project task there.

## Expected serial output

For the "Upload + Monitor " task in the `wiznet_5500_evb_pico_via_usb` environment:

```
--- Terminal on COM7 | 9600 8-N-1
--- Available filters and text transformations: colorize, debug, default, direct, hexlify, log2file, nocontrol, printable, send_on_enter, time
--- More details at https://bit.ly/pio-monitor-filters
--- Quit: Ctrl+C | Menu: Ctrl+T | Help: Ctrl+T followed by Ctrl+H
Booting
Waiting for Ethernet link..
Waiting for Ethernet link..
Waiting for Ethernet link..
Waiting for DHCP address..
Waiting for DHCP address..
Waiting for DHCP address..
Waiting for DHCP address..
Ethernet Ready!
IP address: 192.168.0.208
```
(IP can of course change).

For the "Upload" task in the `wiznet_5500_evb_pico_via_ota` environment:

```
Configuring upload protocol...
AVAILABLE: blackmagic, cmsis-dap, espota, jlink, picoprobe, picotool, raspberrypi-swd
CURRENT: upload_protocol = espota
Uploading .pio\build\wiznet_5500_evb_pico_via_ota\firmware.bin
20:32:12 [DEBUG]: Options: {'esp_ip': '192.168.0.208', 'host_ip': '0.0.0.0', 'esp_port': 2040, 'host_port': 35311, 'auth': '', 'image': '.pio\\build\\wiznet_5500_evb_pico_via_ota\\firmware.bin', 'spiffs': False, 'debug': True, 'progress': True}
20:32:12 [INFO]: Starting on 0.0.0.0:35311
20:32:12 [INFO]: Upload size: 189500
20:32:12 [INFO]: Sending invitation to: 192.168.0.208
20:32:12 [INFO]: Waiting for device...

Uploading: [                                                            ] 0% 
Uploading: [                                                            ] 0%
Uploading: [=                                                           ] 1% 
[..]
Uploading: [=========================================================== ] 97%
Uploading: [=========================================================== ] 98% 
Uploading: [============================================================] 99% 
Uploading: [============================================================] 100% Done...


20:32:15 [INFO]: Waiting for result...
20:32:16 [INFO]: Result: OK
Complete
================================ [SUCCESS] Took 9.52 seconds ======================================
Environment                   Status    Duration
----------------------------  --------  ------------
wiznet_5500_evb_pico_via_ota  SUCCESS   00:00:09.516
```