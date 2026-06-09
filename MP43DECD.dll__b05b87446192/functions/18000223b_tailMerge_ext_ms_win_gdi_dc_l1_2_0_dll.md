# __tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll

- ea: `0x18000223b`
- end: `0x1800022b4`
- name: `__tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022ba`

## callees

- `0x18000223b`
- `0x180020e70`

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
0x18000223b  mov     [rsp+arg_0], rcx
0x180002240  mov     [rsp+arg_8], rdx
0x180002245  mov     [rsp+arg_10], r8
0x18000224a  mov     [rsp+arg_18], r9
0x18000224f  sub     rsp, 68h
0x180002253  movdqa  [rsp+68h+var_48], xmm0
0x180002259  movdqa  [rsp+68h+var_38], xmm1
0x18000225f  movdqa  [rsp+68h+var_28], xmm2
0x180002265  movdqa  [rsp+68h+var_18], xmm3
0x18000226b  mov     rdx, rax
0x18000226e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll
0x180002275  call    __delayLoadHelper2
0x18000227a  movdqa  xmm0, [rsp+68h+var_48]
0x180002280  movdqa  xmm1, [rsp+68h+var_38]
0x180002286  movdqa  xmm2, [rsp+68h+var_28]
0x18000228c  movdqa  xmm3, [rsp+68h+var_18]
0x180002292  mov     rcx, [rsp+68h+arg_0]
0x180002297  mov     rdx, [rsp+68h+arg_8]
0x18000229c  mov     r8, [rsp+68h+arg_10]
0x1800022a4  mov     r9, [rsp+68h+arg_18]
0x1800022ac  add     rsp, 68h
0x1800022b0  jmp     short $+2
0x1800022b2  jmp     rax
```
