# qt5-minimalistic-builds
This is attempt to build Qt 5 libraries in minimalistic mode. Output binaries have fewer dependencies, are lighter and thus are smaller.

**You can get x64 variant of Qt5 library (MSVC and MinGW) on the original repo — [here](https://github.com/martinrotter/qt5-minimalistic-builds).**

**This is fork for x86 (MSVC).**

All original licenses of all used components (Qt, qtbinpatcher, OpenSSL, MSVC) are respected with the additional exception that compiling, linking, and/or using OpenSSL is allowed. Unmodified source code of Qt is used and the license of produced Qt binaries is the same as license used in original OSS Qt libraries.  The build phase of these prebuilt binaries is reproducible, see repository files for build scripts.

Used OpenSSL is taken from [here](https://www.npcglib.org/~stathis/blog/precompiled-openssl/).

You use this stuff on your own risk.

## How this differs from official Qt Windows binaries?
Well, there are some differences:

* these binaries are compiled with **MSVC2017** toolchain and are **x86**,
* **some features and modules are disabled**, which makes dependency tree smaller (details are specified in description of each release),
* distribution is relocatable (via `qtbinpatcher.exe`) and coinstallable with original MSYS2 Qt5 packages,
* debug/release builds are available,
* static/dynamic builds are available,
* allmost all 3rd-party libs used by Qt are compiled directly into libraries,
* link-time optimizations (`/LTCG`) are enabled in MSVC2017 static builds.

## How to use MSVC2017 variant
1. Install Visual Studio 2017 or just Build Tools.
1. Download [prebuilt Qt binaries](https://github.com/yalov/qt5-minimalistic-builds/releases) and unpack them to folder of your choice, for example `C:\Qt\XX`.
1. Use command line to navigate to folder `C:\Qt\XX\bin` and run `qtbinpatcher.exe` and wait for it to finish its job. At this point, installation is complete and Qt library is ready for usage.