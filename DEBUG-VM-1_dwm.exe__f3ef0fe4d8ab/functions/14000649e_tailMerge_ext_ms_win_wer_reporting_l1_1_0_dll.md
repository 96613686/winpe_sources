# __tailMerge_ext_ms_win_wer_reporting_l1_1_0_dll

- ea: `0x14000649e`
- end: `0x140006517`
- name: `__tailMerge_ext_ms_win_wer_reporting_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000651d`
- `0x140006584`
- `0x140006596`
- `0x1400065a8`
- `0x1400065ba`

## callees

- `0x140003b60`
- `0x14000649e`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_wer_reporting_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_wer_reporting_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000649e  mov     [rsp+arg_0], rcx
0x1400064a3  mov     [rsp+arg_8], rdx
0x1400064a8  mov     [rsp+arg_10], r8
0x1400064ad  mov     [rsp+arg_18], r9
0x1400064b2  sub     rsp, 68h
0x1400064b6  movdqa  [rsp+68h+var_48], xmm0
0x1400064bc  movdqa  [rsp+68h+var_38], xmm1
0x1400064c2  movdqa  [rsp+68h+var_28], xmm2
0x1400064c8  movdqa  [rsp+68h+var_18], xmm3
0x1400064ce  mov     rdx, rax
0x1400064d1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_wer_reporting_l1_1_0_dll
0x1400064d8  call    __delayLoadHelper2
0x1400064dd  movdqa  xmm0, [rsp+68h+var_48]
0x1400064e3  movdqa  xmm1, [rsp+68h+var_38]
0x1400064e9  movdqa  xmm2, [rsp+68h+var_28]
0x1400064ef  movdqa  xmm3, [rsp+68h+var_18]
0x1400064f5  mov     rcx, [rsp+68h+arg_0]
0x1400064fa  mov     rdx, [rsp+68h+arg_8]
0x1400064ff  mov     r8, [rsp+68h+arg_10]
0x140006507  mov     r9, [rsp+68h+arg_18]
0x14000650f  add     rsp, 68h
0x140006513  jmp     short $+2
0x140006515  jmp     rax
```
