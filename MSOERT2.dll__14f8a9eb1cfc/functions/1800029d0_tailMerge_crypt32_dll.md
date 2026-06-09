# __tailMerge_crypt32_dll

- ea: `0x1800029d0`
- end: `0x180002a49`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a4f`
- `0x180002a61`
- `0x180002a73`
- `0x180002a85`
- `0x180002a97`
- `0x180002aa9`

## callees

- `0x1800029d0`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp+arg_0], rcx
0x1800029d5  mov     [rsp+arg_8], rdx
0x1800029da  mov     [rsp+arg_10], r8
0x1800029df  mov     [rsp+arg_18], r9
0x1800029e4  sub     rsp, 68h
0x1800029e8  movdqa  [rsp+68h+var_48], xmm0
0x1800029ee  movdqa  [rsp+68h+var_38], xmm1
0x1800029f4  movdqa  [rsp+68h+var_28], xmm2
0x1800029fa  movdqa  [rsp+68h+var_18], xmm3
0x180002a00  mov     rdx, rax
0x180002a03  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180002a0a  call    __delayLoadHelper2
0x180002a0f  movdqa  xmm0, [rsp+68h+var_48]
0x180002a15  movdqa  xmm1, [rsp+68h+var_38]
0x180002a1b  movdqa  xmm2, [rsp+68h+var_28]
0x180002a21  movdqa  xmm3, [rsp+68h+var_18]
0x180002a27  mov     rcx, [rsp+68h+arg_0]
0x180002a2c  mov     rdx, [rsp+68h+arg_8]
0x180002a31  mov     r8, [rsp+68h+arg_10]
0x180002a39  mov     r9, [rsp+68h+arg_18]
0x180002a41  add     rsp, 68h
0x180002a45  jmp     short $+2
0x180002a47  jmp     rax
```
