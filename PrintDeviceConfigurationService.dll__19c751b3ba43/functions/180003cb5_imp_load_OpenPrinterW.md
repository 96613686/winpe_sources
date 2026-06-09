# __imp_load_OpenPrinterW

- ea: `0x180003cb5`
- end: `0x180003cc1`
- name: `__imp_load_OpenPrinterW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003c36`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180003cb5`

## pseudocode

```c
__int64 load_OpenPrinterW()
{
  return _tailMerge_winspool_drv();
}

```

## disassembly

```asm
0x180003cb5  lea     rax, __imp_OpenPrinterW
0x180003cbc  jmp     __tailMerge_winspool_drv
```
