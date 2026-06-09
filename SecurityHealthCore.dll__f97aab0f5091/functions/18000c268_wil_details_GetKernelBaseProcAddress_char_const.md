# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000c268`
- end: `0x18000c2b9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000baf8`
- `0x18000c7a0`

## callees

- `0x18000c268`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c2a2`
- `KERNEL32!GetProcAddress` at `0x18000c2a2`
- `KERNEL32!GetModuleHandleW` at `0x18000c28a`
- `KERNEL32!GetModuleHandleW` at `0x18000c28a`

## string_xrefs

- `0x18000c281`: `kernelbase.dll`

## pseudocode

```c

```
