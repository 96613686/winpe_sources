# __imp_load_GdipTransformPath

- ea: `0x180009701`
- end: `0x18000970d`
- name: `__imp_load_GdipTransformPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipTransformPath` at `0x180009701`

## pseudocode

```c
__int64 load_GdipTransformPath()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009701  lea     rax, __imp_GdipTransformPath
0x180009708  jmp     __tailMerge_gdiplus_dll
```
