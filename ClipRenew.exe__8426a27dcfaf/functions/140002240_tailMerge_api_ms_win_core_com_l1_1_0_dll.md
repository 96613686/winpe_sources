# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x140002240`
- end: `0x1400022b9`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400022bf`
- `0x1400022d1`
- `0x14000236e`

## callees

- `0x140002240`
- `0x140013380`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002240  mov     [rsp+arg_0], rcx
0x140002245  mov     [rsp+arg_8], rdx
0x14000224a  mov     [rsp+arg_10], r8
0x14000224f  mov     [rsp+arg_18], r9
0x140002254  sub     rsp, 68h
0x140002258  movdqa  [rsp+68h+var_48], xmm0
0x14000225e  movdqa  [rsp+68h+var_38], xmm1
0x140002264  movdqa  [rsp+68h+var_28], xmm2
0x14000226a  movdqa  [rsp+68h+var_18], xmm3
0x140002270  mov     rdx, rax
0x140002273  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x14000227a  call    __delayLoadHelper2
0x14000227f  movdqa  xmm0, [rsp+68h+var_48]
0x140002285  movdqa  xmm1, [rsp+68h+var_38]
0x14000228b  movdqa  xmm2, [rsp+68h+var_28]
0x140002291  movdqa  xmm3, [rsp+68h+var_18]
0x140002297  mov     rcx, [rsp+68h+arg_0]
0x14000229c  mov     rdx, [rsp+68h+arg_8]
0x1400022a1  mov     r8, [rsp+68h+arg_10]
0x1400022a9  mov     r9, [rsp+68h+arg_18]
0x1400022b1  add     rsp, 68h
0x1400022b5  jmp     short $+2
0x1400022b7  jmp     rax
```
