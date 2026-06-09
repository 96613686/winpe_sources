# __imp_load_CoTaskMemFree

- ea: `0x1800032ed`
- end: `0x1800032f9`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000326e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032ed`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800032ed  lea     rax, __imp_CoTaskMemFree
0x1800032f4  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
