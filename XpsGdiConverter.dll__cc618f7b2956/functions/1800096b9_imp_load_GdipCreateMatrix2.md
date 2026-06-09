# __imp_load_GdipCreateMatrix2

- ea: `0x1800096b9`
- end: `0x1800096c5`
- name: `__imp_load_GdipCreateMatrix2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateMatrix2` at `0x1800096b9`

## pseudocode

```c
__int64 load_GdipCreateMatrix2()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800096b9  lea     rax, __imp_GdipCreateMatrix2
0x1800096c0  jmp     __tailMerge_gdiplus_dll
```
