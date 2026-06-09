# __tailMerge_api_ms_win_security_provider_l1_1_0_dll

- ea: `0x18000374d`
- end: `0x1800037c6`
- name: `__tailMerge_api_ms_win_security_provider_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800037cc`

## callees

- `0x18000374d`
- `0x180010cc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_provider_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000374d  mov     [rsp+arg_0], rcx
0x180003752  mov     [rsp+arg_8], rdx
0x180003757  mov     [rsp+arg_10], r8
0x18000375c  mov     [rsp+arg_18], r9
0x180003761  sub     rsp, 68h
0x180003765  movdqa  [rsp+68h+var_48], xmm0
0x18000376b  movdqa  [rsp+68h+var_38], xmm1
0x180003771  movdqa  [rsp+68h+var_28], xmm2
0x180003777  movdqa  [rsp+68h+var_18], xmm3
0x18000377d  mov     rdx, rax
0x180003780  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll
0x180003787  call    __delayLoadHelper2
0x18000378c  movdqa  xmm0, [rsp+68h+var_48]
0x180003792  movdqa  xmm1, [rsp+68h+var_38]
0x180003798  movdqa  xmm2, [rsp+68h+var_28]
0x18000379e  movdqa  xmm3, [rsp+68h+var_18]
0x1800037a4  mov     rcx, [rsp+68h+arg_0]
0x1800037a9  mov     rdx, [rsp+68h+arg_8]
0x1800037ae  mov     r8, [rsp+68h+arg_10]
0x1800037b6  mov     r9, [rsp+68h+arg_18]
0x1800037be  add     rsp, 68h
0x1800037c2  jmp     short $+2
0x1800037c4  jmp     rax
```
