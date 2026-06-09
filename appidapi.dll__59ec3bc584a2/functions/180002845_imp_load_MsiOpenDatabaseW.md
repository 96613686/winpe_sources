# __imp_load_MsiOpenDatabaseW

- ea: `0x180002845`
- end: `0x180002851`
- name: `__imp_load_MsiOpenDatabaseW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiOpenDatabaseW` at `0x180002845`

## pseudocode

```c
__int64 load_MsiOpenDatabaseW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x180002845  lea     rax, __imp_MsiOpenDatabaseW
0x18000284c  jmp     __tailMerge_msi_dll
```
