# __tailMerge_api_ms_win_security_lsalookup_l1_1_2_dll

- ea: `0x18000eca1`
- end: `0x18000ed1a`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed20`

## callees

- `0x180008870`
- `0x18000eca1`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000eca1  mov     [rsp+arg_0], rcx
0x18000eca6  mov     [rsp+arg_8], rdx
0x18000ecab  mov     [rsp+arg_10], r8
0x18000ecb0  mov     [rsp+arg_18], r9
0x18000ecb5  sub     rsp, 68h
0x18000ecb9  movdqa  [rsp+68h+var_48], xmm0
0x18000ecbf  movdqa  [rsp+68h+var_38], xmm1
0x18000ecc5  movdqa  [rsp+68h+var_28], xmm2
0x18000eccb  movdqa  [rsp+68h+var_18], xmm3
0x18000ecd1  mov     rdx, rax
0x18000ecd4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_2_dll
0x18000ecdb  call    __delayLoadHelper2
0x18000ece0  movdqa  xmm0, [rsp+68h+var_48]
0x18000ece6  movdqa  xmm1, [rsp+68h+var_38]
0x18000ecec  movdqa  xmm2, [rsp+68h+var_28]
0x18000ecf2  movdqa  xmm3, [rsp+68h+var_18]
0x18000ecf8  mov     rcx, [rsp+68h+arg_0]
0x18000ecfd  mov     rdx, [rsp+68h+arg_8]
0x18000ed02  mov     r8, [rsp+68h+arg_10]
0x18000ed0a  mov     r9, [rsp+68h+arg_18]
0x18000ed12  add     rsp, 68h
0x18000ed16  jmp     short $+2
0x18000ed18  jmp     rax
```
