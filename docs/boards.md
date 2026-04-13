# Board Comparison

The tables below are built from the repo's PlatformIO board metadata and variant build flags. `RAM` is the MCU's on-chip RAM where it is known from the MCU family. `PSRAM` is only shown when the repo declares it explicitly or enables it in board metadata. If the board enables PSRAM but the repo does not declare a size, it is marked as `Yes (size not declared)`.

## Quick Guidance

- Pick an `ESP32-S3` board with `16MB` flash and PSRAM if you want the most headroom for MQTT plus UI: `heltec_v4_tft`, `heltec_v4`, `Station_G2`, `T_Beam_S3_Supreme_SX1262`.
- Pick a TFT board if this will be used as a human-facing companion or field node: `heltec_v4_tft`, `heltec_tracker_v2`, `LilyGo_TDeck`, `Heltec_T190`.
- Pick e-paper if you want a status screen with lower idle draw and less frequent refresh: `Heltec_E213`, `Heltec_E290`, `Heltec_Wireless_Paper`, `ThinkNode_M5`.
- Pick a headless board if this is mainly a fixed MQTT gateway and screen space is not useful: `Xiao_C3`, `RAK_3112`, `Tenstar_C3`, `Heltec_ct62`, `Generic_E22`.
- Pick a GPS-capable board if location-aware/mobile use matters: the T-Beam family, `heltec_tracker_v2`, `Heltec_v3`, `heltec_v4`, `Station_G2`, `ThinkNode_M5`.
- If you want the most conservative, older radio family choices, the `SX1276` boards are `LilyGo_TLora_V2_1_1_6`, `Tbeam_SX1276`, and `Heltec_v2`.

## `repeater_mqtt` Boards

Rows with a trailing `_` in the env name are still included because they exist in `variants/eastmesh_mqtt/platformio.ini`, but they look more experimental than the main EastMesh targets listed in [local-builds.md](./local-builds.md).

