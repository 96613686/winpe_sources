# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180043cf0`
- end: `0x180043d4e`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180043ad0`

## callees

- `0x180043cf0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180043d30`
- `KERNEL32!GetProcAddress` at `0x180043d30`
- `KERNEL32!GetModuleHandleW` at `0x180043d12`
- `KERNEL32!GetModuleHandleW` at `0x180043d12`

## string_xrefs

- `0x180043d09`: `kernelbase.dll`

## pseudocode

```c

```
