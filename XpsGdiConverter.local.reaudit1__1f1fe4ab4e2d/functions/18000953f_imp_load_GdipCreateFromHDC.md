# __imp_load_GdipCreateFromHDC

- ea: `0x18000953f`
- end: `0x18000954b`
- name: `__imp_load_GdipCreateFromHDC`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateFromHDC` at `0x18000953f`

## pseudocode

```c
__int64 load_GdipCreateFromHDC()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x18000953f  lea     rax, __imp_GdipCreateFromHDC
0x180009546  jmp     __tailMerge_gdiplus_dll
```
