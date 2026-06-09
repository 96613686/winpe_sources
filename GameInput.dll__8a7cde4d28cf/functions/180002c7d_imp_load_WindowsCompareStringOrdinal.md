# __imp_load_WindowsCompareStringOrdinal

- ea: `0x180002c7d`
- end: `0x180002c89`
- name: `__imp_load_WindowsCompareStringOrdinal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002bc8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180002c7d`

## pseudocode

```c
__int64 load_WindowsCompareStringOrdinal()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002c7d  lea     rax, __imp_WindowsCompareStringOrdinal
0x180002c84  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
