# __imp_load_GdipCreateTexture2I

- ea: `0x1800096ef`
- end: `0x1800096fb`
- name: `__imp_load_GdipCreateTexture2I`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateTexture2I` at `0x1800096ef`

## pseudocode

```c
__int64 load_GdipCreateTexture2I()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800096ef  lea     rax, __imp_GdipCreateTexture2I
0x1800096f6  jmp     __tailMerge_gdiplus_dll
```
