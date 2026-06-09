# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x14000319c`
- end: `0x140003215`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000321b`

## callees

- `0x14000319c`
- `0x14001d800`

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
0x14000319c  mov     [rsp+arg_0], rcx
0x1400031a1  mov     [rsp+arg_8], rdx
0x1400031a6  mov     [rsp+arg_10], r8
0x1400031ab  mov     [rsp+arg_18], r9
0x1400031b0  sub     rsp, 68h
0x1400031b4  movdqa  [rsp+68h+var_48], xmm0
0x1400031ba  movdqa  [rsp+68h+var_38], xmm1
0x1400031c0  movdqa  [rsp+68h+var_28], xmm2
0x1400031c6  movdqa  [rsp+68h+var_18], xmm3
0x1400031cc  mov     rdx, rax
0x1400031cf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x1400031d6  call    __delayLoadHelper2
0x1400031db  movdqa  xmm0, [rsp+68h+var_48]
0x1400031e1  movdqa  xmm1, [rsp+68h+var_38]
0x1400031e7  movdqa  xmm2, [rsp+68h+var_28]
0x1400031ed  movdqa  xmm3, [rsp+68h+var_18]
0x1400031f3  mov     rcx, [rsp+68h+arg_0]
0x1400031f8  mov     rdx, [rsp+68h+arg_8]
0x1400031fd  mov     r8, [rsp+68h+arg_10]
0x140003205  mov     r9, [rsp+68h+arg_18]
0x14000320d  add     rsp, 68h
0x140003211  jmp     short $+2
0x140003213  jmp     rax
```
