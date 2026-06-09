# __imp_load_UMgrQuerySessionUserToken

- ea: `0x1800023d7`
- end: `0x1800023e3`
- name: `__imp_load_UMgrQuerySessionUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002346`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x1800023d7`

## pseudocode

```c
__int64 load_UMgrQuerySessionUserToken()
{
  return _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800023d7  lea     rax, __imp_UMgrQuerySessionUserToken
0x1800023de  jmp     __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll
```
