# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800a94c8`
- end: `0x1800a9519`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800691b0`
- `0x1800c5030`

## callees

- `0x1800a94c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9502`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a94ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a94ea`

## string_xrefs

- `0x1800a94e1`: `kernelbase.dll`

## pseudocode

```c

```
