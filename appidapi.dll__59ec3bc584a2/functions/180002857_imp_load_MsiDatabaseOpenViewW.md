# __imp_load_MsiDatabaseOpenViewW

- ea: `0x180002857`
- end: `0x180002863`
- name: `__imp_load_MsiDatabaseOpenViewW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiDatabaseOpenViewW` at `0x180002857`

## pseudocode

```c
__int64 load_MsiDatabaseOpenViewW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x180002857  lea     rax, __imp_MsiDatabaseOpenViewW
0x18000285e  jmp     __tailMerge_msi_dll
```
