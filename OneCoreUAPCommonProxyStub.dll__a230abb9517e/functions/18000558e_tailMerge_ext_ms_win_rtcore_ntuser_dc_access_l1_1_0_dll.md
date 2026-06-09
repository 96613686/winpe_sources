# __tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll

- ea: `0x18000558e`
- end: `0x180005607`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000560d`

## callees

- `0x180002420`
- `0x18000558e`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000558e  mov     [rsp+arg_0], rcx
0x180005593  mov     [rsp+arg_8], rdx
0x180005598  mov     [rsp+arg_10], r8
0x18000559d  mov     [rsp+arg_18], r9
0x1800055a2  sub     rsp, 68h
0x1800055a6  movdqa  [rsp+68h+var_48], xmm0
0x1800055ac  movdqa  [rsp+68h+var_38], xmm1
0x1800055b2  movdqa  [rsp+68h+var_28], xmm2
0x1800055b8  movdqa  [rsp+68h+var_18], xmm3
0x1800055be  mov     rdx, rax
0x1800055c1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll
0x1800055c8  call    __delayLoadHelper2
0x1800055cd  movdqa  xmm0, [rsp+68h+var_48]
0x1800055d3  movdqa  xmm1, [rsp+68h+var_38]
0x1800055d9  movdqa  xmm2, [rsp+68h+var_28]
0x1800055df  movdqa  xmm3, [rsp+68h+var_18]
0x1800055e5  mov     rcx, [rsp+68h+arg_0]
0x1800055ea  mov     rdx, [rsp+68h+arg_8]
0x1800055ef  mov     r8, [rsp+68h+arg_10]
0x1800055f7  mov     r9, [rsp+68h+arg_18]
0x1800055ff  add     rsp, 68h
0x180005603  jmp     short $+2
0x180005605  jmp     rax
```
