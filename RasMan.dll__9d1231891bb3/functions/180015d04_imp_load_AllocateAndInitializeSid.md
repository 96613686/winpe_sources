# __imp_load_AllocateAndInitializeSid

- ea: `0x180015d04`
- end: `0x180015d10`
- name: `__imp_load_AllocateAndInitializeSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001586b`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015d04`

## pseudocode

```c
__int64 load_AllocateAndInitializeSid()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180015d04  lea     rax, __imp_AllocateAndInitializeSid
0x180015d0b  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
