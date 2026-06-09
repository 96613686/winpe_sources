# __tailMerge_provpackageapidll_dll

- ea: `0x1400020e0`
- end: `0x140002159`
- name: `__tailMerge_provpackageapidll_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000215f`

## callees

- `0x1400020e0`
- `0x14000dd40`

## pseudocode

```c
__int64 __fastcall _tailMerge_provpackageapidll_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_provpackageapidll_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400020e0  mov     [rsp+arg_0], rcx
0x1400020e5  mov     [rsp+arg_8], rdx
0x1400020ea  mov     [rsp+arg_10], r8
0x1400020ef  mov     [rsp+arg_18], r9
0x1400020f4  sub     rsp, 68h
0x1400020f8  movdqa  [rsp+68h+var_48], xmm0
0x1400020fe  movdqa  [rsp+68h+var_38], xmm1
0x140002104  movdqa  [rsp+68h+var_28], xmm2
0x14000210a  movdqa  [rsp+68h+var_18], xmm3
0x140002110  mov     rdx, rax
0x140002113  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_provpackageapidll_dll
0x14000211a  call    __delayLoadHelper2
0x14000211f  movdqa  xmm0, [rsp+68h+var_48]
0x140002125  movdqa  xmm1, [rsp+68h+var_38]
0x14000212b  movdqa  xmm2, [rsp+68h+var_28]
0x140002131  movdqa  xmm3, [rsp+68h+var_18]
0x140002137  mov     rcx, [rsp+68h+arg_0]
0x14000213c  mov     rdx, [rsp+68h+arg_8]
0x140002141  mov     r8, [rsp+68h+arg_10]
0x140002149  mov     r9, [rsp+68h+arg_18]
0x140002151  add     rsp, 68h
0x140002155  jmp     short $+2
0x140002157  jmp     rax
```
