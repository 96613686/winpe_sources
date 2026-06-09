# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x140002190`
- end: `0x140002209`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000220f`
- `0x140002221`

## callees

- `0x140002190`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002190  mov     [rsp+arg_0], rcx
0x140002195  mov     [rsp+arg_8], rdx
0x14000219a  mov     [rsp+arg_10], r8
0x14000219f  mov     [rsp+arg_18], r9
0x1400021a4  sub     rsp, 68h
0x1400021a8  movdqa  [rsp+68h+var_48], xmm0
0x1400021ae  movdqa  [rsp+68h+var_38], xmm1
0x1400021b4  movdqa  [rsp+68h+var_28], xmm2
0x1400021ba  movdqa  [rsp+68h+var_18], xmm3
0x1400021c0  mov     rdx, rax
0x1400021c3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x1400021ca  call    __delayLoadHelper2
0x1400021cf  movdqa  xmm0, [rsp+68h+var_48]
0x1400021d5  movdqa  xmm1, [rsp+68h+var_38]
0x1400021db  movdqa  xmm2, [rsp+68h+var_28]
0x1400021e1  movdqa  xmm3, [rsp+68h+var_18]
0x1400021e7  mov     rcx, [rsp+68h+arg_0]
0x1400021ec  mov     rdx, [rsp+68h+arg_8]
0x1400021f1  mov     r8, [rsp+68h+arg_10]
0x1400021f9  mov     r9, [rsp+68h+arg_18]
0x140002201  add     rsp, 68h
0x140002205  jmp     short $+2
0x140002207  jmp     rax
```
