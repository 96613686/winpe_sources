# SdbpGetShimPluginDirectory

- ea: `0x18004842c`
- end: `0x1800484b9`
- name: `SdbpGetShimPluginDirectory`
- size: `141`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800212c4`
- `0x1800363b8`

## callees

- `0x18004842c`
- `0x1800484c0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004847a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004847a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004846c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004846c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180048450`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180048450`

## string_xrefs

- `0x18004843f`: `kernel32.dll`

## pseudocode

```c

```
