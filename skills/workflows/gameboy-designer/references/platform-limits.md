# Game Boy Color and GB Studio limits

Read this for the Platform fit and Content and scope sections. Where GB Studio sets a tighter
limit than the hardware, the GB Studio limit wins. When you are not sure of a GB Studio limit in
the installed version, say so and ask for it to be confirmed in the project.

## Hardware (Game Boy Color)

- Screen: 160x144 pixels, 20x18 tiles of 8x8. Text boxes take a lot of that space.
- Colour: 8 background palettes of 4 colours, 8 sprite palettes of 3 colours + transparent.
  Each 8x8 background tile uses one palette. Palettes can change at runtime, which makes night,
  glow, flashes and fades cheap.
- Sprites: 40 hardware sprites, at most 10 on one horizontal line (more flicker or vanish).
  GB Studio draws actors with 8x16 hardware sprites, so a 16x16 actor uses 2.
- Memory: 32 KB work RAM, 16 KB video RAM. ROM is banked; GB Studio builds MBC5 cartridges.
- CPU: about 8 MHz in double-speed mode. Many moving actors with heavy scripts slow down.
- Sound: 4 channels (2 pulse, 1 wave, 1 noise). Sound effects take a channel from the music.
- Save: battery-backed cartridge RAM, small. Plan the save data as a few variables.

## GB Studio

- Scene types: Top Down, Platformer, Adventure, Shoot 'em Up, Point and Click, Logo. One game can
  mix them, which suits multi-genre pitches.
- Backgrounds have a unique-tile limit (about 192 in most versions). Repeating tiles saves space.
- Each scene has limits on actors and triggers (about 20 actors and 30 triggers in recent
  versions). Crowds, bullets and big herds need careful design.
- Logic uses global variables, a fixed number of them. Systems with many items or creatures need
  a compact data plan.
- Sprites are whole sheets per actor. Mixing parts (a head from one sprite on another body) is
  not built in: plan separate sprites per variant, or few variants.
- Complex systems (procedural maps, physics, deep simulations) may need GBVM scripts or engine
  plugins. Flag these as high risk.

## Physical product

- Cartridge, shell, box and manual take a large share of each pledge. Show a price for each
  physical tier and leave a margin for shipping and pledge-manager fees.
- A colour game should still run, or show a clear "Game Boy Color only" screen, on an original
  Game Boy. Say which the pitch chooses.

## Technical references

- GB Studio documentation: https://www.gbstudio.dev/docs/
- GB Studio colour mode: https://www.gbstudio.dev/docs/settings#color-mode
- Pan Docs, the Game Boy hardware reference: https://gbdev.io/pandocs/
- Pan Docs, colour palettes: https://gbdev.io/pandocs/Palettes.html
- Pan Docs, sprites (OAM): https://gbdev.io/pandocs/OAM.html
- hUGETracker, the music tracker GB Studio uses: https://github.com/SuperDisk/hUGETracker
