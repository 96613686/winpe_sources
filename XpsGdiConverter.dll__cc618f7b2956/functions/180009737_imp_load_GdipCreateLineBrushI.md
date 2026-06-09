# __imp_load_GdipCreateLineBrushI

- ea: `0x180009737`
- end: `0x180009743`
- name: `__imp_load_GdipCreateLineBrushI`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateLineBrushI` at `0x180009737`

## pseudocode

```c
__int64 load_GdipCreateLineBrushI()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009737  lea     rax, __imp_GdipCreateLineBrushI
0x18000973e  jmp     __tailMerge_gdiplus_dll
```
