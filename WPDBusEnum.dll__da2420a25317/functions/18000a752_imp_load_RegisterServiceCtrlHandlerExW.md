# __imp_load_RegisterServiceCtrlHandlerExW

- ea: `0x18000a752`
- end: `0x18000a75e`
- name: `__imp_load_RegisterServiceCtrlHandlerExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000a6d3`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000a752`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerExW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a752  lea     rax, __imp_RegisterServiceCtrlHandlerExW
0x18000a759  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
