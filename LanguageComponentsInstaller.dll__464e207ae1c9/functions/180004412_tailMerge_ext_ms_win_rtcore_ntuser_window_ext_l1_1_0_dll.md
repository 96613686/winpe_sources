# __tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll

- ea: `0x180004412`
- end: `0x18000448b`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004491`

## callees

- `0x180004412`
- `0x180027c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004412  mov     [rsp+arg_0], rcx
0x180004417  mov     [rsp+arg_8], rdx
0x18000441c  mov     [rsp+arg_10], r8
0x180004421  mov     [rsp+arg_18], r9
0x180004426  sub     rsp, 68h
0x18000442a  movdqa  [rsp+68h+var_48], xmm0
0x180004430  movdqa  [rsp+68h+var_38], xmm1
0x180004436  movdqa  [rsp+68h+var_28], xmm2
0x18000443c  movdqa  [rsp+68h+var_18], xmm3
0x180004442  mov     rdx, rax
0x180004445  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll
0x18000444c  call    __delayLoadHelper2
0x180004451  movdqa  xmm0, [rsp+68h+var_48]
0x180004457  movdqa  xmm1, [rsp+68h+var_38]
0x18000445d  movdqa  xmm2, [rsp+68h+var_28]
0x180004463  movdqa  xmm3, [rsp+68h+var_18]
0x180004469  mov     rcx, [rsp+68h+arg_0]
0x18000446e  mov     rdx, [rsp+68h+arg_8]
0x180004473  mov     r8, [rsp+68h+arg_10]
0x18000447b  mov     r9, [rsp+68h+arg_18]
0x180004483  add     rsp, 68h
0x180004487  jmp     short $+2
0x180004489  jmp     rax
```
