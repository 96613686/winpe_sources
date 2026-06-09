# __imp_load_UMgrQueryUserTokenFromSid

- ea: `0x1800023e9`
- end: `0x1800023f5`
- name: `__imp_load_UMgrQueryUserTokenFromSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180002346`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x1800023e9`

## pseudocode

```c
__int64 load_UMgrQueryUserTokenFromSid()
{
  return _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800023e9  lea     rax, __imp_UMgrQueryUserTokenFromSid
0x1800023f0  jmp     __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll
```
