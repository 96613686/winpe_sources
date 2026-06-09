# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000a60c`
- end: `0x18000a685`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a68b`
- `0x18000a824`

## callees

- `0x180007cd0`
- `0x18000a60c`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a60c  mov     [rsp+arg_0], rcx
0x18000a611  mov     [rsp+arg_8], rdx
0x18000a616  mov     [rsp+arg_10], r8
0x18000a61b  mov     [rsp+arg_18], r9
0x18000a620  sub     rsp, 68h
0x18000a624  movdqa  [rsp+68h+var_48], xmm0
0x18000a62a  movdqa  [rsp+68h+var_38], xmm1
0x18000a630  movdqa  [rsp+68h+var_28], xmm2
0x18000a636  movdqa  [rsp+68h+var_18], xmm3
0x18000a63c  mov     rdx, rax
0x18000a63f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x18000a646  call    __delayLoadHelper2
0x18000a64b  movdqa  xmm0, [rsp+68h+var_48]
0x18000a651  movdqa  xmm1, [rsp+68h+var_38]
0x18000a657  movdqa  xmm2, [rsp+68h+var_28]
0x18000a65d  movdqa  xmm3, [rsp+68h+var_18]
0x18000a663  mov     rcx, [rsp+68h+arg_0]
0x18000a668  mov     rdx, [rsp+68h+arg_8]
0x18000a66d  mov     r8, [rsp+68h+arg_10]
0x18000a675  mov     r9, [rsp+68h+arg_18]
0x18000a67d  add     rsp, 68h
0x18000a681  jmp     short $+2
0x18000a683  jmp     rax
```
