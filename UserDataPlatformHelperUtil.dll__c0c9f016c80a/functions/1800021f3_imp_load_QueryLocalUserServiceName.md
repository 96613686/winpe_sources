# __imp_load_QueryLocalUserServiceName

- ea: `0x1800021f3`
- end: `0x1800021ff`
- name: `__imp_load_QueryLocalUserServiceName`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002174`

## import_xrefs

- `api-ms-win-service-private-l1-1-2!QueryLocalUserServiceName` at `0x1800021f3`

## pseudocode

```c
__int64 load_QueryLocalUserServiceName()
{
  return _tailMerge_api_ms_win_service_private_l1_1_2_dll();
}

```

## disassembly

```asm
0x1800021f3  lea     rax, __imp_QueryLocalUserServiceName
0x1800021fa  jmp     __tailMerge_api_ms_win_service_private_l1_1_2_dll
```
