# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1801142ec`
- end: `0x18011433d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180112da0`
- `0x180114570`

## callees

- `0x1801142ec`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18011430e`
- `KERNEL32!GetModuleHandleW` at `0x18011430e`
- `KERNEL32!GetProcAddress` at `0x180114326`
- `KERNEL32!GetProcAddress` at `0x180114326`

## string_xrefs

- `0x180114305`: `kernelbase.dll`

## pseudocode

```c

```
