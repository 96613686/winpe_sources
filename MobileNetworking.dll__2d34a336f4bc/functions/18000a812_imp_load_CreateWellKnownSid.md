# __imp_load_CreateWellKnownSid

- ea: `0x18000a812`
- end: `0x18000a81e`
- name: `__imp_load_CreateWellKnownSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a812`

## pseudocode

```c
__int64 load_CreateWellKnownSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a812  lea     rax, __imp_CreateWellKnownSid
0x18000a819  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
