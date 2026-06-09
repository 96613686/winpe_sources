# __imp_load_CoCreateFreeThreadedMarshaler

- ea: `0x18001431e`
- end: `0x18001432a`
- name: `__imp_load_CoCreateFreeThreadedMarshaler`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001427b`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001431e`

## pseudocode

```c
__int64 load_CoCreateFreeThreadedMarshaler()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001431e  lea     rax, __imp_CoCreateFreeThreadedMarshaler
0x180014325  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
