# __imp_load_CreateFontW

- ea: `0x14000462f`
- end: `0x14000463b`
- name: `__imp_load_CreateFontW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400045b0`

## import_xrefs

- `ext-ms-win-gdi-font-l1-1-2!CreateFontW` at `0x14000462f`

## pseudocode

```c
__int64 load_CreateFontW()
{
  return _tailMerge_ext_ms_win_gdi_font_l1_1_2_dll();
}

```

## disassembly

```asm
0x14000462f  lea     rax, __imp_CreateFontW
0x140004636  jmp     __tailMerge_ext_ms_win_gdi_font_l1_1_2_dll
```
