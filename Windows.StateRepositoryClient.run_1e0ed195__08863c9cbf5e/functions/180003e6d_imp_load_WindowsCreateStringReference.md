# __imp_load_WindowsCreateStringReference

- ea: `0x180003e6d`
- end: `0x180003e79`
- name: `__imp_load_WindowsCreateStringReference`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003696`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003e6d`

## pseudocode

```c
__int64 load_WindowsCreateStringReference()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003e6d  lea     rax, __imp_WindowsCreateStringReference
0x180003e74  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
