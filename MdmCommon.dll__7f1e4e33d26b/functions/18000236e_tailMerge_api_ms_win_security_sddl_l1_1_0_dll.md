# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000236e`
- end: `0x1800023e7`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800023ed`

## callees

- `0x18000236e`
- `0x18001d370`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000236e  mov     [rsp+arg_0], rcx
0x180002373  mov     [rsp+arg_8], rdx
0x180002378  mov     [rsp+arg_10], r8
0x18000237d  mov     [rsp+arg_18], r9
0x180002382  sub     rsp, 68h
0x180002386  movdqa  [rsp+68h+var_48], xmm0
0x18000238c  movdqa  [rsp+68h+var_38], xmm1
0x180002392  movdqa  [rsp+68h+var_28], xmm2
0x180002398  movdqa  [rsp+68h+var_18], xmm3
0x18000239e  mov     rdx, rax
0x1800023a1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x1800023a8  call    __delayLoadHelper2
0x1800023ad  movdqa  xmm0, [rsp+68h+var_48]
0x1800023b3  movdqa  xmm1, [rsp+68h+var_38]
0x1800023b9  movdqa  xmm2, [rsp+68h+var_28]
0x1800023bf  movdqa  xmm3, [rsp+68h+var_18]
0x1800023c5  mov     rcx, [rsp+68h+arg_0]
0x1800023ca  mov     rdx, [rsp+68h+arg_8]
0x1800023cf  mov     r8, [rsp+68h+arg_10]
0x1800023d7  mov     r9, [rsp+68h+arg_18]
0x1800023df  add     rsp, 68h
0x1800023e3  jmp     short $+2
0x1800023e5  jmp     rax
```
