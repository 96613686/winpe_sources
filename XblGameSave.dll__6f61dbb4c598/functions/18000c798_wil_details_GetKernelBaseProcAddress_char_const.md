# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000c798`
- end: `0x18000c7e9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bfc8`
- `0x180026b70`

## callees

- `0x18000c798`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7ba`

## string_xrefs

- `0x18000c7b1`: `kernelbase.dll`

## pseudocode

```c

```
