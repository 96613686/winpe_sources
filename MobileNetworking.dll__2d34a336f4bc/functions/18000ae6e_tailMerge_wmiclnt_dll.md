# __tailMerge_wmiclnt_dll

- ea: `0x18000ae6e`
- end: `0x18000aee7`
- name: `__tailMerge_wmiclnt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aeed`
- `0x18000aeff`
- `0x18000af11`

## callees

- `0x180007cd0`
- `0x18000ae6e`

## pseudocode

```c
__int64 __fastcall _tailMerge_wmiclnt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wmiclnt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ae6e  mov     [rsp+arg_0], rcx
0x18000ae73  mov     [rsp+arg_8], rdx
0x18000ae78  mov     [rsp+arg_10], r8
0x18000ae7d  mov     [rsp+arg_18], r9
0x18000ae82  sub     rsp, 68h
0x18000ae86  movdqa  [rsp+68h+var_48], xmm0
0x18000ae8c  movdqa  [rsp+68h+var_38], xmm1
0x18000ae92  movdqa  [rsp+68h+var_28], xmm2
0x18000ae98  movdqa  [rsp+68h+var_18], xmm3
0x18000ae9e  mov     rdx, rax
0x18000aea1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wmiclnt_dll
0x18000aea8  call    __delayLoadHelper2
0x18000aead  movdqa  xmm0, [rsp+68h+var_48]
0x18000aeb3  movdqa  xmm1, [rsp+68h+var_38]
0x18000aeb9  movdqa  xmm2, [rsp+68h+var_28]
0x18000aebf  movdqa  xmm3, [rsp+68h+var_18]
0x18000aec5  mov     rcx, [rsp+68h+arg_0]
0x18000aeca  mov     rdx, [rsp+68h+arg_8]
0x18000aecf  mov     r8, [rsp+68h+arg_10]
0x18000aed7  mov     r9, [rsp+68h+arg_18]
0x18000aedf  add     rsp, 68h
0x18000aee3  jmp     short $+2
0x18000aee5  jmp     rax
```
