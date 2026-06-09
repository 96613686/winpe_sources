# __imp_load_OpenProcessForQuery

- ea: `0x180002424`
- end: `0x180002430`
- name: `__imp_load_OpenProcessForQuery`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023a5`

## import_xrefs

- `api-ms-win-coreui-secruntime-l1-1-0!OpenProcessForQuery` at `0x180002424`

## pseudocode

```c
__int64 load_OpenProcessForQuery()
{
  return _tailMerge_api_ms_win_coreui_secruntime_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002424  lea     rax, __imp_OpenProcessForQuery
0x18000242b  jmp     __tailMerge_api_ms_win_coreui_secruntime_l1_1_0_dll
```
