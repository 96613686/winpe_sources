# __imp_load_MsiGetComponentPathW

- ea: `0x180002387`
- end: `0x180002393`
- name: `__imp_load_MsiGetComponentPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800022f6`

## import_xrefs

- `msi!__imp_MsiGetComponentPathW` at `0x180002387`

## pseudocode

```c
__int64 load_MsiGetComponentPathW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x180002387  lea     rax, __imp_MsiGetComponentPathW
0x18000238e  jmp     __tailMerge_msi_dll
```
