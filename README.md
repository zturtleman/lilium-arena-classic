<img src="https://raw.githubusercontent.com/clover-moe/lilium-arena/master/misc/lilium.png" width="64">

**Lilium Arena Classic** is an engine compatible with Quake 3 1.16n and versions back to Quake 3 Demo Test 1.09. It supports Quake 3 protocol 43 (.dm3 demo files) and the older QVM Mod APIs.


## Features

### ZTM's Flexible Display

Lilium Arena defaults to displaying the game as 4:3 letterbox with console/notify text at the same relative size as 640x480 resolution for an authentic Quake 3 experience on modern displays in high resolution.

Lilium Arena includes ZTM's Flexible Display; the successor to _ZTM's Flexible HUD mod for ioq3_. Flexible Display offers aspect correct widescreen but with various new enhancements, including support for mods and joining pure servers.

There are six widescreen presentation modes (controlled by `cl_flexibleDisplay` cvar):

1. Original 4:3 view/HUD (default).
2. Expanded view with 4:3 centered HUD.
3. Expanded view/HUD (not compatible with all mods, still under development).
4. Expanded view with stretched HUD.
5. Original stretched view/HUD.
6. Original widescreen view/HUD.

Expanded view respects `dmflags 16` (fixed fov) set by a server and switches to stretched view. There are `flexup` and `flexdown` commands that can be bound to conveniently switch modes while playing. You can optionally replace the original view `sizedown` / `sizeup` keys using `bind - flexdown; bind = flexup; bind + flexup;`.

Flexible Display is compatible with mods based on the original Q3 SDK and ioquake3 by running the mod logic at a fake 640x480 resolution and applying widescreen adjustments in the engine to match the window's resolution. `cl_flexibleDisplay 0` disables Flexible Display to access the mod's original resolution dependent behavior. Flexible Display can also be disabled at compile time if one wants to create a derivative project without this feature.

Additional enhancements in Flexible Display:

- Fixed player model being stretched in setup menu in widescreen when using the original pk3 files / ui.qvm.
- Fixed notify message position for Team Arena voice head in top-left in widescreen when using the original Team Arena pk3 files / cgame.qvm.
- Support for absolute mouse movement in the menu to make mouse movement sensitivity match desktop movement and move to the location touched on a touch screen. (Various iOS and Android ports have shipped a custom ui.qvm to add this, lacking support in mods.)
- Support for the mouse cursor leaving the window while in the menu.
- Support for resizing the window without reloading the game content (opengl1 renderer only).
- The console background and loading level image are aspect correct in "expanded view/HUD" mode; great for mods that add a logo to the console or level images.

General enhancements (usable independent of Flexible Display):

- Console text defaults to scaling to match 640x480 size; this can be overridden using `con_native 1; con_scale 2` to draw at native font resolution like the original Quake 3 with a custom scale factor to make it readable in 4K.
- The game window defaults to resizable.

All the changes for Flexible Display can be disabled by opening the console using Shift+Escape and pasting the following using Ctrl+V and pressing enter:

```
cl_flexibleDisplay 0; con_native 1; r_allowResize 0; vid_restart;
```

and re-enabled using:

```
cl_flexibleDisplay 1; con_native 0; r_allowResize 1; vid_restart;
```


## About

Credit for Quake 3 protocol 43 goes to Thilo Schulz (for ioEF) and Zack Middleton.

Currently QVM float rounding is only correct on x86/x86_64 so it's not ready for Arm, PowerPC, etc.

Lilium Arena Classic is based on [Lilium Arena](https://github.com/clover-moe/lilium-arena).
Lilium Arena Classic code commits: [compare/lilium-arena...master](https://github.com/clover-moe/lilium-arena-classic/compare/lilium-arena...master)

The source code for the Quake 3 1.16n game, cgame, and ui code is not included as it remains under a non-free license.


## License

Lilium Arena Classic is licensed under [the GNU GPLv2](COPYING.txt) (or at your option, any later version). The Quake 3 data files are not under a free license and must be purchased in order to play Quake 3.


## Resources

  * [Website](https://clover.moe/lilium-arena-classic)
  * [Discussion / Technical support](https://clover.moe/open-source)


## Compiling

Lilium Arena Classic is compiled using GNU Make (`make`) and requires a C compiler. Most dependencies are included in the repository. Compiling for Linux requires installing SDL 2 library and headers.


## Contributing

High quality code contributions are more helpful than rushed contributions. LLM ("AI") contributions are not desired.

Reviewing pull requests is sometimes more work than a reviewer doing the work in the first place so pull requests may be disregarded.


## Credits

Lilium Arena Classic is maintained by Clover.moe at https://github.com/clover-moe/lilium-arena-classic.

### id Software

  * John Carmack
  * Robert A. Duffy
  * Jim Dose'
  * Jan Paul van Waveren

### ioquake3 contributors

  * Tim Angus
  * James Canete
  * Vincent Cojot
  * Ryan C. Gordon
  * Aaron Gyes
  * Zack Middleton
  * Ludwig Nussel
  * Julian Priestley
  * Scirocco Six
  * Thilo Schulz
  * Jack Slater
  * Tony J. White
  * ...and many, many others!

### ioEF

  * Thilo Schulz

### Clover.moe

  * Zack Middleton (zturtleman)


## Derivatives

If you create a derivative project that you plan for others to use, it would be preferred to give it a different title such as "Lilium Arena (_your name_ ver.)" to make it easier to discuss and reduce confusion with the project maintained by Clover.moe.

If you're going to pick a different title, it would be preferred that you pick a different song title to build on rather than use the word Lilium. (Lilium is the title of the opening song of the 2004 anime series Elfen Lied.)


