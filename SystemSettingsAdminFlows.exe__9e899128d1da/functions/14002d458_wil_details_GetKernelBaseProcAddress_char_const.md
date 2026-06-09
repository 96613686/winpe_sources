# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14002d458`
- end: `0x14002d4a9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14002e4d0`
- `0x14002f8e8`

## callees

- `0x14002d458`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d47a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d47a`
- `KERNEL32!GetProcAddress` at `0x14002d492`
- `KERNEL32!GetProcAddress` at `0x14002d492`

## string_xrefs

- `0x14002d471`: `kernelbase.dll`

## pseudocode

```c

```
