# CYD-NAS web installer

Installs CYD-NAS (a small microSD file server with a web file manager) on an ESP32-2432S028R (CYD,
micro-USB, ILI9341) from a browser over USB: computers with Chrome or Edge (Web Serial), Android
phones with Chrome and an OTG cable (WebUSB, small CH340 driver).

firmware/boot.bin goes to 0x0 and firmware/app.bin to 0xe000, so the settings (NVS 0x9000-0xDFFF:
WiFi, web login, touch calibration) are kept; "erase" wipes the whole chip first. Files on the
microSD card are never touched by the installer. Installs go through this page only (no one-file image), so each one is counted.

Uses esptool-js 0.6.1 (Apache-2.0), vendored in mobile/esptool-js/ with its licence.
The firmware's screen font is Sarabun (SIL OFL 1.1). Made by tee & claude.
