# __imp_load_OleCreateFontIndirectExt

- ea: `0x18004ea45`
- end: `0x18004ea51`
- name: `__imp_load_OleCreateFontIndirectExt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004e8ca`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreateFontIndirectExt` at `0x18004ea45`

## pseudocode

```c
__int64 load_OleCreateFontIndirectExt()
{
  return _tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004ea45  lea     rax, __imp_OleCreateFontIndirectExt
0x18004ea4c  jmp     __tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll
```
