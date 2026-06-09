# __imp_load_ChangeServiceConfigW

- ea: `0x1800021a0`
- end: `0x1800021ac`
- name: `__imp_load_ChangeServiceConfigW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000211c`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800021a0`

## pseudocode

```c
__int64 load_ChangeServiceConfigW()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800021a0  lea     rax, __imp_ChangeServiceConfigW
0x1800021a7  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
