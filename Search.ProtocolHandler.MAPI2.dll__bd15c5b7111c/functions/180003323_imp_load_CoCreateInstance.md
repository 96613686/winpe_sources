# __imp_load_CoCreateInstance

- ea: `0x180003323`
- end: `0x18000332f`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000326e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003323`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003323  lea     rax, __imp_CoCreateInstance
0x18000332a  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
