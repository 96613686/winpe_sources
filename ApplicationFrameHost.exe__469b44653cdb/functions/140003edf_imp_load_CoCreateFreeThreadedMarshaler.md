# __imp_load_CoCreateFreeThreadedMarshaler

- ea: `0x140003edf`
- end: `0x140003eeb`
- name: `__imp_load_CoCreateFreeThreadedMarshaler`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003e4e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140003edf`

## pseudocode

```c
__int64 load_CoCreateFreeThreadedMarshaler()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003edf  lea     rax, __imp_CoCreateFreeThreadedMarshaler
0x140003ee6  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
