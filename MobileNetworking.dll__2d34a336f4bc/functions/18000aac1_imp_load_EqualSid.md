# __imp_load_EqualSid

- ea: `0x18000aac1`
- end: `0x18000aacd`
- name: `__imp_load_EqualSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000aac1`

## pseudocode

```c
__int64 load_EqualSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aac1  lea     rax, __imp_EqualSid
0x18000aac8  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
