# __tailMerge_userenv_dll

- ea: `0x180002338`
- end: `0x1800023b1`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800023b7`
- `0x1800023d5`
- `0x1800023f3`
- `0x180002405`

## callees

- `0x180002338`
- `0x180014100`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002338  mov     [rsp+arg_0], rcx
0x18000233d  mov     [rsp+arg_8], rdx
0x180002342  mov     [rsp+arg_10], r8
0x180002347  mov     [rsp+arg_18], r9
0x18000234c  sub     rsp, 68h
0x180002350  movdqa  [rsp+68h+var_48], xmm0
0x180002356  movdqa  [rsp+68h+var_38], xmm1
0x18000235c  movdqa  [rsp+68h+var_28], xmm2
0x180002362  movdqa  [rsp+68h+var_18], xmm3
0x180002368  mov     rdx, rax
0x18000236b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180002372  call    __delayLoadHelper2
0x180002377  movdqa  xmm0, [rsp+68h+var_48]
0x18000237d  movdqa  xmm1, [rsp+68h+var_38]
0x180002383  movdqa  xmm2, [rsp+68h+var_28]
0x180002389  movdqa  xmm3, [rsp+68h+var_18]
0x18000238f  mov     rcx, [rsp+68h+arg_0]
0x180002394  mov     rdx, [rsp+68h+arg_8]
0x180002399  mov     r8, [rsp+68h+arg_10]
0x1800023a1  mov     r9, [rsp+68h+arg_18]
0x1800023a9  add     rsp, 68h
0x1800023ad  jmp     short $+2
0x1800023af  jmp     rax
```
