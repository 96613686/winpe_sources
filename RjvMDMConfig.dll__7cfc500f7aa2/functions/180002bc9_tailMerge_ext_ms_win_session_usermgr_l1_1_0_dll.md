# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x180002bc9`
- end: `0x180002c42`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c48`
- `0x180002c5a`
- `0x180002cc0`

## callees

- `0x180002bc9`
- `0x18001ca20`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002bc9  mov     [rsp+arg_0], rcx
0x180002bce  mov     [rsp+arg_8], rdx
0x180002bd3  mov     [rsp+arg_10], r8
0x180002bd8  mov     [rsp+arg_18], r9
0x180002bdd  sub     rsp, 68h
0x180002be1  movdqa  [rsp+68h+var_48], xmm0
0x180002be7  movdqa  [rsp+68h+var_38], xmm1
0x180002bed  movdqa  [rsp+68h+var_28], xmm2
0x180002bf3  movdqa  [rsp+68h+var_18], xmm3
0x180002bf9  mov     rdx, rax
0x180002bfc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x180002c03  call    __delayLoadHelper2
0x180002c08  movdqa  xmm0, [rsp+68h+var_48]
0x180002c0e  movdqa  xmm1, [rsp+68h+var_38]
0x180002c14  movdqa  xmm2, [rsp+68h+var_28]
0x180002c1a  movdqa  xmm3, [rsp+68h+var_18]
0x180002c20  mov     rcx, [rsp+68h+arg_0]
0x180002c25  mov     rdx, [rsp+68h+arg_8]
0x180002c2a  mov     r8, [rsp+68h+arg_10]
0x180002c32  mov     r9, [rsp+68h+arg_18]
0x180002c3a  add     rsp, 68h
0x180002c3e  jmp     short $+2
0x180002c40  jmp     rax
```
