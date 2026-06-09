# __imp_load_WindowsCreateStringReference

- ea: `0x180002d78`
- end: `0x180002d84`
- name: `__imp_load_WindowsCreateStringReference`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002954`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002d78`

## pseudocode

```c
__int64 load_WindowsCreateStringReference()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002d78  lea     rax, __imp_WindowsCreateStringReference
0x180002d7f  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
