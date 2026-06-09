# __tailMerge_api_ms_win_core_winrt_error_l1_1_0_dll

- ea: `0x18001432a`
- end: `0x1800143a3`
- name: `__tailMerge_api_ms_win_core_winrt_error_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800143a9`
- `0x1800143bb`
- `0x180014929`
- `0x18001493b`

## callees

- `0x18000f260`
- `0x18001432a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_error_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_error_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001432a  mov     [rsp+arg_0], rcx
0x18001432f  mov     [rsp+arg_8], rdx
0x180014334  mov     [rsp+arg_10], r8
0x180014339  mov     [rsp+arg_18], r9
0x18001433e  sub     rsp, 68h
0x180014342  movdqa  [rsp+68h+var_48], xmm0
0x180014348  movdqa  [rsp+68h+var_38], xmm1
0x18001434e  movdqa  [rsp+68h+var_28], xmm2
0x180014354  movdqa  [rsp+68h+var_18], xmm3
0x18001435a  mov     rdx, rax
0x18001435d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_error_l1_1_0_dll
0x180014364  call    __delayLoadHelper2
0x180014369  movdqa  xmm0, [rsp+68h+var_48]
0x18001436f  movdqa  xmm1, [rsp+68h+var_38]
0x180014375  movdqa  xmm2, [rsp+68h+var_28]
0x18001437b  movdqa  xmm3, [rsp+68h+var_18]
0x180014381  mov     rcx, [rsp+68h+arg_0]
0x180014386  mov     rdx, [rsp+68h+arg_8]
0x18001438b  mov     r8, [rsp+68h+arg_10]
0x180014393  mov     r9, [rsp+68h+arg_18]
0x18001439b  add     rsp, 68h
0x18001439f  jmp     short $+2
0x1800143a1  jmp     rax
```
