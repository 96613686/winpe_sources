# __imp_load_MsiViewExecute

- ea: `0x180002869`
- end: `0x180002875`
- name: `__imp_load_MsiViewExecute`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiViewExecute` at `0x180002869`

## pseudocode

```c
__int64 load_MsiViewExecute()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x180002869  lea     rax, __imp_MsiViewExecute
0x180002870  jmp     __tailMerge_msi_dll
```
