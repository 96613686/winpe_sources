# __tailMerge_aepic_dll

- ea: `0x1800024a6`
- end: `0x18000251f`
- name: `__tailMerge_aepic_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002525`
- `0x180002537`

## callees

- `0x1800024a6`
- `0x18001bb20`

## pseudocode

```c
__int64 __fastcall _tailMerge_aepic_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_aepic_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024a6  mov     [rsp+arg_0], rcx
0x1800024ab  mov     [rsp+arg_8], rdx
0x1800024b0  mov     [rsp+arg_10], r8
0x1800024b5  mov     [rsp+arg_18], r9
0x1800024ba  sub     rsp, 68h
0x1800024be  movdqa  [rsp+68h+var_48], xmm0
0x1800024c4  movdqa  [rsp+68h+var_38], xmm1
0x1800024ca  movdqa  [rsp+68h+var_28], xmm2
0x1800024d0  movdqa  [rsp+68h+var_18], xmm3
0x1800024d6  mov     rdx, rax
0x1800024d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_aepic_dll
0x1800024e0  call    __delayLoadHelper2
0x1800024e5  movdqa  xmm0, [rsp+68h+var_48]
0x1800024eb  movdqa  xmm1, [rsp+68h+var_38]
0x1800024f1  movdqa  xmm2, [rsp+68h+var_28]
0x1800024f7  movdqa  xmm3, [rsp+68h+var_18]
0x1800024fd  mov     rcx, [rsp+68h+arg_0]
0x180002502  mov     rdx, [rsp+68h+arg_8]
0x180002507  mov     r8, [rsp+68h+arg_10]
0x18000250f  mov     r9, [rsp+68h+arg_18]
0x180002517  add     rsp, 68h
0x18000251b  jmp     short $+2
0x18000251d  jmp     rax
```
