# __tailMerge_crypt32_dll

- ea: `0x18000251f`
- end: `0x180002598`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000259e`
- `0x1800025b0`
- `0x1800025c2`
- `0x1800025d4`
- `0x1800025e6`
- `0x1800025f8`

## callees

- `0x18000251f`
- `0x180014100`

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
0x18000251f  mov     [rsp+arg_0], rcx
0x180002524  mov     [rsp+arg_8], rdx
0x180002529  mov     [rsp+arg_10], r8
0x18000252e  mov     [rsp+arg_18], r9
0x180002533  sub     rsp, 68h
0x180002537  movdqa  [rsp+68h+var_48], xmm0
0x18000253d  movdqa  [rsp+68h+var_38], xmm1
0x180002543  movdqa  [rsp+68h+var_28], xmm2
0x180002549  movdqa  [rsp+68h+var_18], xmm3
0x18000254f  mov     rdx, rax
0x180002552  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180002559  call    __delayLoadHelper2
0x18000255e  movdqa  xmm0, [rsp+68h+var_48]
0x180002564  movdqa  xmm1, [rsp+68h+var_38]
0x18000256a  movdqa  xmm2, [rsp+68h+var_28]
0x180002570  movdqa  xmm3, [rsp+68h+var_18]
0x180002576  mov     rcx, [rsp+68h+arg_0]
0x18000257b  mov     rdx, [rsp+68h+arg_8]
0x180002580  mov     r8, [rsp+68h+arg_10]
0x180002588  mov     r9, [rsp+68h+arg_18]
0x180002590  add     rsp, 68h
0x180002594  jmp     short $+2
0x180002596  jmp     rax
```
