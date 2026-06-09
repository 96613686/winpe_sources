# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x1400029be`
- end: `0x140002a37`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002a3d`

## callees

- `0x1400029be`
- `0x14000fc40`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400029be  mov     [rsp+arg_0], rcx
0x1400029c3  mov     [rsp+arg_8], rdx
0x1400029c8  mov     [rsp+arg_10], r8
0x1400029cd  mov     [rsp+arg_18], r9
0x1400029d2  sub     rsp, 68h
0x1400029d6  movdqa  [rsp+68h+var_48], xmm0
0x1400029dc  movdqa  [rsp+68h+var_38], xmm1
0x1400029e2  movdqa  [rsp+68h+var_28], xmm2
0x1400029e8  movdqa  [rsp+68h+var_18], xmm3
0x1400029ee  mov     rdx, rax
0x1400029f1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x1400029f8  call    __delayLoadHelper2
0x1400029fd  movdqa  xmm0, [rsp+68h+var_48]
0x140002a03  movdqa  xmm1, [rsp+68h+var_38]
0x140002a09  movdqa  xmm2, [rsp+68h+var_28]
0x140002a0f  movdqa  xmm3, [rsp+68h+var_18]
0x140002a15  mov     rcx, [rsp+68h+arg_0]
0x140002a1a  mov     rdx, [rsp+68h+arg_8]
0x140002a1f  mov     r8, [rsp+68h+arg_10]
0x140002a27  mov     r9, [rsp+68h+arg_18]
0x140002a2f  add     rsp, 68h
0x140002a33  jmp     short $+2
0x140002a35  jmp     rax
```
