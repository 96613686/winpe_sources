# __imp_load_WerReportCreate

- ea: `0x1400065ba`
- end: `0x1400065c6`
- name: `__imp_load_WerReportCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000649e`

## import_xrefs

- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x1400065ba`

## pseudocode

```c
__int64 load_WerReportCreate()
{
  return _tailMerge_ext_ms_win_wer_reporting_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400065ba  lea     rax, __imp_WerReportCreate
0x1400065c1  jmp     __tailMerge_ext_ms_win_wer_reporting_l1_1_0_dll
```
