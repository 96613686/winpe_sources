# __imp_load_WaitServiceState

- ea: `0x180003a84`
- end: `0x180003a90`
- name: `__imp_load_WaitServiceState`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003a05`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180003a84`

## pseudocode

```c
__int64 load_WaitServiceState()
{
  return _tailMerge_api_ms_win_service_private_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003a84  lea     rax, __imp_WaitServiceState
0x180003a8b  jmp     __tailMerge_api_ms_win_service_private_l1_1_0_dll
```
