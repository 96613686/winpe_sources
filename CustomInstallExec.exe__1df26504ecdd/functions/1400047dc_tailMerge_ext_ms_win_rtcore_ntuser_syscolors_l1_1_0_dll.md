# __tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll

- ea: `0x1400047dc`
- end: `0x140004855`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000485b`

## callees

- `0x1400047dc`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400047dc  mov     [rsp+arg_0], rcx
0x1400047e1  mov     [rsp+arg_8], rdx
0x1400047e6  mov     [rsp+arg_10], r8
0x1400047eb  mov     [rsp+arg_18], r9
0x1400047f0  sub     rsp, 68h
0x1400047f4  movdqa  [rsp+68h+var_48], xmm0
0x1400047fa  movdqa  [rsp+68h+var_38], xmm1
0x140004800  movdqa  [rsp+68h+var_28], xmm2
0x140004806  movdqa  [rsp+68h+var_18], xmm3
0x14000480c  mov     rdx, rax
0x14000480f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_syscolors_l1_1_0_dll
0x140004816  call    __delayLoadHelper2
0x14000481b  movdqa  xmm0, [rsp+68h+var_48]
0x140004821  movdqa  xmm1, [rsp+68h+var_38]
0x140004827  movdqa  xmm2, [rsp+68h+var_28]
0x14000482d  movdqa  xmm3, [rsp+68h+var_18]
0x140004833  mov     rcx, [rsp+68h+arg_0]
0x140004838  mov     rdx, [rsp+68h+arg_8]
0x14000483d  mov     r8, [rsp+68h+arg_10]
0x140004845  mov     r9, [rsp+68h+arg_18]
0x14000484d  add     rsp, 68h
0x140004851  jmp     short $+2
0x140004853  jmp     rax
```
