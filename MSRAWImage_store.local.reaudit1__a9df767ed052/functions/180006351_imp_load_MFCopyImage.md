# __imp_load_MFCopyImage

- ea: `0x180006351`
- end: `0x18000635d`
- name: `__imp_load_MFCopyImage`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005ba0`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180006351`

## pseudocode

```c
__int64 load_MFCopyImage()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180006351  lea     rax, __imp_MFCopyImage
0x180006358  jmp     __tailMerge_mfplat_dll
```
