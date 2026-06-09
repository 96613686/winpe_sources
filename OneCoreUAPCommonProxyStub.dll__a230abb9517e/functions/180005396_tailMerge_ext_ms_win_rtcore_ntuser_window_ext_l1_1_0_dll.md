# __tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll

- ea: `0x180005396`
- end: `0x18000540f`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005415`
- `0x180005427`

## callees

- `0x180002420`
- `0x180005396`

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
0x180005396  mov     [rsp+arg_0], rcx
0x18000539b  mov     [rsp+arg_8], rdx
0x1800053a0  mov     [rsp+arg_10], r8
0x1800053a5  mov     [rsp+arg_18], r9
0x1800053aa  sub     rsp, 68h
0x1800053ae  movdqa  [rsp+68h+var_48], xmm0
0x1800053b4  movdqa  [rsp+68h+var_38], xmm1
0x1800053ba  movdqa  [rsp+68h+var_28], xmm2
0x1800053c0  movdqa  [rsp+68h+var_18], xmm3
0x1800053c6  mov     rdx, rax
0x1800053c9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_window_ext_l1_1_0_dll
0x1800053d0  call    __delayLoadHelper2
0x1800053d5  movdqa  xmm0, [rsp+68h+var_48]
0x1800053db  movdqa  xmm1, [rsp+68h+var_38]
0x1800053e1  movdqa  xmm2, [rsp+68h+var_28]
0x1800053e7  movdqa  xmm3, [rsp+68h+var_18]
0x1800053ed  mov     rcx, [rsp+68h+arg_0]
0x1800053f2  mov     rdx, [rsp+68h+arg_8]
0x1800053f7  mov     r8, [rsp+68h+arg_10]
0x1800053ff  mov     r9, [rsp+68h+arg_18]
0x180005407  add     rsp, 68h
0x18000540b  jmp     short $+2
0x18000540d  jmp     rax
```
