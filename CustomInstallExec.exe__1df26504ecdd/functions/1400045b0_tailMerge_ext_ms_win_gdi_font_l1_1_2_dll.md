# __tailMerge_ext_ms_win_gdi_font_l1_1_2_dll

- ea: `0x1400045b0`
- end: `0x140004629`
- name: `__tailMerge_ext_ms_win_gdi_font_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000462f`

## callees

- `0x1400045b0`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_font_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400045b0  mov     [rsp+arg_0], rcx
0x1400045b5  mov     [rsp+arg_8], rdx
0x1400045ba  mov     [rsp+arg_10], r8
0x1400045bf  mov     [rsp+arg_18], r9
0x1400045c4  sub     rsp, 68h
0x1400045c8  movdqa  [rsp+68h+var_48], xmm0
0x1400045ce  movdqa  [rsp+68h+var_38], xmm1
0x1400045d4  movdqa  [rsp+68h+var_28], xmm2
0x1400045da  movdqa  [rsp+68h+var_18], xmm3
0x1400045e0  mov     rdx, rax
0x1400045e3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_font_l1_1_2_dll
0x1400045ea  call    __delayLoadHelper2
0x1400045ef  movdqa  xmm0, [rsp+68h+var_48]
0x1400045f5  movdqa  xmm1, [rsp+68h+var_38]
0x1400045fb  movdqa  xmm2, [rsp+68h+var_28]
0x140004601  movdqa  xmm3, [rsp+68h+var_18]
0x140004607  mov     rcx, [rsp+68h+arg_0]
0x14000460c  mov     rdx, [rsp+68h+arg_8]
0x140004611  mov     r8, [rsp+68h+arg_10]
0x140004619  mov     r9, [rsp+68h+arg_18]
0x140004621  add     rsp, 68h
0x140004625  jmp     short $+2
0x140004627  jmp     rax
```
