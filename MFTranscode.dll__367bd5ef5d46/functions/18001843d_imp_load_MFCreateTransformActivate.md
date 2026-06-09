# __imp_load_MFCreateTransformActivate

- ea: `0x18001843d`
- end: `0x180018449`
- name: `__imp_load_MFCreateTransformActivate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!MFCreateTransformActivate` at `0x18001843d`

## pseudocode

```c
__int64 load_MFCreateTransformActivate()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x18001843d  lea     rax, __imp_MFCreateTransformActivate
0x180018444  jmp     __tailMerge_mfplat_dll
```
