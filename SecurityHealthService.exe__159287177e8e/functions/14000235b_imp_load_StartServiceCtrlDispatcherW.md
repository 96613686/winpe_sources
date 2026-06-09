# __imp_load_StartServiceCtrlDispatcherW

- ea: `0x14000235b`
- end: `0x140002367`
- name: `__imp_load_StartServiceCtrlDispatcherW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x14000222d`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14000235b`

## pseudocode

```c
__int64 load_StartServiceCtrlDispatcherW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000235b  lea     rax, __imp_StartServiceCtrlDispatcherW
0x140002362  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
