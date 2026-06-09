# __imp_load_CoMarshalHresult

- ea: `0x18004e820`
- end: `0x18004e82c`
- name: `__imp_load_CoMarshalHresult`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004e686`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalHresult` at `0x18004e820`

## pseudocode

```c
__int64 load_CoMarshalHresult()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004e820  lea     rax, __imp_CoMarshalHresult
0x18004e827  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
