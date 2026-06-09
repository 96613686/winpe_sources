# __imp_load_RegisterServiceCtrlHandlerExW

- ea: `0x140003379`
- end: `0x140003385`
- name: `__imp_load_RegisterServiceCtrlHandlerExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1400032d6`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140003379`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerExW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003379  lea     rax, __imp_RegisterServiceCtrlHandlerExW
0x140003380  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
