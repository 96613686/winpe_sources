# __tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll

- ea: `0x180001dea`
- end: `0x180001e63`
- name: `__tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e69`
- `0x180001e7b`

## callees

- `0x180001dea`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_accesshlpr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001dea  mov     [rsp+arg_0], rcx
0x180001def  mov     [rsp+arg_8], rdx
0x180001df4  mov     [rsp+arg_10], r8
0x180001df9  mov     [rsp+arg_18], r9
0x180001dfe  sub     rsp, 68h
0x180001e02  movdqa  [rsp+68h+var_48], xmm0
0x180001e08  movdqa  [rsp+68h+var_38], xmm1
0x180001e0e  movdqa  [rsp+68h+var_28], xmm2
0x180001e14  movdqa  [rsp+68h+var_18], xmm3
0x180001e1a  mov     rdx, rax
0x180001e1d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_accesshlpr_l1_1_0_dll
0x180001e24  call    __delayLoadHelper2
0x180001e29  movdqa  xmm0, [rsp+68h+var_48]
0x180001e2f  movdqa  xmm1, [rsp+68h+var_38]
0x180001e35  movdqa  xmm2, [rsp+68h+var_28]
0x180001e3b  movdqa  xmm3, [rsp+68h+var_18]
0x180001e41  mov     rcx, [rsp+68h+arg_0]
0x180001e46  mov     rdx, [rsp+68h+arg_8]
0x180001e4b  mov     r8, [rsp+68h+arg_10]
0x180001e53  mov     r9, [rsp+68h+arg_18]
0x180001e5b  add     rsp, 68h
0x180001e5f  jmp     short $+2
0x180001e61  jmp     rax
```
