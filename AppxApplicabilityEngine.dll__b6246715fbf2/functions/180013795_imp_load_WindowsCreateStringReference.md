# __imp_load_WindowsCreateStringReference

- ea: `0x180013795`
- end: `0x1800137a1`
- name: `__imp_load_WindowsCreateStringReference`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800136e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013795`

## pseudocode

```c
__int64 load_WindowsCreateStringReference()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x180013795  lea     rax, __imp_WindowsCreateStringReference
0x18001379c  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```
