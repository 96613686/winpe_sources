# __imp_load_StartServiceCtrlDispatcherW

- ea: `0x140003355`
- end: `0x140003361`
- name: `__imp_load_StartServiceCtrlDispatcherW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1400032d6`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140003355`

## pseudocode

```c
__int64 load_StartServiceCtrlDispatcherW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003355  lea     rax, __imp_StartServiceCtrlDispatcherW
0x14000335c  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
