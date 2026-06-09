# __imp_load_QueryServiceConfigW

- ea: `0x1800041bc`
- end: `0x1800041c8`
- name: `__imp_load_QueryServiceConfigW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000413d`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800041bc`

## pseudocode

```c
__int64 load_QueryServiceConfigW()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800041bc  lea     rax, __imp_QueryServiceConfigW
0x1800041c3  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
