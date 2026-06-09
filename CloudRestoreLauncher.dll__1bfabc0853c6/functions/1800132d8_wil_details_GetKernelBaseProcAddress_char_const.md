# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800132d8`
- end: `0x180013329`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800129a8`
- `0x18001e210`

## callees

- `0x1800132d8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800132fa`
- `KERNEL32!GetModuleHandleW` at `0x1800132fa`
- `KERNEL32!GetProcAddress` at `0x180013312`
- `KERNEL32!GetProcAddress` at `0x180013312`

## string_xrefs

- `0x1800132f1`: `kernelbase.dll`

## pseudocode

```c

```
