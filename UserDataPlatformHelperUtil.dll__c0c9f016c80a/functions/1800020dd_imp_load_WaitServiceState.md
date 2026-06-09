# __imp_load_WaitServiceState

- ea: `0x1800020dd`
- end: `0x1800020e9`
- name: `__imp_load_WaitServiceState`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000205e`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x1800020dd`

## pseudocode

```c
__int64 load_WaitServiceState()
{
  return _tailMerge_api_ms_win_service_private_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800020dd  lea     rax, __imp_WaitServiceState
0x1800020e4  jmp     __tailMerge_api_ms_win_service_private_l1_1_0_dll
```
