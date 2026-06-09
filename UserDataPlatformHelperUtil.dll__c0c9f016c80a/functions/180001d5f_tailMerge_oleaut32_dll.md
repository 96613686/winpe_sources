# __tailMerge_oleaut32_dll

- ea: `0x180001d5f`
- end: `0x180001dd8`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001dde`
- `0x1800022c6`
- `0x1800022d8`
- `0x1800022ea`
- `0x1800022fc`
- `0x1800025b5`
- `0x1800025c7`
- `0x1800025d9`
- `0x1800025eb`
- `0x1800025fd`

## callees

- `0x180001d5f`
- `0x18000a0f0`

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
0x180001d5f  mov     [rsp+arg_0], rcx
0x180001d64  mov     [rsp+arg_8], rdx
0x180001d69  mov     [rsp+arg_10], r8
0x180001d6e  mov     [rsp+arg_18], r9
0x180001d73  sub     rsp, 68h
0x180001d77  movdqa  [rsp+68h+var_48], xmm0
0x180001d7d  movdqa  [rsp+68h+var_38], xmm1
0x180001d83  movdqa  [rsp+68h+var_28], xmm2
0x180001d89  movdqa  [rsp+68h+var_18], xmm3
0x180001d8f  mov     rdx, rax
0x180001d92  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180001d99  call    __delayLoadHelper2
0x180001d9e  movdqa  xmm0, [rsp+68h+var_48]
0x180001da4  movdqa  xmm1, [rsp+68h+var_38]
0x180001daa  movdqa  xmm2, [rsp+68h+var_28]
0x180001db0  movdqa  xmm3, [rsp+68h+var_18]
0x180001db6  mov     rcx, [rsp+68h+arg_0]
0x180001dbb  mov     rdx, [rsp+68h+arg_8]
0x180001dc0  mov     r8, [rsp+68h+arg_10]
0x180001dc8  mov     r9, [rsp+68h+arg_18]
0x180001dd0  add     rsp, 68h
0x180001dd4  jmp     short $+2
0x180001dd6  jmp     rax
```
