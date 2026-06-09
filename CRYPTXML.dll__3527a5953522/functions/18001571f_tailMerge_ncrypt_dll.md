# __tailMerge_ncrypt_dll

- ea: `0x18001571f`
- end: `0x180015798`
- name: `__tailMerge_ncrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001579e`
- `0x1800157b0`
- `0x1800157d4`
- `0x180015876`
- `0x18001589a`

## callees

- `0x180012ae0`
- `0x18001571f`

## pseudocode

```c
__int64 __fastcall _tailMerge_ncrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ncrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001571f  mov     [rsp+arg_0], rcx
0x180015724  mov     [rsp+arg_8], rdx
0x180015729  mov     [rsp+arg_10], r8
0x18001572e  mov     [rsp+arg_18], r9
0x180015733  sub     rsp, 68h
0x180015737  movdqa  [rsp+68h+var_48], xmm0
0x18001573d  movdqa  [rsp+68h+var_38], xmm1
0x180015743  movdqa  [rsp+68h+var_28], xmm2
0x180015749  movdqa  [rsp+68h+var_18], xmm3
0x18001574f  mov     rdx, rax
0x180015752  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ncrypt_dll
0x180015759  call    __delayLoadHelper2
0x18001575e  movdqa  xmm0, [rsp+68h+var_48]
0x180015764  movdqa  xmm1, [rsp+68h+var_38]
0x18001576a  movdqa  xmm2, [rsp+68h+var_28]
0x180015770  movdqa  xmm3, [rsp+68h+var_18]
0x180015776  mov     rcx, [rsp+68h+arg_0]
0x18001577b  mov     rdx, [rsp+68h+arg_8]
0x180015780  mov     r8, [rsp+68h+arg_10]
0x180015788  mov     r9, [rsp+68h+arg_18]
0x180015790  add     rsp, 68h
0x180015794  jmp     short $+2
0x180015796  jmp     rax
```
