# __imp_load_GdipSetPathGradientCenterColor

- ea: `0x180009695`
- end: `0x1800096a1`
- name: `__imp_load_GdipSetPathGradientCenterColor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetPathGradientCenterColor` at `0x180009695`

## pseudocode

```c
__int64 load_GdipSetPathGradientCenterColor()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009695  lea     rax, __imp_GdipSetPathGradientCenterColor
0x18000969c  jmp     __tailMerge_gdiplus_dll
```
