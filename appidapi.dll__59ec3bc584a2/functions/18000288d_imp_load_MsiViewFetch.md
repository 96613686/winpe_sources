# __imp_load_MsiViewFetch

- ea: `0x18000288d`
- end: `0x180002899`
- name: `__imp_load_MsiViewFetch`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiViewFetch` at `0x18000288d`

## pseudocode

```c
__int64 load_MsiViewFetch()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x18000288d  lea     rax, __imp_MsiViewFetch
0x180002894  jmp     __tailMerge_msi_dll
```
