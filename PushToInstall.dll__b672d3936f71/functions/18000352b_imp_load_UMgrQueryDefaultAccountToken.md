# __imp_load_UMgrQueryDefaultAccountToken

- ea: `0x18000352b`
- end: `0x180003537`
- name: `__imp_load_UMgrQueryDefaultAccountToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003488`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18000352b`

## pseudocode

```c
__int64 load_UMgrQueryDefaultAccountToken()
{
  return _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000352b  lea     rax, __imp_UMgrQueryDefaultAccountToken
0x180003532  jmp     __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll
```
