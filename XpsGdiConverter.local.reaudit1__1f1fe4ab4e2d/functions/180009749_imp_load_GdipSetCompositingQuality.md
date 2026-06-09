# __imp_load_GdipSetCompositingQuality

- ea: `0x180009749`
- end: `0x180009755`
- name: `__imp_load_GdipSetCompositingQuality`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetCompositingQuality` at `0x180009749`

## pseudocode

```c
__int64 load_GdipSetCompositingQuality()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009749  lea     rax, __imp_GdipSetCompositingQuality
0x180009750  jmp     __tailMerge_gdiplus_dll
```
