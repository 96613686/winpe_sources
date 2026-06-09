# __imp_load_QueryServiceConfigW

- ea: `0x18001c917`
- end: `0x18001c923`
- name: `__imp_load_QueryServiceConfigW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001c886`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001c917`

## pseudocode

```c
__int64 load_QueryServiceConfigW()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x18001c917  lea     rax, __imp_QueryServiceConfigW
0x18001c91e  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
