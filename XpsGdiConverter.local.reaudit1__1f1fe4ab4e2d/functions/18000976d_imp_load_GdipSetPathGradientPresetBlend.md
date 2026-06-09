# __imp_load_GdipSetPathGradientPresetBlend

- ea: `0x18000976d`
- end: `0x180009779`
- name: `__imp_load_GdipSetPathGradientPresetBlend`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18000976d`

## pseudocode

```c
__int64 load_GdipSetPathGradientPresetBlend()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x18000976d  lea     rax, __imp_GdipSetPathGradientPresetBlend
0x180009774  jmp     __tailMerge_gdiplus_dll
```
