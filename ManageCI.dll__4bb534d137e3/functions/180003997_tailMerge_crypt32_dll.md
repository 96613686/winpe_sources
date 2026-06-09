# __tailMerge_crypt32_dll

- ea: `0x180003997`
- end: `0x180003a10`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a16`
- `0x180003a28`
- `0x180003a3a`
- `0x180003a4c`
- `0x180003a5e`
- `0x180003a70`
- `0x180003a82`
- `0x180003a94`
- `0x180003aa6`
- `0x180003ab8`
- `0x180003aca`
- `0x180003adc`
- `0x180003aee`
- `0x180003b00`

## callees

- `0x180003997`
- `0x1800296d0`

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
0x180003997  mov     [rsp+arg_0], rcx
0x18000399c  mov     [rsp+arg_8], rdx
0x1800039a1  mov     [rsp+arg_10], r8
0x1800039a6  mov     [rsp+arg_18], r9
0x1800039ab  sub     rsp, 68h
0x1800039af  movdqa  [rsp+68h+var_48], xmm0
0x1800039b5  movdqa  [rsp+68h+var_38], xmm1
0x1800039bb  movdqa  [rsp+68h+var_28], xmm2
0x1800039c1  movdqa  [rsp+68h+var_18], xmm3
0x1800039c7  mov     rdx, rax
0x1800039ca  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x1800039d1  call    __delayLoadHelper2
0x1800039d6  movdqa  xmm0, [rsp+68h+var_48]
0x1800039dc  movdqa  xmm1, [rsp+68h+var_38]
0x1800039e2  movdqa  xmm2, [rsp+68h+var_28]
0x1800039e8  movdqa  xmm3, [rsp+68h+var_18]
0x1800039ee  mov     rcx, [rsp+68h+arg_0]
0x1800039f3  mov     rdx, [rsp+68h+arg_8]
0x1800039f8  mov     r8, [rsp+68h+arg_10]
0x180003a00  mov     r9, [rsp+68h+arg_18]
0x180003a08  add     rsp, 68h
0x180003a0c  jmp     short $+2
0x180003a0e  jmp     rax
```
