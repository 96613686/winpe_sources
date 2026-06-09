# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x180002977`
- end: `0x1800029f0`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800029f6`
- `0x180002a08`

## callees

- `0x180002977`
- `0x180013920`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002977  mov     [rsp+arg_0], rcx
0x18000297c  mov     [rsp+arg_8], rdx
0x180002981  mov     [rsp+arg_10], r8
0x180002986  mov     [rsp+arg_18], r9
0x18000298b  sub     rsp, 68h
0x18000298f  movdqa  [rsp+68h+var_48], xmm0
0x180002995  movdqa  [rsp+68h+var_38], xmm1
0x18000299b  movdqa  [rsp+68h+var_28], xmm2
0x1800029a1  movdqa  [rsp+68h+var_18], xmm3
0x1800029a7  mov     rdx, rax
0x1800029aa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x1800029b1  call    __delayLoadHelper2
0x1800029b6  movdqa  xmm0, [rsp+68h+var_48]
0x1800029bc  movdqa  xmm1, [rsp+68h+var_38]
0x1800029c2  movdqa  xmm2, [rsp+68h+var_28]
0x1800029c8  movdqa  xmm3, [rsp+68h+var_18]
0x1800029ce  mov     rcx, [rsp+68h+arg_0]
0x1800029d3  mov     rdx, [rsp+68h+arg_8]
0x1800029d8  mov     r8, [rsp+68h+arg_10]
0x1800029e0  mov     r9, [rsp+68h+arg_18]
0x1800029e8  add     rsp, 68h
0x1800029ec  jmp     short $+2
0x1800029ee  jmp     rax
```
