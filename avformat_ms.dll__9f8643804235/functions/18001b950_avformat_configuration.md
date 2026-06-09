# avformat_configuration

- ea: `0x18001b950`
- end: `0x18001b958`
- name: `avformat_configuration`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## string_xrefs

- `0x18001b950`: `--toolchain=msvc --target-os=win32 --disable-programs --disable-d3d11va --disable-dxva2 --enable-shared --enable-cross-compile --extra-cflags='-guard:cf -Qspectre -Gy -Gw' --extra-ldflags='-PROFILE -GUARD:CF -DYNAMICBASE -OPT:ICF -OPT:REF' --arch=x86_64 --extra-ldflags=-CETCOMPAT --prefix=/c/__w/1/s/FFmpegInterop/ffmpeg/Build/x64 --extra-cflags='-DWINAPI_FAMILY=WINAPI_FAMILY_APP -D_WIN32_WINNT=0x0A00' --extra-ldflags='-APPCONTAINER WindowsApp.lib -NODEFAULTLIB:kernel32.lib -DEFAULTLIB:onecore.li`

## pseudocode

```c
const char *avformat_configuration()
{
  return "--toolchain=msvc --target-os=win32 --disable-programs --disable-d3d11va --disable-dxva2 --enable-shared --enabl"
         "e-cross-compile --extra-cflags='-guard:cf -Qspectre -Gy -Gw' --extra-ldflags='-PROFILE -GUARD:CF -DYNAMICBASE -"
         "OPT:ICF -OPT:REF' --arch=x86_64 --extra-ldflags=-CETCOMPAT --prefix=/c/__w/1/s/FFmpegInterop/ffmpeg/Build/x64 -"
         "-extra-cflags='-DWINAPI_FAMILY=WINAPI_FAMILY_APP -D_WIN32_WINNT=0x0A00' --extra-ldflags='-APPCONTAINER WindowsA"
         "pp.lib -NODEFAULTLIB:kernel32.lib -DEFAULTLIB:onecore.lib' --extra-cflags=-MT --extra-ldflags='-NODEFAULTLIB:li"
         "bucrt.lib -DEFAULTLIB:ucrt.lib' --disable-everything --enable-small --disable-avdevice --disable-avfilter --dis"
         "able-autodetect --disable-doc --disable-htmlpages --disable-manpages --disable-podpages --disable-txtpages --di"
         "sable-network --disable-error-resilience --disable-faan --enable-parser=vorbis --enable-decoder=vorbis --enable"
         "-decoder=theora --enable-parser=vp3 --enable-demuxer=ogg --enable-parser=flac --extra-cflags='@/c/__t/UndockedC"
         "ompilerWarnings/CompilerWarnings.EO.rsp' --extra-cflags='-analyze -analyze:log:includesuppressed -analyze:log:f"
         "ormat:sarif -analyze:plugin EspXEngine.dll -analyze:ruleset /c/__t/NativeCompilerStaticAnalysisRuleset/mandator"
         "y_to_fix.ruleset' --extra-cflags='-experimental:log /c/__w/1/s/FFmpegInterop/ffmpeg/Output/x64/'";
}

```

## disassembly

```asm
0x18001b950  lea     rax, aToolchainMsvcT; "--toolchain=msvc --target-os=win32 --di"...
0x18001b957  retn
```
