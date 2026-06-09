# __tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll

- ea: `0x18000219e`
- end: `0x180002217`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000221d`
- `0x18000222f`

## callees

- `0x18000219e`
- `0x180020e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000219e  mov     [rsp+arg_0], rcx
0x1800021a3  mov     [rsp+arg_8], rdx
0x1800021a8  mov     [rsp+arg_10], r8
0x1800021ad  mov     [rsp+arg_18], r9
0x1800021b2  sub     rsp, 68h
0x1800021b6  movdqa  [rsp+68h+var_48], xmm0
0x1800021bc  movdqa  [rsp+68h+var_38], xmm1
0x1800021c2  movdqa  [rsp+68h+var_28], xmm2
0x1800021c8  movdqa  [rsp+68h+var_18], xmm3
0x1800021ce  mov     rdx, rax
0x1800021d1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll
0x1800021d8  call    __delayLoadHelper2
0x1800021dd  movdqa  xmm0, [rsp+68h+var_48]
0x1800021e3  movdqa  xmm1, [rsp+68h+var_38]
0x1800021e9  movdqa  xmm2, [rsp+68h+var_28]
0x1800021ef  movdqa  xmm3, [rsp+68h+var_18]
0x1800021f5  mov     rcx, [rsp+68h+arg_0]
0x1800021fa  mov     rdx, [rsp+68h+arg_8]
0x1800021ff  mov     r8, [rsp+68h+arg_10]
0x180002207  mov     r9, [rsp+68h+arg_18]
0x18000220f  add     rsp, 68h
0x180002213  jmp     short $+2
0x180002215  jmp     rax
```
