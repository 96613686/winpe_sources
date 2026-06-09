# __imp_load_WindowsCreateStringReference

- ea: `0x1400023f9`
- end: `0x140002405`
- name: `__imp_load_WindowsCreateStringReference`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000237a`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400023f9`

## pseudocode

```c
__int64 load_WindowsCreateStringReference()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400023f9  lea     rax, __imp_WindowsCreateStringReference
0x140002400  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
