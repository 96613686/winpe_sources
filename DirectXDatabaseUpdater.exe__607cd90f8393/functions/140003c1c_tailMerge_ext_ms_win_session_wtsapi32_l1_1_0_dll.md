# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x140003c1c`
- end: `0x140003c95`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003c9b`
- `0x140003d04`
- `0x140003d16`

## callees

- `0x140003c1c`
- `0x1400183b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003c1c  mov     [rsp+arg_0], rcx
0x140003c21  mov     [rsp+arg_8], rdx
0x140003c26  mov     [rsp+arg_10], r8
0x140003c2b  mov     [rsp+arg_18], r9
0x140003c30  sub     rsp, 68h
0x140003c34  movdqa  [rsp+68h+var_48], xmm0
0x140003c3a  movdqa  [rsp+68h+var_38], xmm1
0x140003c40  movdqa  [rsp+68h+var_28], xmm2
0x140003c46  movdqa  [rsp+68h+var_18], xmm3
0x140003c4c  mov     rdx, rax
0x140003c4f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x140003c56  call    __delayLoadHelper2
0x140003c5b  movdqa  xmm0, [rsp+68h+var_48]
0x140003c61  movdqa  xmm1, [rsp+68h+var_38]
0x140003c67  movdqa  xmm2, [rsp+68h+var_28]
0x140003c6d  movdqa  xmm3, [rsp+68h+var_18]
0x140003c73  mov     rcx, [rsp+68h+arg_0]
0x140003c78  mov     rdx, [rsp+68h+arg_8]
0x140003c7d  mov     r8, [rsp+68h+arg_10]
0x140003c85  mov     r9, [rsp+68h+arg_18]
0x140003c8d  add     rsp, 68h
0x140003c91  jmp     short $+2
0x140003c93  jmp     rax
```
