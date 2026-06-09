# __imp_load_GdipDeletePath

- ea: `0x1800096a7`
- end: `0x1800096b3`
- name: `__imp_load_GdipDeletePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipDeletePath` at `0x1800096a7`

## pseudocode

```c
__int64 load_GdipDeletePath()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800096a7  lea     rax, __imp_GdipDeletePath
0x1800096ae  jmp     __tailMerge_gdiplus_dll
```
