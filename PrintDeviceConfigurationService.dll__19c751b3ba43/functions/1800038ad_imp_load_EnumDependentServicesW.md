# __imp_load_EnumDependentServicesW

- ea: `0x1800038ad`
- end: `0x1800038b9`
- name: `__imp_load_EnumDependentServicesW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000382e`

## import_xrefs

- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800038ad`

## pseudocode

```c
__int64 load_EnumDependentServicesW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_1_dll();
}

```

## disassembly

```asm
0x1800038ad  lea     rax, __imp_EnumDependentServicesW
0x1800038b4  jmp     __tailMerge_api_ms_win_service_core_l1_1_1_dll
```
