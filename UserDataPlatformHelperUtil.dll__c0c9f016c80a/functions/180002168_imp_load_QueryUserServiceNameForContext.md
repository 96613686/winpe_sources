# __imp_load_QueryUserServiceNameForContext

- ea: `0x180002168`
- end: `0x180002174`
- name: `__imp_load_QueryUserServiceNameForContext`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800020e9`

## import_xrefs

- `api-ms-win-service-private-l1-1-3!QueryUserServiceNameForContext` at `0x180002168`

## pseudocode

```c
__int64 load_QueryUserServiceNameForContext()
{
  return _tailMerge_api_ms_win_service_private_l1_1_3_dll();
}

```

## disassembly

```asm
0x180002168  lea     rax, __imp_QueryUserServiceNameForContext
0x18000216f  jmp     __tailMerge_api_ms_win_service_private_l1_1_3_dll
```
