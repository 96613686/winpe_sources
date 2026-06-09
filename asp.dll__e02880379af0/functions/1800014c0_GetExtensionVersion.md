# GetExtensionVersion

- ea: `0x1800014c0`
- end: `0x180001540`
- name: `GetExtensionVersion`
- size: `128`
- prototype: `BOOL __stdcall(HSE_VERSION_INFO *pVer)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800014c0`
- `0x180004a64`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180001500`
- `msvcrt!strcpy_s` at `0x180001500`
- `KERNEL32!GetModuleHandleExW` at `0x180001520`
- `KERNEL32!GetModuleHandleExW` at `0x180001520`
- `KERNEL32!SetLastError` at `0x180001536`
- `KERNEL32!SetLastError` at `0x180001536`

## pseudocode

```c

```
