# __imp_load_PropVariantCopy

- ea: `0x18000358a`
- end: `0x180003596`
- name: `__imp_load_PropVariantCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000326e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000358a`

## pseudocode

```c
__int64 load_PropVariantCopy()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000358a  lea     rax, __imp_PropVariantCopy
0x180003591  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
