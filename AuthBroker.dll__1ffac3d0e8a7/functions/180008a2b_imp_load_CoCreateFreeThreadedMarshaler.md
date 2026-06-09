# __imp_load_CoCreateFreeThreadedMarshaler

- ea: `0x180008a2b`
- end: `0x180008a37`
- name: `__imp_load_CoCreateFreeThreadedMarshaler`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008643`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008a2b`

## pseudocode

```c
__int64 load_CoCreateFreeThreadedMarshaler()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008a2b  lea     rax, __imp_CoCreateFreeThreadedMarshaler
0x180008a32  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
