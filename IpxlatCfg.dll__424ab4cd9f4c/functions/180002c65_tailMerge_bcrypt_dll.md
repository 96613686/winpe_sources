# __tailMerge_bcrypt_dll

- ea: `0x180002c65`
- end: `0x180002cde`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ce4`

## callees

- `0x180002c65`
- `0x180017cd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002c65  mov     [rsp+arg_0], rcx
0x180002c6a  mov     [rsp+arg_8], rdx
0x180002c6f  mov     [rsp+arg_10], r8
0x180002c74  mov     [rsp+arg_18], r9
0x180002c79  sub     rsp, 68h
0x180002c7d  movdqa  [rsp+68h+var_48], xmm0
0x180002c83  movdqa  [rsp+68h+var_38], xmm1
0x180002c89  movdqa  [rsp+68h+var_28], xmm2
0x180002c8f  movdqa  [rsp+68h+var_18], xmm3
0x180002c95  mov     rdx, rax
0x180002c98  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180002c9f  call    __delayLoadHelper2
0x180002ca4  movdqa  xmm0, [rsp+68h+var_48]
0x180002caa  movdqa  xmm1, [rsp+68h+var_38]
0x180002cb0  movdqa  xmm2, [rsp+68h+var_28]
0x180002cb6  movdqa  xmm3, [rsp+68h+var_18]
0x180002cbc  mov     rcx, [rsp+68h+arg_0]
0x180002cc1  mov     rdx, [rsp+68h+arg_8]
0x180002cc6  mov     r8, [rsp+68h+arg_10]
0x180002cce  mov     r9, [rsp+68h+arg_18]
0x180002cd6  add     rsp, 68h
0x180002cda  jmp     short $+2
0x180002cdc  jmp     rax
```
