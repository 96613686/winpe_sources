# __imp_load_StringFromCLSID

- ea: `0x18000346e`
- end: `0x18000347a`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003395`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000346e`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000346e  lea     rax, __imp_StringFromCLSID
0x180003475  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