| Env                                    | CPU               | RAM    | PSRAM                   | Flash | LoRa   | Display         | GPS | Web UI | Notes                                   |
| -------------------------------------- | ----------------- | ------ | ----------------------- | ----- | ------ | --------------- | --- | ------ | --------------------------------------- |
| T_Beam_S3_Supreme_SX1262_repeater_mqtt | ESP32S3 / 240 MHz | 512 KB | 8 MB                    | 8MB   | SX1262 | OLED (SH1106)   | Yes | Yes    | GPS, more memory headroom               |
| LilyGo_TLora_V2_1_1_6_repeater_mqtt    | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1276 | OLED (SSD1306)  | Yes | Yes    | GPS                                     |
| LilyGo_TBeam_1W_repeater_mqtt          | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 16MB  | SX1262 | OLED (SH1106)   | Yes | Yes    | GPS, more memory headroom               |
| Xiao_C3_repeater_mqtt                  | ESP32C3 / 160 MHz | 400 KB | No                      | 4 MB  | SX1262 | None            | Yes | No     | headless, GPS, web panel off            |
| Ebyte_EoRa-S3_Repeater_mqtt            | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 4MB   | SX1262 | OLED (SSD1306)  | No  | Yes    | more memory headroom                    |
| RAK_3112_repeater_mqtt                 | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | None            | Yes | Yes    | headless, GPS                           |
| Tbeam_SX1262_repeater_mqtt             | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1262 | OLED (SSD1306)  | Yes | Yes    | GPS                                     |
| Heltec_E290_repeater_mqtt              | ESP32S3 / 240 MHz | 512 KB | 8 MB                    | 16MB  | SX1262 | E-paper (2.9")  | No  | Yes    | low-power display, more memory headroom |
| Tbeam_SX1276_repeater_mqtt             | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1276 | OLED (SSD1306)  | Yes | Yes    | GPS                                     |
| Heltec_E213_repeater_mqtt              | ESP32S3 / 240 MHz | 512 KB | 8 MB                    | 16MB  | SX1262 | E-paper (2.13") | No  | Yes    | low-power display, more memory headroom |
| Heltec_Wireless_Tracker_repeater_mqtt  | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | TFT (ST7735)    | Yes | Yes    | richer UI, GPS                          |
| M5Stack_Unit_C6L_repeater_mqtt         | ESP32C6 / 160 MHz | 512 KB | No                      | 4 MB  | SX1262 | None            | Yes | Yes    | headless, GPS                           |
| LilyGo_TDeck_repeater_mqtt             | ESP32S3 / 240 MHz | 512 KB | No                      | 16MB  | SX1262 | TFT (ST7789)    | Yes | Yes    | richer UI, GPS                          |
| Station_G2_repeater_mqtt               | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 16MB  | SX1262 | OLED (SH1106)   | Yes | Yes    | GPS, more memory headroom               |
| Station_G2_logging_repeater_mqtt       | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 16MB  | SX1262 | OLED (SH1106)   | Yes | Yes    | GPS, more memory headroom               |
| LilyGo_T3S3_sx1262_repeater_mqtt       | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 4MB   | SX1262 | OLED (SSD1306)  | No  | Yes    | more memory headroom                    |
| Meshadventurer_sx1262_repeater_mqtt    | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1262 | OLED (SSD1306)  | Yes | Yes    | GPS                                     |
| Meshadventurer_sx1268_repeater_mqtt    | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1268 | OLED (SSD1306)  | Yes | Yes    | GPS                                     |
| Heltec_Wireless_Paper_repeater_mqtt    | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | E-paper (2.13") | No  | Yes    | low-power display                       |
| heltec_v4_repeater_mqtt                | ESP32S3 / 240 MHz | 512 KB | 2 MB                    | 16MB  | SX1262 | OLED (SSD1306)  | Yes | Yes    | GPS, more memory headroom               |
| heltec_v4_tft_repeater_mqtt            | ESP32S3 / 240 MHz | 512 KB | 2 MB                    | 16MB  | SX1262 | TFT (ST7789)    | Yes | Yes    | richer UI, GPS, more memory headroom    |
| heltec_tracker_v2_repeater_mqtt        | ESP32S3 / 240 MHz | 512 KB | No                      | 8MB   | SX1262 | TFT (ST7735)    | Yes | Yes    | richer UI, GPS                          |
| Heltec_v3_repeater_mqtt                | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | OLED (SSD1306)  | Yes | Yes    | GPS                                     |
| Heltec_WSL3_repeater_mqtt              | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | None            | Yes | Yes    | headless, GPS                           |
| LilyGo_T3S3_sx1276_repeater_mqtt       | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 4MB   | SX1276 | OLED (SSD1306)  | No  | Yes    | more memory headroom                    |
| LilyGo*Tlora_C6_repeater_mqtt*         | ESP32C6 / 160 MHz | 512 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| Xiao*C6_repeater_mqtt*                 | ESP32C6 / 160 MHz | 512 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| Meshimi*repeater_mqtt*                 | ESP32C6 / 160 MHz | 512 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| WHY2025*badge_repeater_mqtt*           | ESP32C6 / 160 MHz | 512 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| Heltec_v2_repeater_mqtt                | ESP32 / 240 MHz   | 520 KB | No                      | 8 MB  | SX1276 | OLED (SSD1306)  | No  | Yes    |                                         |
| nibble_screen_connect_repeater_mqtt    | ESP32S3 / 240 MHz | 512 KB | No                      | 4MB   | SX1262 | OLED (SSD1306)  | No  | Yes    |                                         |
| ThinkNode_M2_Repeater_mqtt             | ESP32S3 / 240 MHz | 512 KB | No                      | 4MB   | SX1262 | OLED (SH1106)   | No  | Yes    |                                         |
| ThinkNode_M5_Repeater_mqtt             | ESP32S3 / 240 MHz | 512 KB | No                      | 4MB   | SX1262 | E-paper (GxEPD) | Yes | Yes    | low-power display, GPS                  |
| Heltec*T190_repeater_mqtt*             | ESP32S3 / 240 MHz | 512 KB | 8 MB                    | 16MB  | SX1262 | TFT (ST7789)    | No  | Yes    | richer UI, more memory headroom         |
| Tenstar_C3_sx1262_repeater_mqtt        | ESP32C3 / 160 MHz | 400 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| Tenstar_C3_sx1268_repeater_mqtt        | ESP32C3 / 160 MHz | 400 KB | No                      | 4 MB  | SX1268 | None            | No  | Yes    | headless                                |
| Heltec_ct62_repeater_mqtt              | ESP32C3 / 160 MHz | 400 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| Xiao_S3_WIO_repeater_mqtt              | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | None            | Yes | Yes    | headless, GPS                           |
| Generic_E22_sx1262_repeater_mqtt       | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1262 | None            | No  | Yes    | headless                                |
| Generic_E22_sx1268_repeater_mqtt       | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1268 | None            | No  | Yes    | headless                                |

## `companion_radio_wifi` Boards With A Display

This table only includes Wi-Fi companion envs that actually have a display configured. Headless Wi-Fi companion envs such as `Xiao_C3_companion_radio_wifi` are intentionally excluded here.

| Env                                           | CPU               | RAM    | PSRAM                   | Flash | LoRa   | Display         | GPS | Notes                                |
| --------------------------------------------- | ----------------- | ------ | ----------------------- | ----- | ------ | --------------- | --- | ------------------------------------ |
| heltec_tracker_v2_companion_radio_wifi        | ESP32S3 / 240 MHz | 512 KB | No                      | 8MB   | SX1262 | TFT (ST7735)    | Yes | richer UI, GPS                       |
| Heltec_v2_companion_radio_wifi                | ESP32 / 240 MHz   | 520 KB | No                      | 8 MB  | SX1276 | OLED (SSD1306)  | No  |                                      |
| Heltec_v3_companion_radio_wifi                | ESP32S3 / 240 MHz | 512 KB | No                      | 8 MB  | SX1262 | OLED (SSD1306)  | Yes | GPS                                  |
| heltec_v4_companion_radio_wifi                | ESP32S3 / 240 MHz | 512 KB | 2 MB                    | 16MB  | SX1262 | OLED (SSD1306)  | Yes | GPS, more memory headroom            |
| heltec_v4_tft_companion_radio_wifi            | ESP32S3 / 240 MHz | 512 KB | 2 MB                    | 16MB  | SX1262 | TFT (ST7789)    | Yes | richer UI, GPS, more memory headroom |
| LilyGo_TBeam_1W_companion_radio_wifi          | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 16MB  | SX1262 | OLED (SH1106)   | Yes | GPS, more memory headroom            |
| LilyGo_TLora_V2_1_1_6_companion_radio_wifi    | ESP32 / 240 MHz   | 520 KB | No                      | 4 MB  | SX1276 | OLED (SSD1306)  | Yes | GPS                                  |
| nibble_screen_connect_companion_radio_wifi    | ESP32S3 / 240 MHz | 512 KB | No                      | 4MB   | SX1262 | OLED (SSD1306)  | No  |                                      |
| Station_G2_companion_radio_wifi               | ESP32S3 / 240 MHz | 512 KB | Yes (size not declared) | 16MB  | SX1262 | OLED (SH1106)   | Yes | GPS, more memory headroom            |
| T_Beam_S3_Supreme_SX1262_companion_radio_wifi | ESP32S3 / 240 MHz | 512 KB | 8 MB                    | 8MB   | SX1262 | OLED (SH1106)   | Yes | GPS, more memory headroom            |
| ThinkNode_M2_companion_radio_wifi             | ESP32S3 / 240 MHz | 512 KB | No                      | 4MB   | SX1262 | OLED (SH1106)   | No  |                                      |
| ThinkNode_M5_companion_radio_wifi             | ESP32S3 / 240 MHz | 512 KB | No                      | 4MB   | SX1262 | E-paper (GxEPD) | Yes | low-power display, GPS               |

## Practical Picks

- Best all-round MQTT repeater with screen and memory headroom: `heltec_v4_repeater_mqtt`, `heltec_v4_tft_repeater_mqtt`, `T_Beam_S3_Supreme_SX1262_repeater_mqtt`, `Station_G2_repeater_mqtt`.
- Best MQTT repeater if you want a simple headless install: `RAK_3112_repeater_mqtt`, `Tenstar_C3_sx1262_repeater_mqtt`, `Heltec_ct62_repeater_mqtt`, `Generic_E22_sx1262_repeater_mqtt`.
- Best low-power display MQTT builds: `Heltec_E213_repeater_mqtt`, `Heltec_E290_repeater_mqtt`, `Heltec_Wireless_Paper_repeater_mqtt`, `ThinkNode_M5_Repeater_mqtt`.
- Best companion choices if you want the richest local UI: `heltec_v4_tft_companion_radio_wifi` and `heltec_tracker_v2_companion_radio_wifi`.
- Best companion choices if you want maximum memory headroom: `T_Beam_S3_Supreme_SX1262_companion_radio_wifi`, `heltec_v4_companion_radio_wifi`, `heltec_v4_tft_companion_radio_wifi`, `Station_G2_companion_radio_wifi`.
- Best companion choices if you prefer OLED over TFT: `T_Beam_S3_Supreme_SX1262_companion_radio_wifi`, `heltec_v4_companion_radio_wifi`, `LilyGo_TBeam_1W_companion_radio_wifi`.
