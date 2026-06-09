# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003e110`
- end: `0x18003e16e`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003df10`

## callees

- `0x18003e110`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003e150`
- `KERNEL32!GetProcAddress` at `0x18003e150`
- `KERNEL32!GetModuleHandleW` at `0x18003e132`
- `KERNEL32!GetModuleHandleW` at `0x18003e132`

## string_xrefs

- `0x18003e129`: `kernelbase.dll`

## pseudocode

```c

```
