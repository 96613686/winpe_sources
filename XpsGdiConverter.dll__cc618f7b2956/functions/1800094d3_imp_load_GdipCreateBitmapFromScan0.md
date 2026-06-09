# __imp_load_GdipCreateBitmapFromScan0

- ea: `0x1800094d3`
- end: `0x1800094df`
- name: `__imp_load_GdipCreateBitmapFromScan0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800094d3`

## pseudocode

```c
__int64 load_GdipCreateBitmapFromScan0()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800094d3  lea     rax, __imp_GdipCreateBitmapFromScan0
0x1800094da  jmp     __tailMerge_gdiplus_dll
```
