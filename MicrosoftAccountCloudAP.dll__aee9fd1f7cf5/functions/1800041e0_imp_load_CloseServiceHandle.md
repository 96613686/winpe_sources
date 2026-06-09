# __imp_load_CloseServiceHandle

- ea: `0x1800041e0`
- end: `0x1800041ec`
- name: `__imp_load_CloseServiceHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800040b2`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041e0`

## pseudocode

```c
__int64 load_CloseServiceHandle()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800041e0  lea     rax, __imp_CloseServiceHandle
0x1800041e7  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
