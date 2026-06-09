# RemoveTreeProtection

- ea: `0x18007698c`
- end: `0x180076a54`
- name: `RemoveTreeProtection`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180076610`

## callees

- `0x18007698c`
- `0x180076b94`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800769c5`
- `KERNEL32!GetProcAddress` at `0x1800769c5`
- `KERNEL32!GetModuleHandleW` at `0x1800769aa`
- `KERNEL32!GetModuleHandleW` at `0x1800769aa`

## string_xrefs

- `0x1800769a3`: `advapi32.dll`
- `0x1800769bb`: `TreeResetNamedSecurityInfoW`
- `0x180076a1f`: `Error %08d setting admin access of [%ws]\n`

## pseudocode

```c

```
