# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180014858`
- end: `0x1800148a9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800139e8`
- `0x180015020`

## callees

- `0x180014858`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014892`
- `KERNEL32!GetProcAddress` at `0x180014892`
- `KERNEL32!GetModuleHandleW` at `0x18001487a`
- `KERNEL32!GetModuleHandleW` at `0x18001487a`

## string_xrefs

- `0x180014871`: `kernelbase.dll`

## pseudocode

```c

```
