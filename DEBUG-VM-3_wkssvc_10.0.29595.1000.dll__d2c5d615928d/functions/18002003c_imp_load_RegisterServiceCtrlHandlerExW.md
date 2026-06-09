# __imp_load_RegisterServiceCtrlHandlerExW

- ea: `0x18002003c`
- end: `0x180020048`
- name: `__imp_load_RegisterServiceCtrlHandlerExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001ff87`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002003c`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerExW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002003c  lea     rax, __imp_RegisterServiceCtrlHandlerExW
0x180020043  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
