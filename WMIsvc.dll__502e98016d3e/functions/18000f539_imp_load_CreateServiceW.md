# __imp_load_CreateServiceW

- ea: `0x18000f539`
- end: `0x18000f545`
- name: `__imp_load_CreateServiceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000f3e7`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18000f539`

## pseudocode

```c
__int64 load_CreateServiceW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f539  lea     rax, __imp_CreateServiceW
0x18000f540  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
