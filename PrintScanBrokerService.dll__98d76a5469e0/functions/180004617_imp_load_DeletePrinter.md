# __imp_load_DeletePrinter

- ea: `0x180004617`
- end: `0x180004623`
- name: `__imp_load_DeletePrinter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800044e9`

## import_xrefs

- `ext-ms-win-printer-winspool-l1-1-4!DeletePrinter` at `0x180004617`

## pseudocode

```c
__int64 load_DeletePrinter()
{
  return _tailMerge_ext_ms_win_printer_winspool_l1_1_4_dll();
}

```

## disassembly

```asm
0x180004617  lea     rax, __imp_DeletePrinter
0x18000461e  jmp     __tailMerge_ext_ms_win_printer_winspool_l1_1_4_dll
```
