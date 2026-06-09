# __imp_load_GdipSetPathGradientCenterPointI

- ea: `0x180009551`
- end: `0x18000955d`
- name: `__imp_load_GdipSetPathGradientCenterPointI`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetPathGradientCenterPointI` at `0x180009551`

## pseudocode

```c
__int64 load_GdipSetPathGradientCenterPointI()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009551  lea     rax, __imp_GdipSetPathGradientCenterPointI
0x180009558  jmp     __tailMerge_gdiplus_dll
```
