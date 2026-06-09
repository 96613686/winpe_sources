# __imp_load_IsValidSid

- ea: `0x18000a74c`
- end: `0x18000a758`
- name: `__imp_load_IsValidSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a74c`

## pseudocode

```c
__int64 load_IsValidSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a74c  lea     rax, __imp_IsValidSid
0x18000a753  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
