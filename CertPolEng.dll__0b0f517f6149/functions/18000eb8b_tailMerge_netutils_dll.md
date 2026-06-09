# __tailMerge_netutils_dll

- ea: `0x18000eb8b`
- end: `0x18000ec04`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ec0a`

## callees

- `0x180008870`
- `0x18000eb8b`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000eb8b  mov     [rsp+arg_0], rcx
0x18000eb90  mov     [rsp+arg_8], rdx
0x18000eb95  mov     [rsp+arg_10], r8
0x18000eb9a  mov     [rsp+arg_18], r9
0x18000eb9f  sub     rsp, 68h
0x18000eba3  movdqa  [rsp+68h+var_48], xmm0
0x18000eba9  movdqa  [rsp+68h+var_38], xmm1
0x18000ebaf  movdqa  [rsp+68h+var_28], xmm2
0x18000ebb5  movdqa  [rsp+68h+var_18], xmm3
0x18000ebbb  mov     rdx, rax
0x18000ebbe  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x18000ebc5  call    __delayLoadHelper2
0x18000ebca  movdqa  xmm0, [rsp+68h+var_48]
0x18000ebd0  movdqa  xmm1, [rsp+68h+var_38]
0x18000ebd6  movdqa  xmm2, [rsp+68h+var_28]
0x18000ebdc  movdqa  xmm3, [rsp+68h+var_18]
0x18000ebe2  mov     rcx, [rsp+68h+arg_0]
0x18000ebe7  mov     rdx, [rsp+68h+arg_8]
0x18000ebec  mov     r8, [rsp+68h+arg_10]
0x18000ebf4  mov     r9, [rsp+68h+arg_18]
0x18000ebfc  add     rsp, 68h
0x18000ec00  jmp     short $+2
0x18000ec02  jmp     rax
```
