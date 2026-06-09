# __imp_load_MsiVerifyPackageW

- ea: `0x180002833`
- end: `0x18000283f`
- name: `__imp_load_MsiVerifyPackageW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiVerifyPackageW` at `0x180002833`

## pseudocode

```c
__int64 load_MsiVerifyPackageW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x180002833  lea     rax, __imp_MsiVerifyPackageW
0x18000283a  jmp     __tailMerge_msi_dll
```
