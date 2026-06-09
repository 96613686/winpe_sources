# __imp_load_OpenServiceW

- ea: `0x180001ec0`
- end: `0x180001ecc`
- name: `__imp_load_OpenServiceW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001e20`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180001ec0`

## pseudocode

```c
__int64 load_OpenServiceW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001ec0  lea     rax, __imp_OpenServiceW
0x180001ec7  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
