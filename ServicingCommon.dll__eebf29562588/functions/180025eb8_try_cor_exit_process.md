# try_cor_exit_process

- ea: `0x180025eb8`
- end: `0x180025f1f`
- name: `try_cor_exit_process`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025d98`
- `0x180025e84`

## callees

- `0x180025eb8`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x180025ee0`
- `KERNEL32!GetModuleHandleExW` at `0x180025ee0`
- `KERNEL32!GetProcAddress` at `0x180025ef6`
- `KERNEL32!GetProcAddress` at `0x180025ef6`
- `KERNEL32!FreeLibrary` at `0x180025f12`
- `KERNEL32!FreeLibrary` at `0x180025f12`

## string_xrefs

- `0x180025ed7`: `mscoree.dll`

## pseudocode

```c

```
