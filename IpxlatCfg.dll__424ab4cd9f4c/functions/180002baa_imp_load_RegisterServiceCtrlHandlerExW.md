# __imp_load_RegisterServiceCtrlHandlerExW

- ea: `0x180002baa`
- end: `0x180002bb6`
- name: `__imp_load_RegisterServiceCtrlHandlerExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002b19`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002baa`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerExW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002baa  lea     rax, __imp_RegisterServiceCtrlHandlerExW
0x180002bb1  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
