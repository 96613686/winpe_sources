# __imp_load_WindowsDeleteString

- ea: `0x140009b14`
- end: `0x140009b20`
- name: `__imp_load_WindowsDeleteString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000984d`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009b14`

## pseudocode

```c
__int64 load_WindowsDeleteString()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x140009b14  lea     rax, __imp_WindowsDeleteString
0x140009b1b  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
