# __imp_load_QueryServiceStatusEx

- ea: `0x180005e01`
- end: `0x180005e0d`
- name: `__imp_load_QueryServiceStatusEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180005d82`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180005e01`

## pseudocode

```c
__int64 load_QueryServiceStatusEx()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x180005e01  lea     rax, __imp_QueryServiceStatusEx
0x180005e08  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
