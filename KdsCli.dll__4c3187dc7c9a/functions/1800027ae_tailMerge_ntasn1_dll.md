# __tailMerge_ntasn1_dll

- ea: `0x1800027ae`
- end: `0x180002827`
- name: `__tailMerge_ntasn1_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000282d`
- `0x18000283f`
- `0x180002851`

## callees

- `0x1800027ae`
- `0x18001a560`

## pseudocode

```c
__int64 __fastcall _tailMerge_ntasn1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ntasn1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027ae  mov     [rsp+arg_0], rcx
0x1800027b3  mov     [rsp+arg_8], rdx
0x1800027b8  mov     [rsp+arg_10], r8
0x1800027bd  mov     [rsp+arg_18], r9
0x1800027c2  sub     rsp, 68h
0x1800027c6  movdqa  [rsp+68h+var_48], xmm0
0x1800027cc  movdqa  [rsp+68h+var_38], xmm1
0x1800027d2  movdqa  [rsp+68h+var_28], xmm2
0x1800027d8  movdqa  [rsp+68h+var_18], xmm3
0x1800027de  mov     rdx, rax
0x1800027e1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ntasn1_dll
0x1800027e8  call    __delayLoadHelper2
0x1800027ed  movdqa  xmm0, [rsp+68h+var_48]
0x1800027f3  movdqa  xmm1, [rsp+68h+var_38]
0x1800027f9  movdqa  xmm2, [rsp+68h+var_28]
0x1800027ff  movdqa  xmm3, [rsp+68h+var_18]
0x180002805  mov     rcx, [rsp+68h+arg_0]
0x18000280a  mov     rdx, [rsp+68h+arg_8]
0x18000280f  mov     r8, [rsp+68h+arg_10]
0x180002817  mov     r9, [rsp+68h+arg_18]
0x18000281f  add     rsp, 68h
0x180002823  jmp     short $+2
0x180002825  jmp     rax
```
