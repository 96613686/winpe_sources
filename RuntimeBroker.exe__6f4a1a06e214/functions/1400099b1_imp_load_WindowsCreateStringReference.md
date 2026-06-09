# __imp_load_WindowsCreateStringReference

- ea: `0x1400099b1`
- end: `0x1400099bd`
- name: `__imp_load_WindowsCreateStringReference`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000984d`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400099b1`

## pseudocode

```c
__int64 load_WindowsCreateStringReference()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400099b1  lea     rax, __imp_WindowsCreateStringReference
0x1400099b8  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
