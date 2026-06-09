# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x1400022ca`
- end: `0x140002343`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002349`

## callees

- `0x1400022ca`
- `0x140011350`

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
0x1400022ca  mov     [rsp+arg_0], rcx
0x1400022cf  mov     [rsp+arg_8], rdx
0x1400022d4  mov     [rsp+arg_10], r8
0x1400022d9  mov     [rsp+arg_18], r9
0x1400022de  sub     rsp, 68h
0x1400022e2  movdqa  [rsp+68h+var_48], xmm0
0x1400022e8  movdqa  [rsp+68h+var_38], xmm1
0x1400022ee  movdqa  [rsp+68h+var_28], xmm2
0x1400022f4  movdqa  [rsp+68h+var_18], xmm3
0x1400022fa  mov     rdx, rax
0x1400022fd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x140002304  call    __delayLoadHelper2
0x140002309  movdqa  xmm0, [rsp+68h+var_48]
0x14000230f  movdqa  xmm1, [rsp+68h+var_38]
0x140002315  movdqa  xmm2, [rsp+68h+var_28]
0x14000231b  movdqa  xmm3, [rsp+68h+var_18]
0x140002321  mov     rcx, [rsp+68h+arg_0]
0x140002326  mov     rdx, [rsp+68h+arg_8]
0x14000232b  mov     r8, [rsp+68h+arg_10]
0x140002333  mov     r9, [rsp+68h+arg_18]
0x14000233b  add     rsp, 68h
0x14000233f  jmp     short $+2
0x140002341  jmp     rax
```
