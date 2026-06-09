# __imp_load_ControlService

- ea: `0x1800037ec`
- end: `0x1800037f8`
- name: `__imp_load_ControlService`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000376d`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800037ec`

## pseudocode

```c
__int64 load_ControlService()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800037ec  lea     rax, __imp_ControlService
0x1800037f3  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
