# __imp_load_CreateDIBSection

- ea: `0x180016f11`
- end: `0x180016f1d`
- name: `__imp_load_CreateDIBSection`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016e92`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180016f11`

## pseudocode

```c
__int64 load_CreateDIBSection()
{
  return _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll();
}

```

## disassembly

```asm
0x180016f11  lea     rax, __imp_CreateDIBSection
0x180016f18  jmp     __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll
```
