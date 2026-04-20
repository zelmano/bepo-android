# zBépo — Android Physical Keyboard Layout

An Android application that registers a custom physical keyboard layout, making zBépo available as a system-level input option for external Bluetooth and USB keyboards.

zBépo is a personal variant of the [bépo](https://bepo.fr) layout, optimized for both French text entry and programming. Digits are accessible directly (no Shift required), and common programming symbols are placed on the Shift layer of the number row.

## Requirements

- Android 4.1 or later
- An external keyboard (Bluetooth or USB)

## Installation

Download the latest APK from the [Releases](https://github.com/zelmano/bepo-android/releases) page and install it via sideloading. The app has no interface — it registers the layout with the Android input system silently upon installation.

## Enabling the Layout

1. Connect your external keyboard.
2. Go to **Settings → General management → Language and input → Physical keyboard**.
3. Select your keyboard from the list.
4. Choose **French (zBépo)**.

> Path may vary slightly depending on Android version and device manufacturer.

## Layout Overview

The layout source is maintained in [`zbepo.toml`](https://github.com/zelmano/zbepo) using the [Kalamine](https://github.com/OneDeadKey/kalamine) keyboard layout descriptor format.

**Number row** — digits on base, symbols on Shift:

| Key | Base | Shift | AltGr | Shift+AltGr |
|-----|------|-------|-------|-------------|
| `` ` `` | — | `#` | | |
| `1` | `1` | `$` | | `◌̄` dead macron |
| `2` | `2` | | | `◌́` dead acute |
| `3` | `3` | | | `◌̌` dead caron |
| `4` | `4` | `` ` `` | | `◌̀` dead grave |
| `6` | `6` | `@` | | |
| `7` | `7` | `+` | | |
| `8` | `8` | `-` | | |
| `9` | `9` | `/` | | |
| `0` | `0` | `*` | `°` | |
| `-` | `-` | `=` | | |
| `=` | `=` | `%` | | |

**Space bar:**

| Combo | Output |
|-------|--------|
| Space | space |
| Shift+Space | `-` hyphen |
| AltGr+Space | `_` underscore |
| Shift+AltGr+Space | non-breaking space |

## Building from Source

The project uses Gradle. A debug APK can be built without a signing keystore:

```sh
./gradlew assembleDebug
```

CI builds are handled automatically via GitHub Actions on each push to `main`.

## License

MIT — based on [bepo-android](https://github.com/anisse/bepo-android) by Anisse Astier.
