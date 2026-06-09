# __tailMerge_crypt32_dll

- ea: `0x1800023c0`
- end: `0x180002439`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000243f`
- `0x180002475`
- `0x180002487`

## callees

- `0x1800023c0`
- `0x18001a560`

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
0x1800023c0  mov     [rsp+arg_0], rcx
0x1800023c5  mov     [rsp+arg_8], rdx
0x1800023ca  mov     [rsp+arg_10], r8
0x1800023cf  mov     [rsp+arg_18], r9
0x1800023d4  sub     rsp, 68h
0x1800023d8  movdqa  [rsp+68h+var_48], xmm0
0x1800023de  movdqa  [rsp+68h+var_38], xmm1
0x1800023e4  movdqa  [rsp+68h+var_28], xmm2
0x1800023ea  movdqa  [rsp+68h+var_18], xmm3
0x1800023f0  mov     rdx, rax
0x1800023f3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x1800023fa  call    __delayLoadHelper2
0x1800023ff  movdqa  xmm0, [rsp+68h+var_48]
0x180002405  movdqa  xmm1, [rsp+68h+var_38]
0x18000240b  movdqa  xmm2, [rsp+68h+var_28]
0x180002411  movdqa  xmm3, [rsp+68h+var_18]
0x180002417  mov     rcx, [rsp+68h+arg_0]
0x18000241c  mov     rdx, [rsp+68h+arg_8]
0x180002421  mov     r8, [rsp+68h+arg_10]
0x180002429  mov     r9, [rsp+68h+arg_18]
0x180002431  add     rsp, 68h
0x180002435  jmp     short $+2
0x180002437  jmp     rax
```
