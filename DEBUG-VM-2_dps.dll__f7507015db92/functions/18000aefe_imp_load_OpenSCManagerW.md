# __imp_load_OpenSCManagerW

- ea: `0x18000aefe`
- end: `0x18000af0a`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000ad88`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000aefe`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aefe  lea     rax, __imp_OpenSCManagerW
0x18000af05  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
