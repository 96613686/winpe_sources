# __imp_load_PropVariantCopy

- ea: `0x180055510`
- end: `0x18005551c`
- name: `__imp_load_PropVariantCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180055401`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180055510`

## pseudocode

```c
__int64 load_PropVariantCopy()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180055510  lea     rax, __imp_PropVariantCopy
0x180055517  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
