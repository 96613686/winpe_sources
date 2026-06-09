# __imp_load_WindowsCreateString

- ea: `0x1400098cc`
- end: `0x1400098d8`
- name: `__imp_load_WindowsCreateString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000984d`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400098cc`

## pseudocode

```c
__int64 load_WindowsCreateString()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400098cc  lea     rax, __imp_WindowsCreateString
0x1400098d3  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
