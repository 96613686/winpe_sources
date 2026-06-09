# __imp_load_GdipDeleteMatrix

- ea: `0x1800094c1`
- end: `0x1800094cd`
- name: `__imp_load_GdipDeleteMatrix`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipDeleteMatrix` at `0x1800094c1`

## pseudocode

```c
__int64 load_GdipDeleteMatrix()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800094c1  lea     rax, __imp_GdipDeleteMatrix
0x1800094c8  jmp     __tailMerge_gdiplus_dll
```
