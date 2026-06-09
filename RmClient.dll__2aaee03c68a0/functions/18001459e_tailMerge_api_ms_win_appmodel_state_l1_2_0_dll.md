# __tailMerge_api_ms_win_appmodel_state_l1_2_0_dll

- ea: `0x18001459e`
- end: `0x180014617`
- name: `__tailMerge_api_ms_win_appmodel_state_l1_2_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001461d`
- `0x18001462f`
- `0x180014641`

## callees

- `0x18000f260`
- `0x18001459e`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_state_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_state_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001459e  mov     [rsp+arg_0], rcx
0x1800145a3  mov     [rsp+arg_8], rdx
0x1800145a8  mov     [rsp+arg_10], r8
0x1800145ad  mov     [rsp+arg_18], r9
0x1800145b2  sub     rsp, 68h
0x1800145b6  movdqa  [rsp+68h+var_48], xmm0
0x1800145bc  movdqa  [rsp+68h+var_38], xmm1
0x1800145c2  movdqa  [rsp+68h+var_28], xmm2
0x1800145c8  movdqa  [rsp+68h+var_18], xmm3
0x1800145ce  mov     rdx, rax
0x1800145d1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_state_l1_2_0_dll
0x1800145d8  call    __delayLoadHelper2
0x1800145dd  movdqa  xmm0, [rsp+68h+var_48]
0x1800145e3  movdqa  xmm1, [rsp+68h+var_38]
0x1800145e9  movdqa  xmm2, [rsp+68h+var_28]
0x1800145ef  movdqa  xmm3, [rsp+68h+var_18]
0x1800145f5  mov     rcx, [rsp+68h+arg_0]
0x1800145fa  mov     rdx, [rsp+68h+arg_8]
0x1800145ff  mov     r8, [rsp+68h+arg_10]
0x180014607  mov     r9, [rsp+68h+arg_18]
0x18001460f  add     rsp, 68h
0x180014613  jmp     short $+2
0x180014615  jmp     rax
```
