# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x180002346`
- end: `0x1800023bf`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800023c5`
- `0x1800023d7`
- `0x1800023e9`

## callees

- `0x180002346`
- `0x180011cc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002346  mov     [rsp+arg_0], rcx
0x18000234b  mov     [rsp+arg_8], rdx
0x180002350  mov     [rsp+arg_10], r8
0x180002355  mov     [rsp+arg_18], r9
0x18000235a  sub     rsp, 68h
0x18000235e  movdqa  [rsp+68h+var_48], xmm0
0x180002364  movdqa  [rsp+68h+var_38], xmm1
0x18000236a  movdqa  [rsp+68h+var_28], xmm2
0x180002370  movdqa  [rsp+68h+var_18], xmm3
0x180002376  mov     rdx, rax
0x180002379  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x180002380  call    __delayLoadHelper2
0x180002385  movdqa  xmm0, [rsp+68h+var_48]
0x18000238b  movdqa  xmm1, [rsp+68h+var_38]
0x180002391  movdqa  xmm2, [rsp+68h+var_28]
0x180002397  movdqa  xmm3, [rsp+68h+var_18]
0x18000239d  mov     rcx, [rsp+68h+arg_0]
0x1800023a2  mov     rdx, [rsp+68h+arg_8]
0x1800023a7  mov     r8, [rsp+68h+arg_10]
0x1800023af  mov     r9, [rsp+68h+arg_18]
0x1800023b7  add     rsp, 68h
0x1800023bb  jmp     short $+2
0x1800023bd  jmp     rax
```
