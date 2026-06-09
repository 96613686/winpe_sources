# __imp_load_GdipAddPathEllipse

- ea: `0x180009599`
- end: `0x1800095a5`
- name: `__imp_load_GdipAddPathEllipse`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipAddPathEllipse` at `0x180009599`

## pseudocode

```c
__int64 load_GdipAddPathEllipse()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180009599  lea     rax, __imp_GdipAddPathEllipse
0x1800095a0  jmp     __tailMerge_gdiplus_dll
```
