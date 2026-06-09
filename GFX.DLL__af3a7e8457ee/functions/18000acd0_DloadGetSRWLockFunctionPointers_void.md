# DloadGetSRWLockFunctionPointers(void)

- ea: `0x18000acd0`
- end: `0x18000ad6e`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `158`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a9cc`
- `0x18000ac0c`
- `0x180183f68`

## callees

- `0x18000acd0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ad14`
- `KERNEL32!GetProcAddress` at `0x18000ad30`
- `KERNEL32!GetProcAddress` at `0x18000ad14`
- `KERNEL32!GetProcAddress` at `0x18000ad30`
- `KERNEL32!GetModuleHandleW` at `0x18000acf7`
- `KERNEL32!GetModuleHandleW` at `0x18000acf7`

## string_xrefs

- `0x18000acf0`: `KERNEL32.DLL`

## pseudocode

```c

```
