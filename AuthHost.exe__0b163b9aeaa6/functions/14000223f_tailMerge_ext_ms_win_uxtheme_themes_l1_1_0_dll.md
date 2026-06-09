# __tailMerge_ext_ms_win_uxtheme_themes_l1_1_0_dll

- ea: `0x14000223f`
- end: `0x1400022b8`
- name: `__tailMerge_ext_ms_win_uxtheme_themes_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400022be`
- `0x1400022d0`

## callees

- `0x14000223f`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_uxtheme_themes_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_uxtheme_themes_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000223f  mov     [rsp+arg_0], rcx
0x140002244  mov     [rsp+arg_8], rdx
0x140002249  mov     [rsp+arg_10], r8
0x14000224e  mov     [rsp+arg_18], r9
0x140002253  sub     rsp, 68h
0x140002257  movdqa  [rsp+68h+var_48], xmm0
0x14000225d  movdqa  [rsp+68h+var_38], xmm1
0x140002263  movdqa  [rsp+68h+var_28], xmm2
0x140002269  movdqa  [rsp+68h+var_18], xmm3
0x14000226f  mov     rdx, rax
0x140002272  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_uxtheme_themes_l1_1_0_dll
0x140002279  call    __delayLoadHelper2
0x14000227e  movdqa  xmm0, [rsp+68h+var_48]
0x140002284  movdqa  xmm1, [rsp+68h+var_38]
0x14000228a  movdqa  xmm2, [rsp+68h+var_28]
0x140002290  movdqa  xmm3, [rsp+68h+var_18]
0x140002296  mov     rcx, [rsp+68h+arg_0]
0x14000229b  mov     rdx, [rsp+68h+arg_8]
0x1400022a0  mov     r8, [rsp+68h+arg_10]
0x1400022a8  mov     r9, [rsp+68h+arg_18]
0x1400022b0  add     rsp, 68h
0x1400022b4  jmp     short $+2
0x1400022b6  jmp     rax
```
