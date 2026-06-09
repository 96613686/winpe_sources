# try_cor_exit_process

- ea: `0x180029dc8`
- end: `0x180029e2f`
- name: `try_cor_exit_process`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180029ca8`
- `0x180029d94`

## callees

- `0x180029dc8`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x180029df0`
- `KERNEL32!GetModuleHandleExW` at `0x180029df0`
- `KERNEL32!GetProcAddress` at `0x180029e06`
- `KERNEL32!GetProcAddress` at `0x180029e06`
- `KERNEL32!FreeLibrary` at `0x180029e22`
- `KERNEL32!FreeLibrary` at `0x180029e22`

## string_xrefs

- `0x180029de7`: `mscoree.dll`

## pseudocode

```c

```
