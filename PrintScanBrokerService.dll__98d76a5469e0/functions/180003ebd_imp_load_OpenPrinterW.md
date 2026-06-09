# __imp_load_OpenPrinterW

- ea: `0x180003ebd`
- end: `0x180003ec9`
- name: `__imp_load_OpenPrinterW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003e2c`

## import_xrefs

- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180003ebd`

## pseudocode

```c
__int64 load_OpenPrinterW()
{
  return _tailMerge_ext_ms_win_printer_winspool_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003ebd  lea     rax, __imp_OpenPrinterW
0x180003ec4  jmp     __tailMerge_ext_ms_win_printer_winspool_core_l1_1_0_dll
```
