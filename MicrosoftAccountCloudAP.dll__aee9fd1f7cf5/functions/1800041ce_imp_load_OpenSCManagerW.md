# __imp_load_OpenSCManagerW

- ea: `0x1800041ce`
- end: `0x1800041da`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800040b2`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800041ce`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800041ce  lea     rax, __imp_OpenSCManagerW
0x1800041d5  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
