# __imp_load_UMgrQueryUserToken

- ea: `0x180002c48`
- end: `0x180002c54`
- name: `__imp_load_UMgrQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002bc9`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180002c48`

## pseudocode

```c
__int64 load_UMgrQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002c48  lea     rax, __imp_UMgrQueryUserToken
0x180002c4f  jmp     __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll
```
