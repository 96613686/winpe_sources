# __imp_load_WindowsDeleteString

- ea: `0x1800055c5`
- end: `0x1800055d1`
- name: `__imp_load_WindowsDeleteString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800053d6`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800055c5`

## pseudocode

```c
__int64 load_WindowsDeleteString()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800055c5  lea     rax, __imp_WindowsDeleteString
0x1800055cc  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
