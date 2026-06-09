# __tailMerge_bcrypt_dll

- ea: `0x1800156a6`
- end: `0x18001571f`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800157c2`
- `0x1800157e6`
- `0x1800157f8`
- `0x18001580a`
- `0x18001581c`
- `0x18001582e`
- `0x180015840`
- `0x180015852`
- `0x180015864`
- `0x180015888`

## callees

- `0x180012ae0`
- `0x1800156a6`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800156a6  mov     [rsp+arg_0], rcx
0x1800156ab  mov     [rsp+arg_8], rdx
0x1800156b0  mov     [rsp+arg_10], r8
0x1800156b5  mov     [rsp+arg_18], r9
0x1800156ba  sub     rsp, 68h
0x1800156be  movdqa  [rsp+68h+var_48], xmm0
0x1800156c4  movdqa  [rsp+68h+var_38], xmm1
0x1800156ca  movdqa  [rsp+68h+var_28], xmm2
0x1800156d0  movdqa  [rsp+68h+var_18], xmm3
0x1800156d6  mov     rdx, rax
0x1800156d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800156e0  call    __delayLoadHelper2
0x1800156e5  movdqa  xmm0, [rsp+68h+var_48]
0x1800156eb  movdqa  xmm1, [rsp+68h+var_38]
0x1800156f1  movdqa  xmm2, [rsp+68h+var_28]
0x1800156f7  movdqa  xmm3, [rsp+68h+var_18]
0x1800156fd  mov     rcx, [rsp+68h+arg_0]
0x180015702  mov     rdx, [rsp+68h+arg_8]
0x180015707  mov     r8, [rsp+68h+arg_10]
0x18001570f  mov     r9, [rsp+68h+arg_18]
0x180015717  add     rsp, 68h
0x18001571b  jmp     short $+2
0x18001571d  jmp     rax
```
