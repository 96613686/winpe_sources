# DloadGetSRWLockFunctionPointers(void)

- ea: `0x18000ae10`
- end: `0x18000aeae`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ab0c`
- `0x18000ad4c`
- `0x180187af8`

## callees

- `0x18000ae10`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ae54`
- `KERNEL32!GetProcAddress` at `0x18000ae70`
- `KERNEL32!GetProcAddress` at `0x18000ae54`
- `KERNEL32!GetProcAddress` at `0x18000ae70`
- `KERNEL32!GetModuleHandleW` at `0x18000ae37`
- `KERNEL32!GetModuleHandleW` at `0x18000ae37`

## string_xrefs

- `0x18000ae30`: `KERNEL32.DLL`

## pseudocode

```c

```
