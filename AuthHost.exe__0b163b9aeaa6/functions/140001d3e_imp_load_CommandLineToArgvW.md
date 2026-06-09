# __imp_load_CommandLineToArgvW

- ea: `0x140001d3e`
- end: `0x140001d4a`
- name: `__imp_load_CommandLineToArgvW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001cbf`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140001d3e`

## pseudocode

```c
__int64 load_CommandLineToArgvW()
{
  return _tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll();
}

```

## disassembly

```asm
0x140001d3e  lea     rax, __imp_CommandLineToArgvW
0x140001d45  jmp     __tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll
```
