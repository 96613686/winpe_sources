# __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll

- ea: `0x14000416c`
- end: `0x1400041e5`
- name: `__tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400041eb`
- `0x1400041fd`
- `0x14000420f`

## callees

- `0x14000416c`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsapolicy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000416c  mov     [rsp+arg_0], rcx
0x140004171  mov     [rsp+arg_8], rdx
0x140004176  mov     [rsp+arg_10], r8
0x14000417b  mov     [rsp+arg_18], r9
0x140004180  sub     rsp, 68h
0x140004184  movdqa  [rsp+68h+var_48], xmm0
0x14000418a  movdqa  [rsp+68h+var_38], xmm1
0x140004190  movdqa  [rsp+68h+var_28], xmm2
0x140004196  movdqa  [rsp+68h+var_18], xmm3
0x14000419c  mov     rdx, rax
0x14000419f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsapolicy_l1_1_0_dll
0x1400041a6  call    __delayLoadHelper2
0x1400041ab  movdqa  xmm0, [rsp+68h+var_48]
0x1400041b1  movdqa  xmm1, [rsp+68h+var_38]
0x1400041b7  movdqa  xmm2, [rsp+68h+var_28]
0x1400041bd  movdqa  xmm3, [rsp+68h+var_18]
0x1400041c3  mov     rcx, [rsp+68h+arg_0]
0x1400041c8  mov     rdx, [rsp+68h+arg_8]
0x1400041cd  mov     r8, [rsp+68h+arg_10]
0x1400041d5  mov     r9, [rsp+68h+arg_18]
0x1400041dd  add     rsp, 68h
0x1400041e1  jmp     short $+2
0x1400041e3  jmp     rax
```
