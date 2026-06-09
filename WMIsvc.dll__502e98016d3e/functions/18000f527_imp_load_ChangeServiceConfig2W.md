# __imp_load_ChangeServiceConfig2W

- ea: `0x18000f527`
- end: `0x18000f533`
- name: `__imp_load_ChangeServiceConfig2W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000f484`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18000f527`

## pseudocode

```c
__int64 load_ChangeServiceConfig2W()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000f527  lea     rax, __imp_ChangeServiceConfig2W
0x18000f52e  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
