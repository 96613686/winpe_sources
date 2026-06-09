# __imp_load_UMgrGetConstrainedUserToken

- ea: `0x18000e04c`
- end: `0x18000e058`
- name: `__imp_load_UMgrGetConstrainedUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003488`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18000e04c`

## pseudocode

```c
__int64 load_UMgrGetConstrainedUserToken()
{
  return _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000e04c  lea     rax, __imp_UMgrGetConstrainedUserToken
0x18000e053  jmp     __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll
```
