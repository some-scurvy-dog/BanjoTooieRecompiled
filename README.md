# Banjo-Tooie Independent PC Recompilation

Disclaimer: This project is not affiliated with [BanjoRecomp](https://github.com/BanjoRecomp/BanjoRecomp) or the team that created the Banjo Kazooie Recompilation.

This is an independent alpha recompilation of Banjo-Tooie for PC using AI. It powered by
[RT64](https://github.com/rt64/rt64). The game and assets are not included. You
must provide your own supported copy of the game.

[View screenshots](SCREENSHOTS.md)

[YouTube channel](https://www.youtube.com/@some-scurvy-dog)

## Alpha status

Windows x64 alpha releases are available. There is no support for Linux/Mac at this time.

## Download and install

Download the Windows ZIP from the
[project's Releases page](https://github.com/some-scurvy-dog/BanjoTooieRecompiled/releases),
extract the entire ZIP to a folder, and keep its files together. Run
`TooieRecompiled.exe` from that folder. There is no installer.

## First launch

Use Windows x64 and a compatible graphics driver. The Microsoft Visual C++ x64
Redistributable may be needed; install it from
[Microsoft](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist).

On the launcher's **Play** page, choose **Choose ROM...**, select your supported
ROM, confirm the launcher says it is validated, then choose **Start Game**. The
launcher does not provide the game. It accepts only an NTSC-U 1.0 big-endian
`.z64` ROM with SHA-256:

```text
9ec37fba6890362eba86fb855697a9cff1519275531b172083a1a6a045483583
```

Other regions, byte orders and modified ROMs are unsupported. If validation
fails, check the hash and file format; changing the filename does not convert a
ROM. Do not share ROMs or extracted game assets. See the [player guide](docs/PLAYER_GUIDE.md)
for hash-checking, controls, saves and troubleshooting.

## Features

- Native Windows gameplay with a launcher and local ROM validation.
- Keyboard and controller input, remapping, and rumble on supported devices.
- Display, resolution, anti-aliasing, framing, audio and presentation options.
- Ordinary in-game saves, optional cheat controls and travel/progression tools.
- A separate Private Practice session with one durable save-state slot.
- F3 diagnostics and an F4 log marker for reporting problems.

The [release notes](docs/RELEASE_NOTES.md) describe tested behavior and
known limits.

## Saves and Private Practice

Ordinary play uses the game's normal progress saves. F5 requests an ordinary
save while the original in-game pause menu is open; it does not save an exact
position. **Start Private Practice...** opens a separate session that does not
write normal progress. In **Tools > Practice**, **Save State** and **Load State**
use one durable slot. States require the same build, ROM, gameplay settings and
render settings; updates may make an old state unusable. See the [player guide](docs/PLAYER_GUIDE.md)
before switching builds or using practice tools.

Saves, settings and logs are kept in `%LOCALAPPDATA%\BanjoTooieRecompiled`. A
profile from an earlier test build (`TooieRecomp-frontend`) is copied there on
first start and the original is left unchanged.

Turning off active cheat effects does not undo permanent progress such as moves,
egg types or opened routes. Read the save-backup advice in the player guide.

## Known limitations

Full-game completion and broad PC compatibility have not been established, and
minimum Windows and hardware requirements are unknown. Some settings and tools
remain experimental. Review the release notes before testing.

## Help and reporting

Use the [issue tracker](https://github.com/some-scurvy-dog/BanjoTooieRecompiled/issues)
to report a problem. Include the build version or executable hash, Windows/GPU
and driver, controller, settings, location, and concise steps to reproduce it.
F4 adds a marker to the logs; it does not take a screenshot. Review and redact
logs before sharing. Never attach a ROM, save file, generated game data, or
entire profile.

## AI disclosure

AI tools generated substantial portions of this project's code and assisted
with engineering and review. My role has been directing development, testing
the game, and verifying its behavior.

Some related projects prohibit AI-generated contributions. Their policies must
be respected when contributing upstream. This is an independent project; no
upstream endorsement is implied. See [Contributing](CONTRIBUTING.md).

## Credits, license and contributing

This project uses [N64Recomp](https://github.com/N64Recomp/N64Recomp) to
statically recompile N64 game code,
[N64ModernRuntime](https://github.com/N64Recomp/N64ModernRuntime) for runtime
services, and RT64 for rendering. It also uses
[Dear ImGui](https://github.com/ocornut/imgui) and other libraries listed in
[third-party notices](THIRD_PARTY_NOTICES.md). The Banjo-Tooie decompilation
provides symbols and reverse-engineering groundwork; see its
[project page](https://github.com/Mr-Wiseguy/banjo-tooie). These projects and
their contributors are credited for their work; this project is independent
and is not endorsed by them.

Project material that its authors can license is under
[GPL-3.0-only](LICENSE). Dependencies, game-derived material and assets retain
their own terms. No game ROM or extracted game assets are included. Read
[Contributing](CONTRIBUTING.md) before proposing changes.

## Build from source

The [Windows build guide](docs/WINDOWS.md) is for developers. It covers source
generation and the native Windows build; these development tools are not player
requirements. See [generation details](docs/CODEGEN.md) for how a user-provided
ROM is used locally, and [architecture](docs/ARCHITECTURE.md) for an overview.
