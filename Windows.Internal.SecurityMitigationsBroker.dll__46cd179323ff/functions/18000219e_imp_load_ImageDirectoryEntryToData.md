# __imp_load_ImageDirectoryEntryToData

- ea: `0x18000219e`
- end: `0x1800021aa`
- name: `__imp_load_ImageDirectoryEntryToData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000210d`

## import_xrefs

- `imagehlp!ImageDirectoryEntryToData` at `0x18000219e`

## pseudocode

```c
__int64 load_ImageDirectoryEntryToData()
{
  return _tailMerge_imagehlp_dll();
}

```

## disassembly

```asm
0x18000219e  lea     rax, __imp_ImageDirectoryEntryToData
0x1800021a5  jmp     __tailMerge_imagehlp_dll
```
