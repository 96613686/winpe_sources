# __tailMerge_ext_ms_win_ntuser_gui_l1_1_1_dll

- ea: `0x140004751`
- end: `0x1400047ca`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400047d0`

## callees

- `0x140004751`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_gui_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004751  mov     [rsp+arg_0], rcx
0x140004756  mov     [rsp+arg_8], rdx
0x14000475b  mov     [rsp+arg_10], r8
0x140004760  mov     [rsp+arg_18], r9
0x140004765  sub     rsp, 68h
0x140004769  movdqa  [rsp+68h+var_48], xmm0
0x14000476f  movdqa  [rsp+68h+var_38], xmm1
0x140004775  movdqa  [rsp+68h+var_28], xmm2
0x14000477b  movdqa  [rsp+68h+var_18], xmm3
0x140004781  mov     rdx, rax
0x140004784  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_1_dll
0x14000478b  call    __delayLoadHelper2
0x140004790  movdqa  xmm0, [rsp+68h+var_48]
0x140004796  movdqa  xmm1, [rsp+68h+var_38]
0x14000479c  movdqa  xmm2, [rsp+68h+var_28]
0x1400047a2  movdqa  xmm3, [rsp+68h+var_18]
0x1400047a8  mov     rcx, [rsp+68h+arg_0]
0x1400047ad  mov     rdx, [rsp+68h+arg_8]
0x1400047b2  mov     r8, [rsp+68h+arg_10]
0x1400047ba  mov     r9, [rsp+68h+arg_18]
0x1400047c2  add     rsp, 68h
0x1400047c6  jmp     short $+2
0x1400047c8  jmp     rax
```
