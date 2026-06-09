# __imp_load_SetServiceStatus

- ea: `0x180001fb0`
- end: `0x180001fbc`
- name: `__imp_load_SetServiceStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001f0c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001fb0`

## pseudocode

```c
__int64 load_SetServiceStatus()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001fb0  lea     rax, __imp_SetServiceStatus
0x180001fb7  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
