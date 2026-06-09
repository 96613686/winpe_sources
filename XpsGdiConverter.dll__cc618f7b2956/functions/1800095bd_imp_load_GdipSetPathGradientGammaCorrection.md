# __imp_load_GdipSetPathGradientGammaCorrection

- ea: `0x1800095bd`
- end: `0x1800095c9`
- name: `__imp_load_GdipSetPathGradientGammaCorrection`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x1800095bd`

## pseudocode

```c
__int64 load_GdipSetPathGradientGammaCorrection()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800095bd  lea     rax, __imp_GdipSetPathGradientGammaCorrection
0x1800095c4  jmp     __tailMerge_gdiplus_dll
```
