# RemoveTreeProtection

- ea: `0x180076cfc`
- end: `0x180076dc4`
- name: `RemoveTreeProtection`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180076980`

## callees

- `0x180076cfc`
- `0x180076f04`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180076d35`
- `KERNEL32!GetProcAddress` at `0x180076d35`
- `KERNEL32!GetModuleHandleW` at `0x180076d1a`
- `KERNEL32!GetModuleHandleW` at `0x180076d1a`

## string_xrefs

- `0x180076d13`: `advapi32.dll`
- `0x180076d2b`: `TreeResetNamedSecurityInfoW`
- `0x180076d8f`: `Error %08d setting admin access of [%ws]\n`

## pseudocode

```c

```
