# __imp_load_GdipSetPathGradientWrapMode

- ea: `0x1800095f3`
- end: `0x1800095ff`
- name: `__imp_load_GdipSetPathGradientWrapMode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetPathGradientWrapMode` at `0x1800095f3`

## pseudocode

```c
__int64 load_GdipSetPathGradientWrapMode()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800095f3  lea     rax, __imp_GdipSetPathGradientWrapMode
0x1800095fa  jmp     __tailMerge_gdiplus_dll
```
