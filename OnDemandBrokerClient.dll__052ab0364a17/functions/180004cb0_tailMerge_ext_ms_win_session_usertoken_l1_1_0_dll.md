# __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll

- ea: `0x180004cb0`
- end: `0x180004d29`
- name: `__tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d2f`

## callees

- `0x180004cb0`
- `0x180006400`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004cb0  mov     [rsp+arg_0], rcx
0x180004cb5  mov     [rsp+arg_8], rdx
0x180004cba  mov     [rsp+arg_10], r8
0x180004cbf  mov     [rsp+arg_18], r9
0x180004cc4  sub     rsp, 68h
0x180004cc8  movdqa  [rsp+68h+var_48], xmm0
0x180004cce  movdqa  [rsp+68h+var_38], xmm1
0x180004cd4  movdqa  [rsp+68h+var_28], xmm2
0x180004cda  movdqa  [rsp+68h+var_18], xmm3
0x180004ce0  mov     rdx, rax
0x180004ce3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll
0x180004cea  call    __delayLoadHelper2
0x180004cef  movdqa  xmm0, [rsp+68h+var_48]
0x180004cf5  movdqa  xmm1, [rsp+68h+var_38]
0x180004cfb  movdqa  xmm2, [rsp+68h+var_28]
0x180004d01  movdqa  xmm3, [rsp+68h+var_18]
0x180004d07  mov     rcx, [rsp+68h+arg_0]
0x180004d0c  mov     rdx, [rsp+68h+arg_8]
0x180004d11  mov     r8, [rsp+68h+arg_10]
0x180004d19  mov     r9, [rsp+68h+arg_18]
0x180004d21  add     rsp, 68h
0x180004d25  jmp     short $+2
0x180004d27  jmp     rax
```
