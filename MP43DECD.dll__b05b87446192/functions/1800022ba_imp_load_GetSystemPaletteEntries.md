# __imp_load_GetSystemPaletteEntries

- ea: `0x1800022ba`
- end: `0x1800022c6`
- name: `__imp_load_GetSystemPaletteEntries`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000223b`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x1800022ba`

## pseudocode

```c
__int64 load_GetSystemPaletteEntries()
{
  return _tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll();
}

```

## disassembly

```asm
0x1800022ba  lea     rax, __imp_GetSystemPaletteEntries
0x1800022c1  jmp     __tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll
```
