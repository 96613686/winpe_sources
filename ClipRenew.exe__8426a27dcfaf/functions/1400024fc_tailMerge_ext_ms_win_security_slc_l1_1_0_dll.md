# __tailMerge_ext_ms_win_security_slc_l1_1_0_dll

- ea: `0x1400024fc`
- end: `0x140002575`
- name: `__tailMerge_ext_ms_win_security_slc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000257b`
- `0x14000258d`
- `0x14000259f`

## callees

- `0x1400024fc`
- `0x140013380`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_slc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_slc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400024fc  mov     [rsp+arg_0], rcx
0x140002501  mov     [rsp+arg_8], rdx
0x140002506  mov     [rsp+arg_10], r8
0x14000250b  mov     [rsp+arg_18], r9
0x140002510  sub     rsp, 68h
0x140002514  movdqa  [rsp+68h+var_48], xmm0
0x14000251a  movdqa  [rsp+68h+var_38], xmm1
0x140002520  movdqa  [rsp+68h+var_28], xmm2
0x140002526  movdqa  [rsp+68h+var_18], xmm3
0x14000252c  mov     rdx, rax
0x14000252f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_slc_l1_1_0_dll
0x140002536  call    __delayLoadHelper2
0x14000253b  movdqa  xmm0, [rsp+68h+var_48]
0x140002541  movdqa  xmm1, [rsp+68h+var_38]
0x140002547  movdqa  xmm2, [rsp+68h+var_28]
0x14000254d  movdqa  xmm3, [rsp+68h+var_18]
0x140002553  mov     rcx, [rsp+68h+arg_0]
0x140002558  mov     rdx, [rsp+68h+arg_8]
0x14000255d  mov     r8, [rsp+68h+arg_10]
0x140002565  mov     r9, [rsp+68h+arg_18]
0x14000256d  add     rsp, 68h
0x140002571  jmp     short $+2
0x140002573  jmp     rax
```
