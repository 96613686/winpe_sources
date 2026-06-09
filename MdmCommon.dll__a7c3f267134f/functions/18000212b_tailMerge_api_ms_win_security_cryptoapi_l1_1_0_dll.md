# __tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll

- ea: `0x18000212b`
- end: `0x1800021a4`
- name: `__tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800021aa`
- `0x1800021bc`
- `0x1800021ce`
- `0x18000226b`
- `0x18000227d`
- `0x18000228f`
- `0x1800022a1`
- `0x1800022b3`
- `0x1800022c5`
- `0x1800022d7`

## callees

- `0x18000212b`
- `0x18001da40`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_cryptoapi_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000212b  mov     [rsp+arg_0], rcx
0x180002130  mov     [rsp+arg_8], rdx
0x180002135  mov     [rsp+arg_10], r8
0x18000213a  mov     [rsp+arg_18], r9
0x18000213f  sub     rsp, 68h
0x180002143  movdqa  [rsp+68h+var_48], xmm0
0x180002149  movdqa  [rsp+68h+var_38], xmm1
0x18000214f  movdqa  [rsp+68h+var_28], xmm2
0x180002155  movdqa  [rsp+68h+var_18], xmm3
0x18000215b  mov     rdx, rax
0x18000215e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_cryptoapi_l1_1_0_dll
0x180002165  call    __delayLoadHelper2
0x18000216a  movdqa  xmm0, [rsp+68h+var_48]
0x180002170  movdqa  xmm1, [rsp+68h+var_38]
0x180002176  movdqa  xmm2, [rsp+68h+var_28]
0x18000217c  movdqa  xmm3, [rsp+68h+var_18]
0x180002182  mov     rcx, [rsp+68h+arg_0]
0x180002187  mov     rdx, [rsp+68h+arg_8]
0x18000218c  mov     r8, [rsp+68h+arg_10]
0x180002194  mov     r9, [rsp+68h+arg_18]
0x18000219c  add     rsp, 68h
0x1800021a0  jmp     short $+2
0x1800021a2  jmp     rax
```
