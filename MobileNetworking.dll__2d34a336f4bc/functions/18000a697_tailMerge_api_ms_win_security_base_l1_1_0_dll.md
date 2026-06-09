# __tailMerge_api_ms_win_security_base_l1_1_0_dll

- ea: `0x18000a697`
- end: `0x18000a710`
- name: `__tailMerge_api_ms_win_security_base_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `19`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a716`
- `0x18000a728`
- `0x18000a73a`
- `0x18000a74c`
- `0x18000a75e`
- `0x18000a770`
- `0x18000a782`
- `0x18000a794`
- `0x18000a7a6`
- `0x18000a7b8`
- `0x18000a7ca`
- `0x18000a7dc`
- `0x18000a7ee`
- `0x18000a800`
- `0x18000a812`
- `0x18000a8c1`
- `0x18000aa67`
- `0x18000aaaf`
- `0x18000aac1`

## callees

- `0x180007cd0`
- `0x18000a697`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a697  mov     [rsp+arg_0], rcx
0x18000a69c  mov     [rsp+arg_8], rdx
0x18000a6a1  mov     [rsp+arg_10], r8
0x18000a6a6  mov     [rsp+arg_18], r9
0x18000a6ab  sub     rsp, 68h
0x18000a6af  movdqa  [rsp+68h+var_48], xmm0
0x18000a6b5  movdqa  [rsp+68h+var_38], xmm1
0x18000a6bb  movdqa  [rsp+68h+var_28], xmm2
0x18000a6c1  movdqa  [rsp+68h+var_18], xmm3
0x18000a6c7  mov     rdx, rax
0x18000a6ca  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll
0x18000a6d1  call    __delayLoadHelper2
0x18000a6d6  movdqa  xmm0, [rsp+68h+var_48]
0x18000a6dc  movdqa  xmm1, [rsp+68h+var_38]
0x18000a6e2  movdqa  xmm2, [rsp+68h+var_28]
0x18000a6e8  movdqa  xmm3, [rsp+68h+var_18]
0x18000a6ee  mov     rcx, [rsp+68h+arg_0]
0x18000a6f3  mov     rdx, [rsp+68h+arg_8]
0x18000a6f8  mov     r8, [rsp+68h+arg_10]
0x18000a700  mov     r9, [rsp+68h+arg_18]
0x18000a708  add     rsp, 68h
0x18000a70c  jmp     short $+2
0x18000a70e  jmp     rax
```
