# __imp_load_WTSQueryUserToken

- ea: `0x180002555`
- end: `0x180002561`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024d6`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180002555`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002555  lea     rax, __imp_WTSQueryUserToken
0x18000255c  jmp     __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll
```
