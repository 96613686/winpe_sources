# __imp_load_GdipFillPath

- ea: `0x1800095cf`
- end: `0x1800095db`
- name: `__imp_load_GdipFillPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipFillPath` at `0x1800095cf`

## pseudocode

```c
__int64 load_GdipFillPath()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800095cf  lea     rax, __imp_GdipFillPath
0x1800095d6  jmp     __tailMerge_gdiplus_dll
```
