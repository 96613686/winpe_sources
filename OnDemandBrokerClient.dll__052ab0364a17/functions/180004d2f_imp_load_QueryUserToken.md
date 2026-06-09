# __imp_load_QueryUserToken

- ea: `0x180004d2f`
- end: `0x180004d3b`
- name: `__imp_load_QueryUserToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004cb0`

## import_xrefs

- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180004d2f`

## pseudocode

```c
__int64 load_QueryUserToken()
{
  return _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll();
}

```

## disassembly

```asm
0x180004d2f  lea     rax, __imp_QueryUserToken
0x180004d36  jmp     __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll
```
