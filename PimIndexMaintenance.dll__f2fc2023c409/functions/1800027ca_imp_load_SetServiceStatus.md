# __imp_load_SetServiceStatus

- ea: `0x1800027ca`
- end: `0x1800027d6`
- name: `__imp_load_SetServiceStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000274b`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800027ca`

## pseudocode

```c
__int64 load_SetServiceStatus()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800027ca  lea     rax, __imp_SetServiceStatus
0x1800027d1  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
