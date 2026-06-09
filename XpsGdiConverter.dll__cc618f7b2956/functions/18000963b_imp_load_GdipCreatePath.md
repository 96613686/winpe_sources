# __imp_load_GdipCreatePath

- ea: `0x18000963b`
- end: `0x180009647`
- name: `__imp_load_GdipCreatePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009442`

## import_xrefs

- `gdiplus!GdipCreatePath` at `0x18000963b`

## pseudocode

```c
__int64 load_GdipCreatePath()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x18000963b  lea     rax, __imp_GdipCreatePath
0x180009642  jmp     __tailMerge_gdiplus_dll
```
