# __tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll

- ea: `0x1400042b1`
- end: `0x14000432a`
- name: `__tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004330`
- `0x140004342`
- `0x140004354`

## callees

- `0x1400042b1`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_keyboard_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400042b1  mov     [rsp+arg_0], rcx
0x1400042b6  mov     [rsp+arg_8], rdx
0x1400042bb  mov     [rsp+arg_10], r8
0x1400042c0  mov     [rsp+arg_18], r9
0x1400042c5  sub     rsp, 68h
0x1400042c9  movdqa  [rsp+68h+var_48], xmm0
0x1400042cf  movdqa  [rsp+68h+var_38], xmm1
0x1400042d5  movdqa  [rsp+68h+var_28], xmm2
0x1400042db  movdqa  [rsp+68h+var_18], xmm3
0x1400042e1  mov     rdx, rax
0x1400042e4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_keyboard_l1_1_0_dll
0x1400042eb  call    __delayLoadHelper2
0x1400042f0  movdqa  xmm0, [rsp+68h+var_48]
0x1400042f6  movdqa  xmm1, [rsp+68h+var_38]
0x1400042fc  movdqa  xmm2, [rsp+68h+var_28]
0x140004302  movdqa  xmm3, [rsp+68h+var_18]
0x140004308  mov     rcx, [rsp+68h+arg_0]
0x14000430d  mov     rdx, [rsp+68h+arg_8]
0x140004312  mov     r8, [rsp+68h+arg_10]
0x14000431a  mov     r9, [rsp+68h+arg_18]
0x140004322  add     rsp, 68h
0x140004326  jmp     short $+2
0x140004328  jmp     rax
```
