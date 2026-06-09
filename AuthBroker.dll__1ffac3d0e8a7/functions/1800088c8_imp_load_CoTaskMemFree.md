# __imp_load_CoTaskMemFree

- ea: `0x1800088c8`
- end: `0x1800088d4`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008643`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088c8`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800088c8  lea     rax, __imp_CoTaskMemFree
0x1800088cf  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
