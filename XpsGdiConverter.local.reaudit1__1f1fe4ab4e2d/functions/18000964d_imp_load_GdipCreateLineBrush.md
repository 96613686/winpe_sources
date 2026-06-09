# __imp_load_GdipCreateLineBrush

- ea: `0x18000964d`
- end: `0x180009659`
- name: `__imp_load_GdipCreateLineBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateLineBrush` at `0x18000964d`

## pseudocode

```c
__int64 load_GdipCreateLineBrush()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x18000964d  lea     rax, __imp_GdipCreateLineBrush
0x180009654  jmp     __tailMerge_gdiplus_dll
```
