# __tailMerge_oleaut32_dll

- ea: `0x140002080`
- end: `0x1400020f9`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400020ff`
- `0x140002111`
- `0x1400021ae`
- `0x1400021c0`
- `0x1400021d2`
- `0x14000227c`

## callees

- `0x140002080`
- `0x140009150`

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
0x140002080  mov     [rsp+arg_0], rcx
0x140002085  mov     [rsp+arg_8], rdx
0x14000208a  mov     [rsp+arg_10], r8
0x14000208f  mov     [rsp+arg_18], r9
0x140002094  sub     rsp, 68h
0x140002098  movdqa  [rsp+68h+var_48], xmm0
0x14000209e  movdqa  [rsp+68h+var_38], xmm1
0x1400020a4  movdqa  [rsp+68h+var_28], xmm2
0x1400020aa  movdqa  [rsp+68h+var_18], xmm3
0x1400020b0  mov     rdx, rax
0x1400020b3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x1400020ba  call    __delayLoadHelper2
0x1400020bf  movdqa  xmm0, [rsp+68h+var_48]
0x1400020c5  movdqa  xmm1, [rsp+68h+var_38]
0x1400020cb  movdqa  xmm2, [rsp+68h+var_28]
0x1400020d1  movdqa  xmm3, [rsp+68h+var_18]
0x1400020d7  mov     rcx, [rsp+68h+arg_0]
0x1400020dc  mov     rdx, [rsp+68h+arg_8]
0x1400020e1  mov     r8, [rsp+68h+arg_10]
0x1400020e9  mov     r9, [rsp+68h+arg_18]
0x1400020f1  add     rsp, 68h
0x1400020f5  jmp     short $+2
0x1400020f7  jmp     rax
```
