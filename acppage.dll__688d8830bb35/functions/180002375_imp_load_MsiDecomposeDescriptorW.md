# __imp_load_MsiDecomposeDescriptorW

- ea: `0x180002375`
- end: `0x180002381`
- name: `__imp_load_MsiDecomposeDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800022f6`

## import_xrefs

- `msi!__imp_MsiDecomposeDescriptorW` at `0x180002375`

## pseudocode

```c
__int64 load_MsiDecomposeDescriptorW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x180002375  lea     rax, __imp_MsiDecomposeDescriptorW
0x18000237c  jmp     __tailMerge_msi_dll
```
