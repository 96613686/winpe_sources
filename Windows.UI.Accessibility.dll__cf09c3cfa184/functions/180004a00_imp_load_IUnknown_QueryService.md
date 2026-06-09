# __imp_load_IUnknown_QueryService

- ea: `0x180004a00`
- end: `0x180004a0c`
- name: `__imp_load_IUnknown_QueryService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000497e`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180004a00`

## pseudocode

```c
__int64 load_IUnknown_QueryService()
{
  return _tailMerge_api_ms_win_shcore_comhelpers_l1_1_0_dll();
}

```

## disassembly

```asm
0x180004a00  lea     rax, __imp_IUnknown_QueryService
0x180004a07  jmp     __tailMerge_api_ms_win_shcore_comhelpers_l1_1_0_dll
```
