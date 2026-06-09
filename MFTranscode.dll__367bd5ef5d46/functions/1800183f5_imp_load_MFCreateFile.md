# __imp_load_MFCreateFile

- ea: `0x1800183f5`
- end: `0x180018401`
- name: `__imp_load_MFCreateFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateFile` at `0x1800183f5`

## pseudocode

```c
__int64 load_MFCreateFile()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x1800183f5  lea     rax, __imp_MFCreateFile
0x1800183fc  jmp     __tailMerge_mfplat_dll
```
