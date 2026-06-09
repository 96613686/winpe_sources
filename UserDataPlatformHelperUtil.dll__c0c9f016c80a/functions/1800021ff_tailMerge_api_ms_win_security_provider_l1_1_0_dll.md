# __tailMerge_api_ms_win_security_provider_l1_1_0_dll

- ea: `0x1800021ff`
- end: `0x180002278`
- name: `__tailMerge_api_ms_win_security_provider_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000227e`
- `0x180002290`

## callees

- `0x1800021ff`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_provider_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800021ff  mov     [rsp+arg_0], rcx
0x180002204  mov     [rsp+arg_8], rdx
0x180002209  mov     [rsp+arg_10], r8
0x18000220e  mov     [rsp+arg_18], r9
0x180002213  sub     rsp, 68h
0x180002217  movdqa  [rsp+68h+var_48], xmm0
0x18000221d  movdqa  [rsp+68h+var_38], xmm1
0x180002223  movdqa  [rsp+68h+var_28], xmm2
0x180002229  movdqa  [rsp+68h+var_18], xmm3
0x18000222f  mov     rdx, rax
0x180002232  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll
0x180002239  call    __delayLoadHelper2
0x18000223e  movdqa  xmm0, [rsp+68h+var_48]
0x180002244  movdqa  xmm1, [rsp+68h+var_38]
0x18000224a  movdqa  xmm2, [rsp+68h+var_28]
0x180002250  movdqa  xmm3, [rsp+68h+var_18]
0x180002256  mov     rcx, [rsp+68h+arg_0]
0x18000225b  mov     rdx, [rsp+68h+arg_8]
0x180002260  mov     r8, [rsp+68h+arg_10]
0x180002268  mov     r9, [rsp+68h+arg_18]
0x180002270  add     rsp, 68h
0x180002274  jmp     short $+2
0x180002276  jmp     rax
```
