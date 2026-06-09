# __imp_load_StringFromCLSID

- ea: `0x1800202b4`
- end: `0x1800202c0`
- name: `__imp_load_StringFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002003a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800202b4`

## pseudocode

```c
__int64 load_StringFromCLSID()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800202b4  lea     rax, __imp_StringFromCLSID
0x1800202bb  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
