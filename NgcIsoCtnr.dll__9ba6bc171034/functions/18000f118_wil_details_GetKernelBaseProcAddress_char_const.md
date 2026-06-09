# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000f118`
- end: `0x18000f169`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e948`
- `0x18000f640`

## callees

- `0x18000f118`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f13a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f13a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f152`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f152`

## string_xrefs

- `0x18000f131`: `kernelbase.dll`

## pseudocode

```c

```
