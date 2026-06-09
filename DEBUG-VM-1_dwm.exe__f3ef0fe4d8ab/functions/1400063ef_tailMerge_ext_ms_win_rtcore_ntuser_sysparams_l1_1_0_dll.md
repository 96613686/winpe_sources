# __tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll

- ea: `0x1400063ef`
- end: `0x140006468`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000646e`
- `0x140006480`
- `0x140006492`

## callees

- `0x140003b60`
- `0x1400063ef`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400063ef  mov     [rsp+arg_0], rcx
0x1400063f4  mov     [rsp+arg_8], rdx
0x1400063f9  mov     [rsp+arg_10], r8
0x1400063fe  mov     [rsp+arg_18], r9
0x140006403  sub     rsp, 68h
0x140006407  movdqa  [rsp+68h+var_48], xmm0
0x14000640d  movdqa  [rsp+68h+var_38], xmm1
0x140006413  movdqa  [rsp+68h+var_28], xmm2
0x140006419  movdqa  [rsp+68h+var_18], xmm3
0x14000641f  mov     rdx, rax
0x140006422  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll
0x140006429  call    __delayLoadHelper2
0x14000642e  movdqa  xmm0, [rsp+68h+var_48]
0x140006434  movdqa  xmm1, [rsp+68h+var_38]
0x14000643a  movdqa  xmm2, [rsp+68h+var_28]
0x140006440  movdqa  xmm3, [rsp+68h+var_18]
0x140006446  mov     rcx, [rsp+68h+arg_0]
0x14000644b  mov     rdx, [rsp+68h+arg_8]
0x140006450  mov     r8, [rsp+68h+arg_10]
0x140006458  mov     r9, [rsp+68h+arg_18]
0x140006460  add     rsp, 68h
0x140006464  jmp     short $+2
0x140006466  jmp     rax
```
