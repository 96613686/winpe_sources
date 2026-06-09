# __tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll

- ea: `0x180002259`
- end: `0x1800022d2`
- name: `__tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022d8`

## callees

- `0x180002259`
- `0x180020f30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002259  mov     [rsp+arg_0], rcx
0x18000225e  mov     [rsp+arg_8], rdx
0x180002263  mov     [rsp+arg_10], r8
0x180002268  mov     [rsp+arg_18], r9
0x18000226d  sub     rsp, 68h
0x180002271  movdqa  [rsp+68h+var_48], xmm0
0x180002277  movdqa  [rsp+68h+var_38], xmm1
0x18000227d  movdqa  [rsp+68h+var_28], xmm2
0x180002283  movdqa  [rsp+68h+var_18], xmm3
0x180002289  mov     rdx, rax
0x18000228c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll
0x180002293  call    __delayLoadHelper2
0x180002298  movdqa  xmm0, [rsp+68h+var_48]
0x18000229e  movdqa  xmm1, [rsp+68h+var_38]
0x1800022a4  movdqa  xmm2, [rsp+68h+var_28]
0x1800022aa  movdqa  xmm3, [rsp+68h+var_18]
0x1800022b0  mov     rcx, [rsp+68h+arg_0]
0x1800022b5  mov     rdx, [rsp+68h+arg_8]
0x1800022ba  mov     r8, [rsp+68h+arg_10]
0x1800022c2  mov     r9, [rsp+68h+arg_18]
0x1800022ca  add     rsp, 68h
0x1800022ce  jmp     short $+2
0x1800022d0  jmp     rax
```
