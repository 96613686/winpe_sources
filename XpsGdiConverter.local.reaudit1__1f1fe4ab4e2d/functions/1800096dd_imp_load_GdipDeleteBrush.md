# __imp_load_GdipDeleteBrush

- ea: `0x1800096dd`
- end: `0x1800096e9`
- name: `__imp_load_GdipDeleteBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x1800096dd`

## pseudocode

```c
__int64 load_GdipDeleteBrush()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800096dd  lea     rax, __imp_GdipDeleteBrush
0x1800096e4  jmp     __tailMerge_gdiplus_dll
```
