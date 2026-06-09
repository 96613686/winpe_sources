# __imp_load_GdipCreatePathGradientFromPath

- ea: `0x180009683`
- end: `0x18000968f`
- name: `__imp_load_GdipCreatePathGradientFromPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreatePathGradientFromPath` at `0x180009683`

## pseudocode

```c
__int64 load_GdipCreatePathGradientFromPath()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009683  lea     rax, __imp_GdipCreatePathGradientFromPath
0x18000968a  jmp     __tailMerge_gdiplus_dll
```
