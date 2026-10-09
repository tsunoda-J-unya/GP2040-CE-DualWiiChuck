# GP2040 Configuration for Cytron Maker Nano RP2040 (Dual Wii Nunchuk)

Two Wii Nunchuks, one on each Maker Port. Each port is wired to its own I2C block, so both Nunchuks can use address `0x52` without conflict. Ports are bound by I2C block, not by detection order, so they never swap after a reboot or re-plug.

| Maker Port | GPIO (SDA/SCL) | I2C block | Wii port | Default mapping |
|---|---|---|---|---|
| Port 0 | GPIO0 / GPIO1 | I2C0 | Port 1 | Stick → Left analog, C → S2 (Start), Z → S1 (Select) |
| Port 1 | GPIO26 / GPIO27 | I2C1 | Port 2 | Stick → Right analog, C → B2, Z → B1 |

All mappings can be changed in the web configurator under **Add-ons → Wii Extension → Port 1 / Port 2**. The defaults only apply to a fresh configuration.

- Unplugged ports are re-probed every second, so a Nunchuk can be connected after boot.
- With two ports active, they poll on alternating milliseconds (about 500 Hz each).
- Accelerometer data (PS3, PS4, PS5 General and SInput modes only) comes from Port 1. Port 2 is used only when Port 1 is not reporting motion.
- The on-board user button (GPIO20) is mapped to S2. Hold it while plugging in to open the web configurator.

## Button pins

| GPIO | Action | GPIO | Action |
|---|---|---|---|
| 2 | Up | 13 | B4 |
| 3 | Down | 14 | R1 |
| 4 | Right | 15 | L1 |
| 5 | Left | 16 | S1 |
| 6 | B1 | 17 | S2 |
| 7 | B2 | 18 | L3 |
| 8 | R2 | 19 | R3 |
| 9 | L2 | 28 | A1 |
| 12 | B3 | 29 | A2 |
