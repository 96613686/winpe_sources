# __tailMerge_ext_ms_win_rpc_firewallportuse_l1_1_0_dll

- ea: `0x1800063f6`
- end: `0x18000646f`
- name: `__tailMerge_ext_ms_win_rpc_firewallportuse_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006475`
- `0x180006487`

## callees

- `0x1800063f6`
- `0x18000a860`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rpc_firewallportuse_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rpc_firewallportuse_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800063f6  mov     [rsp+arg_0], rcx
0x1800063fb  mov     [rsp+arg_8], rdx
0x180006400  mov     [rsp+arg_10], r8
0x180006405  mov     [rsp+arg_18], r9
0x18000640a  sub     rsp, 68h
0x18000640e  movdqa  [rsp+68h+var_48], xmm0
0x180006414  movdqa  [rsp+68h+var_38], xmm1
0x18000641a  movdqa  [rsp+68h+var_28], xmm2
0x180006420  movdqa  [rsp+68h+var_18], xmm3
0x180006426  mov     rdx, rax
0x180006429  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rpc_firewallportuse_l1_1_0_dll
0x180006430  call    __delayLoadHelper2
0x180006435  movdqa  xmm0, [rsp+68h+var_48]
0x18000643b  movdqa  xmm1, [rsp+68h+var_38]
0x180006441  movdqa  xmm2, [rsp+68h+var_28]
0x180006447  movdqa  xmm3, [rsp+68h+var_18]
0x18000644d  mov     rcx, [rsp+68h+arg_0]
0x180006452  mov     rdx, [rsp+68h+arg_8]
0x180006457  mov     r8, [rsp+68h+arg_10]
0x18000645f  mov     r9, [rsp+68h+arg_18]
0x180006467  add     rsp, 68h
0x18000646b  jmp     short $+2
0x18000646d  jmp     rax
```
