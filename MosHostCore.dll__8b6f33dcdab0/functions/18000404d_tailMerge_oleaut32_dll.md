# __tailMerge_oleaut32_dll

- ea: `0x18000404d`
- end: `0x1800040c6`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800040cc`
- `0x1800040de`
- `0x1800040f0`
- `0x180004102`
- `0x180004114`
- `0x180004126`
- `0x180004138`
- `0x18000414a`
- `0x18000415c`
- `0x18000416e`
- `0x180004180`
- `0x180004192`
- `0x1800041a4`
- `0x1800041b6`
- `0x1800041c8`

## callees

- `0x18000404d`
- `0x180022e30`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000404d  mov     [rsp+arg_0], rcx
0x180004052  mov     [rsp+arg_8], rdx
0x180004057  mov     [rsp+arg_10], r8
0x18000405c  mov     [rsp+arg_18], r9
0x180004061  sub     rsp, 68h
0x180004065  movdqa  [rsp+68h+var_48], xmm0
0x18000406b  movdqa  [rsp+68h+var_38], xmm1
0x180004071  movdqa  [rsp+68h+var_28], xmm2
0x180004077  movdqa  [rsp+68h+var_18], xmm3
0x18000407d  mov     rdx, rax
0x180004080  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180004087  call    __delayLoadHelper2
0x18000408c  movdqa  xmm0, [rsp+68h+var_48]
0x180004092  movdqa  xmm1, [rsp+68h+var_38]
0x180004098  movdqa  xmm2, [rsp+68h+var_28]
0x18000409e  movdqa  xmm3, [rsp+68h+var_18]
0x1800040a4  mov     rcx, [rsp+68h+arg_0]
0x1800040a9  mov     rdx, [rsp+68h+arg_8]
0x1800040ae  mov     r8, [rsp+68h+arg_10]
0x1800040b6  mov     r9, [rsp+68h+arg_18]
0x1800040be  add     rsp, 68h
0x1800040c2  jmp     short $+2
0x1800040c4  jmp     rax
```
