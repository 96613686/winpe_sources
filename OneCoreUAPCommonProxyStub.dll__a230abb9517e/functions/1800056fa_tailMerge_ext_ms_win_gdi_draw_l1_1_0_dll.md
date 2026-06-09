# __tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll

- ea: `0x1800056fa`
- end: `0x180005773`
- name: `__tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005779`
- `0x1800057e0`

## callees

- `0x180002420`
- `0x1800056fa`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_draw_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800056fa  mov     [rsp+arg_0], rcx
0x1800056ff  mov     [rsp+arg_8], rdx
0x180005704  mov     [rsp+arg_10], r8
0x180005709  mov     [rsp+arg_18], r9
0x18000570e  sub     rsp, 68h
0x180005712  movdqa  [rsp+68h+var_48], xmm0
0x180005718  movdqa  [rsp+68h+var_38], xmm1
0x18000571e  movdqa  [rsp+68h+var_28], xmm2
0x180005724  movdqa  [rsp+68h+var_18], xmm3
0x18000572a  mov     rdx, rax
0x18000572d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_0_dll
0x180005734  call    __delayLoadHelper2
0x180005739  movdqa  xmm0, [rsp+68h+var_48]
0x18000573f  movdqa  xmm1, [rsp+68h+var_38]
0x180005745  movdqa  xmm2, [rsp+68h+var_28]
0x18000574b  movdqa  xmm3, [rsp+68h+var_18]
0x180005751  mov     rcx, [rsp+68h+arg_0]
0x180005756  mov     rdx, [rsp+68h+arg_8]
0x18000575b  mov     r8, [rsp+68h+arg_10]
0x180005763  mov     r9, [rsp+68h+arg_18]
0x18000576b  add     rsp, 68h
0x18000576f  jmp     short $+2
0x180005771  jmp     rax
```
