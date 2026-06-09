# __imp_load_SHTaskPoolQueueTask

- ea: `0x18002afd4`
- end: `0x18002afe0`
- name: `__imp_load_SHTaskPoolQueueTask`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002af55`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002afd4`

## pseudocode

```c
__int64 load_SHTaskPoolQueueTask()
{
  return _tailMerge_api_ms_win_shcore_taskpool_l1_1_0_dll();
}

```

## disassembly

```asm
0x18002afd4  lea     rax, __imp_SHTaskPoolQueueTask
0x18002afdb  jmp     __tailMerge_api_ms_win_shcore_taskpool_l1_1_0_dll
```
