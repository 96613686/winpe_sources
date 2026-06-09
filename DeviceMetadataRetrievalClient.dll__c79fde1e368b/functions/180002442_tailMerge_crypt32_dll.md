# __tailMerge_crypt32_dll

- ea: `0x180002442`
- end: `0x1800024bb`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800024c1`

## callees

- `0x180002442`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002442  mov     [rsp+arg_0], rcx
0x180002447  mov     [rsp+arg_8], rdx
0x18000244c  mov     [rsp+arg_10], r8
0x180002451  mov     [rsp+arg_18], r9
0x180002456  sub     rsp, 68h
0x18000245a  movdqa  [rsp+68h+var_48], xmm0
0x180002460  movdqa  [rsp+68h+var_38], xmm1
0x180002466  movdqa  [rsp+68h+var_28], xmm2
0x18000246c  movdqa  [rsp+68h+var_18], xmm3
0x180002472  mov     rdx, rax
0x180002475  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18000247c  call    __delayLoadHelper2
0x180002481  movdqa  xmm0, [rsp+68h+var_48]
0x180002487  movdqa  xmm1, [rsp+68h+var_38]
0x18000248d  movdqa  xmm2, [rsp+68h+var_28]
0x180002493  movdqa  xmm3, [rsp+68h+var_18]
0x180002499  mov     rcx, [rsp+68h+arg_0]
0x18000249e  mov     rdx, [rsp+68h+arg_8]
0x1800024a3  mov     r8, [rsp+68h+arg_10]
0x1800024ab  mov     r9, [rsp+68h+arg_18]
0x1800024b3  add     rsp, 68h
0x1800024b7  jmp     short $+2
0x1800024b9  jmp     rax
```
