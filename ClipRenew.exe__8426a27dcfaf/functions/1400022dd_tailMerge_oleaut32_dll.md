# __tailMerge_oleaut32_dll

- ea: `0x1400022dd`
- end: `0x140002356`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000235c`
- `0x14000240b`
- `0x1400024ba`
- `0x1400024de`

## callees

- `0x1400022dd`
- `0x140013380`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400022dd  mov     [rsp+arg_0], rcx
0x1400022e2  mov     [rsp+arg_8], rdx
0x1400022e7  mov     [rsp+arg_10], r8
0x1400022ec  mov     [rsp+arg_18], r9
0x1400022f1  sub     rsp, 68h
0x1400022f5  movdqa  [rsp+68h+var_48], xmm0
0x1400022fb  movdqa  [rsp+68h+var_38], xmm1
0x140002301  movdqa  [rsp+68h+var_28], xmm2
0x140002307  movdqa  [rsp+68h+var_18], xmm3
0x14000230d  mov     rdx, rax
0x140002310  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x140002317  call    __delayLoadHelper2
0x14000231c  movdqa  xmm0, [rsp+68h+var_48]
0x140002322  movdqa  xmm1, [rsp+68h+var_38]
0x140002328  movdqa  xmm2, [rsp+68h+var_28]
0x14000232e  movdqa  xmm3, [rsp+68h+var_18]
0x140002334  mov     rcx, [rsp+68h+arg_0]
0x140002339  mov     rdx, [rsp+68h+arg_8]
0x14000233e  mov     r8, [rsp+68h+arg_10]
0x140002346  mov     r9, [rsp+68h+arg_18]
0x14000234e  add     rsp, 68h
0x140002352  jmp     short $+2
0x140002354  jmp     rax
```
