# __imp_load_CoMarshalInterface

- ea: `0x180014aab`
- end: `0x180014ab7`
- name: `__imp_load_CoMarshalInterface`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001427b`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180014aab`

## pseudocode

```c
__int64 load_CoMarshalInterface()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180014aab  lea     rax, __imp_CoMarshalInterface
0x180014ab2  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
