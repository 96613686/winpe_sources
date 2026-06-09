# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x14000440f`
- end: `0x140004488`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000448e`

## callees

- `0x14000440f`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000440f  mov     [rsp+arg_0], rcx
0x140004414  mov     [rsp+arg_8], rdx
0x140004419  mov     [rsp+arg_10], r8
0x14000441e  mov     [rsp+arg_18], r9
0x140004423  sub     rsp, 68h
0x140004427  movdqa  [rsp+68h+var_48], xmm0
0x14000442d  movdqa  [rsp+68h+var_38], xmm1
0x140004433  movdqa  [rsp+68h+var_28], xmm2
0x140004439  movdqa  [rsp+68h+var_18], xmm3
0x14000443f  mov     rdx, rax
0x140004442  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x140004449  call    __delayLoadHelper2
0x14000444e  movdqa  xmm0, [rsp+68h+var_48]
0x140004454  movdqa  xmm1, [rsp+68h+var_38]
0x14000445a  movdqa  xmm2, [rsp+68h+var_28]
0x140004460  movdqa  xmm3, [rsp+68h+var_18]
0x140004466  mov     rcx, [rsp+68h+arg_0]
0x14000446b  mov     rdx, [rsp+68h+arg_8]
0x140004470  mov     r8, [rsp+68h+arg_10]
0x140004478  mov     r9, [rsp+68h+arg_18]
0x140004480  add     rsp, 68h
0x140004484  jmp     short $+2
0x140004486  jmp     rax
```
