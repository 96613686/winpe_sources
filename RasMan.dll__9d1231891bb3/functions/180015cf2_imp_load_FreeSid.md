# __imp_load_FreeSid

- ea: `0x180015cf2`
- end: `0x180015cfe`
- name: `__imp_load_FreeSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001586b`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180015cf2`

## pseudocode

```c
__int64 load_FreeSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180015cf2  lea     rax, __imp_FreeSid
0x180015cf9  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
