# __imp_load_OpenSCManagerW

- ea: `0x18000374f`
- end: `0x18000375b`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800036d0`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000374f`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000374f  lea     rax, __imp_OpenSCManagerW
0x180003756  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
