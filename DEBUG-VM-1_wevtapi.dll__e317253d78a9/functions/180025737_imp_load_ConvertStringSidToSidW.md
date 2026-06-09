# __imp_load_ConvertStringSidToSidW

- ea: `0x180025737`
- end: `0x180025743`
- name: `__imp_load_ConvertStringSidToSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800256a6`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180025737`

## pseudocode

```c
__int64 load_ConvertStringSidToSidW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x180025737  lea     rax, __imp_ConvertStringSidToSidW
0x18002573e  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
