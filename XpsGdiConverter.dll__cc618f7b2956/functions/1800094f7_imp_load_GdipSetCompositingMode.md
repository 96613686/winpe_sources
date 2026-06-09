# __imp_load_GdipSetCompositingMode

- ea: `0x1800094f7`
- end: `0x180009503`
- name: `__imp_load_GdipSetCompositingMode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipSetCompositingMode` at `0x1800094f7`

## pseudocode

```c
__int64 load_GdipSetCompositingMode()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800094f7  lea     rax, __imp_GdipSetCompositingMode
0x1800094fe  jmp     __tailMerge_gdiplus_dll
```
