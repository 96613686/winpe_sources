# __imp_load_OpenSCManagerW

- ea: `0x180004b2c`
- end: `0x180004b38`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180004aad`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004b2c`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x180004b2c  lea     rax, __imp_OpenSCManagerW
0x180004b33  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
