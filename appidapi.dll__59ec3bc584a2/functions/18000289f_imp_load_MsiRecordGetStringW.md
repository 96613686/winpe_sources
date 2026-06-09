# __imp_load_MsiRecordGetStringW

- ea: `0x18000289f`
- end: `0x1800028ab`
- name: `__imp_load_MsiRecordGetStringW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiRecordGetStringW` at `0x18000289f`

## pseudocode

```c
__int64 load_MsiRecordGetStringW()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x18000289f  lea     rax, __imp_MsiRecordGetStringW
0x1800028a6  jmp     __tailMerge_msi_dll
```
