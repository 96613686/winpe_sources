# __tailMerge_propsys_dll

- ea: `0x1800100d5`
- end: `0x18001014e`
- name: `__tailMerge_propsys_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010154`
- `0x180010166`
- `0x180010178`

## callees

- `0x18000e230`
- `0x1800100d5`

## pseudocode

```c
__int64 __fastcall _tailMerge_propsys_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_propsys_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800100d5  mov     [rsp+arg_0], rcx
0x1800100da  mov     [rsp+arg_8], rdx
0x1800100df  mov     [rsp+arg_10], r8
0x1800100e4  mov     [rsp+arg_18], r9
0x1800100e9  sub     rsp, 68h
0x1800100ed  movdqa  [rsp+68h+var_48], xmm0
0x1800100f3  movdqa  [rsp+68h+var_38], xmm1
0x1800100f9  movdqa  [rsp+68h+var_28], xmm2
0x1800100ff  movdqa  [rsp+68h+var_18], xmm3
0x180010105  mov     rdx, rax
0x180010108  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_propsys_dll
0x18001010f  call    __delayLoadHelper2
0x180010114  movdqa  xmm0, [rsp+68h+var_48]
0x18001011a  movdqa  xmm1, [rsp+68h+var_38]
0x180010120  movdqa  xmm2, [rsp+68h+var_28]
0x180010126  movdqa  xmm3, [rsp+68h+var_18]
0x18001012c  mov     rcx, [rsp+68h+arg_0]
0x180010131  mov     rdx, [rsp+68h+arg_8]
0x180010136  mov     r8, [rsp+68h+arg_10]
0x18001013e  mov     r9, [rsp+68h+arg_18]
0x180010146  add     rsp, 68h
0x18001014a  jmp     short $+2
0x18001014c  jmp     rax
```
