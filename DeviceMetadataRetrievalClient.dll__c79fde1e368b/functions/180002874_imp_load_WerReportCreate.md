# __imp_load_WerReportCreate

- ea: `0x180002874`
- end: `0x180002880`
- name: `__imp_load_WerReportCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800027f5`

## import_xrefs

- `wer!WerReportCreate` at `0x180002874`

## pseudocode

```c
__int64 load_WerReportCreate()
{
  return _tailMerge_wer_dll();
}

```

## disassembly

```asm
0x180002874  lea     rax, __imp_WerReportCreate
0x18000287b  jmp     __tailMerge_wer_dll
```
