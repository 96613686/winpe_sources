# __imp_load_WindowsDeleteString

- ea: `0x18000315c`
- end: `0x180003168`
- name: `__imp_load_WindowsDeleteString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ed0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000315c`

## pseudocode

```c
__int64 load_WindowsDeleteString()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000315c  lea     rax, __imp_WindowsDeleteString
0x180003163  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
