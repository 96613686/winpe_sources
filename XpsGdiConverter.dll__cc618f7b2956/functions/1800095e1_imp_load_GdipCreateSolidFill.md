# __imp_load_GdipCreateSolidFill

- ea: `0x1800095e1`
- end: `0x1800095ed`
- name: `__imp_load_GdipCreateSolidFill`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreateSolidFill` at `0x1800095e1`

## pseudocode

```c
__int64 load_GdipCreateSolidFill()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800095e1  lea     rax, __imp_GdipCreateSolidFill
0x1800095e8  jmp     __tailMerge_gdiplus_dll
```
