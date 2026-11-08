[README](../README.md) · [Install](install.md) · [Using the menu](menu.md) · **Beginner (RTX 20)** · [Game compatibility](compatibility.md) · [Troubleshooting](troubleshooting.md)

# Beginner guide (RTX 2060 and friends)

You only need a few controls. The in-game menu defaults to **Simple** detail so
the rest stays out of the way. Switch **Menu → Detail** to **Full** any time.

## What to turn on

| Goal | What to do |
| --- | --- |
| Unlock Multi Frame Generation | Install the DLL, open the menu with **Backspace**, pick **2x** or **3x** |
| Show Frame Generation in a game that hid it | Tick **Game FG option: Unlock**, restart the game, then enable Frame Generation in the game |
| DLSS 5 Neural Rendering | Put `nvngx_dlssnr.dll` beside the game, open the **DLSS 5** tab, set **Hook Method** to **Auto** and **Look** to **Balanced** |

## Install (short)

1. Download `MFGUnlocker` from
   [Releases](https://github.com/dashdogy/MFG-Unlocker/releases) and extract it.
2. Rename `MFGUnlocker.dll` to the name your game loads early, usually
   `version.dll` or `winmm.dll`. See [Game compatibility](compatibility.md).
3. Put that file beside the **real game .exe**, not the launcher.
4. Launch the game and press **Backspace**.

Do not install this in games with [anti-cheat](compatibility.md#games-with-anti-cheat).

## Frame Generation on an RTX 2060

1. If the game has **no Frame Generation setting**, tick **Game FG option:
   Unlock** in the menu and **restart** the game once.
2. In the game's graphics settings, turn **Frame Generation / DLSS Frame
   Generation** **On**.
3. In MFG Unlocker's menu, set **Mode** / **MFG mode** to **2x FG** or **3x
   MFG**. Start low; higher multipliers need more GPU headroom on Turing.
4. Leave **Detail** on **Simple** unless you need presets, V-Sync, XeMFG or
   diagnostics.

**Follow game** keeps whatever multiplier the game asked for. You usually want
a fixed **2x** or **3x** instead.

## DLSS 5 Neural Rendering (NR)

MFG Unlocker does **not** ship NVIDIA's DLSS 5 dll. You need an
`nvngx_dlssnr.dll` that **supports your GPU** (including RTX 20). Place it
beside the game executable (or beside MFG Unlocker). The **DLSS 5** tab appears
when that dll is found.

Recommended Simple settings:

- **Hook Method:** Auto
- **Look:** Balanced
- **Half rate:** on if the GPU cost is too high (about half the cost)

If Status says the GPU or provider is unsupported, that dll build does not
support your card; you need a different `nvngx_dlssnr.dll`.

## Recommended starting point (RTX 2060)

```text
Menu Detail          Simple
Game FG option       Unlock  (only if the game hid Frame Generation)
Mode / MFG mode      2x FG or 3x MFG
DLSS 5 Hook Method   Auto
DLSS 5 Look          Balanced
DLSS 5 Half rate     On if FPS drops too much
```

## If something fails

- No menu: wrong DLL name or folder — see [Install](install.md) and
  [Troubleshooting](troubleshooting.md).
- No Frame Generation option: Unlock + restart, above.
- No DLSS 5 tab: missing or unsupported `nvngx_dlssnr.dll`.
- Need every control again: set **Menu → Detail** to **Full**.
