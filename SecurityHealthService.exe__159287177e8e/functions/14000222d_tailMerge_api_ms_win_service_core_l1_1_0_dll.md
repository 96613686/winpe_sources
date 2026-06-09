# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x14000222d`
- end: `0x1400022a6`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1400022ac`
- `0x1400022be`
- `0x14000235b`

## callees

- `0x14000222d`
- `0x140011350`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000222d  mov     [rsp+arg_0], rcx
0x140002232  mov     [rsp+arg_8], rdx
0x140002237  mov     [rsp+arg_10], r8
0x14000223c  mov     [rsp+arg_18], r9
0x140002241  sub     rsp, 68h
0x140002245  movdqa  [rsp+68h+var_48], xmm0
0x14000224b  movdqa  [rsp+68h+var_38], xmm1
0x140002251  movdqa  [rsp+68h+var_28], xmm2
0x140002257  movdqa  [rsp+68h+var_18], xmm3
0x14000225d  mov     rdx, rax
0x140002260  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x140002267  call    __delayLoadHelper2
0x14000226c  movdqa  xmm0, [rsp+68h+var_48]
0x140002272  movdqa  xmm1, [rsp+68h+var_38]
0x140002278  movdqa  xmm2, [rsp+68h+var_28]
0x14000227e  movdqa  xmm3, [rsp+68h+var_18]
0x140002284  mov     rcx, [rsp+68h+arg_0]
0x140002289  mov     rdx, [rsp+68h+arg_8]
0x14000228e  mov     r8, [rsp+68h+arg_10]
0x140002296  mov     r9, [rsp+68h+arg_18]
0x14000229e  add     rsp, 68h
0x1400022a2  jmp     short $+2
0x1400022a4  jmp     rax
```
