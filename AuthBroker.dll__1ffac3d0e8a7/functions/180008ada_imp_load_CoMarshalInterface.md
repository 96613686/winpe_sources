# __imp_load_CoMarshalInterface

- ea: `0x180008ada`
- end: `0x180008ae6`
- name: `__imp_load_CoMarshalInterface`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008643`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180008ada`

## pseudocode

```c
__int64 load_CoMarshalInterface()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008ada  lea     rax, __imp_CoMarshalInterface
0x180008ae1  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
