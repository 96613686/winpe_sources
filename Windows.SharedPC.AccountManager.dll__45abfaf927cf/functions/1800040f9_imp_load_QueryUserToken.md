# __imp_load_QueryUserToken

- ea: `0x1800040f9`
- end: `0x180004105`
- name: `__imp_load_QueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000407a`

## import_xrefs

- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800040f9`

## pseudocode

```c
__int64 load_QueryUserToken()
{
  return _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800040f9  lea     rax, __imp_QueryUserToken
0x180004100  jmp     __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll
```
