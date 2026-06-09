# __tailMerge_api_ms_win_security_logon_l1_1_1_dll

- ea: `0x1400042b8`
- end: `0x140004331`
- name: `__tailMerge_api_ms_win_security_logon_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004337`

## callees

- `0x1400042b8`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_logon_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_logon_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400042b8  mov     [rsp+arg_0], rcx
0x1400042bd  mov     [rsp+arg_8], rdx
0x1400042c2  mov     [rsp+arg_10], r8
0x1400042c7  mov     [rsp+arg_18], r9
0x1400042cc  sub     rsp, 68h
0x1400042d0  movdqa  [rsp+68h+var_48], xmm0
0x1400042d6  movdqa  [rsp+68h+var_38], xmm1
0x1400042dc  movdqa  [rsp+68h+var_28], xmm2
0x1400042e2  movdqa  [rsp+68h+var_18], xmm3
0x1400042e8  mov     rdx, rax
0x1400042eb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_logon_l1_1_1_dll
0x1400042f2  call    __delayLoadHelper2
0x1400042f7  movdqa  xmm0, [rsp+68h+var_48]
0x1400042fd  movdqa  xmm1, [rsp+68h+var_38]
0x140004303  movdqa  xmm2, [rsp+68h+var_28]
0x140004309  movdqa  xmm3, [rsp+68h+var_18]
0x14000430f  mov     rcx, [rsp+68h+arg_0]
0x140004314  mov     rdx, [rsp+68h+arg_8]
0x140004319  mov     r8, [rsp+68h+arg_10]
0x140004321  mov     r9, [rsp+68h+arg_18]
0x140004329  add     rsp, 68h
0x14000432d  jmp     short $+2
0x14000432f  jmp     rax
```
