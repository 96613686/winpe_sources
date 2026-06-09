# __imp_load_GetLengthSid

- ea: `0x18000a794`
- end: `0x18000a7a0`
- name: `__imp_load_GetLengthSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a794`

## pseudocode

```c
__int64 load_GetLengthSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a794  lea     rax, __imp_GetLengthSid
0x18000a79b  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
