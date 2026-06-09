# __imp_load_OpenSCManagerW

- ea: `0x1800031f5`
- end: `0x180003201`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003152`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800031f5`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800031f5  lea     rax, __imp_OpenSCManagerW
0x1800031fc  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
