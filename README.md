# IKEA TRADFRI 5-button remote – Color presets (ZHA)

A Home Assistant blueprint for the round IKEA TRADFRI 5-button remote
(E1524 / E1810) connected through ZHA.

[![Open your Home Assistant instance and show the blueprint import dialog with this blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fwhud%2Fha-ikea-tradfri-remote-blueprint%2Fblob%2Fmain%2Fblueprints%2Fautomation%2Fwhud%2Fzha_ikea_tradfri_5button_remote_presets.yaml)

## Buttons

| Button   | Short press                  | Long press                        |
| -------- | ---------------------------- | --------------------------------- |
| Power    | Toggle the light             | Full brightness, normal white     |
| Dim-Up   | Increase brightness          | Keep increasing until released    |
| Dim-Down | Decrease brightness          | Keep decreasing until released    |
| Right    | Next color preset (1–5)      | Rainbow fade until released       |
| Left     | Back to normal (warm white)  | Back to normal (warm white)       |

## Settings

- **Remote** and **Light**: which remote controls which light (or light group).
- **Color presets**: five color pickers. The right button steps through them in order.
- **Normal light**: color temperature and brightness for the left button ("undo whatever the kids did").
- **Advanced → Speed**: fade time and how fast held buttons repeat (default 500 ms).

## How the color cycling works

Blueprint automations can't remember anything between runs, so the right button
looks at the light's current color, finds the closest preset, and moves on to
the next one. If the light is off or showing white, it starts at color 1. Pick
five colors that look clearly different from each other.

## Requirements

- Home Assistant 2024.10 or newer
- The remote paired with ZHA

## Credits

Based on
[zha_ikea_tradfri_5button_remote_color](https://github.com/niro1987/homeassistant-config/blob/main/blueprints/automation/niro1987/zha_ikea_tradfri_5button_remote_color.yaml)
by [niro1987](https://github.com/niro1987), MIT License.
