# __tailMerge_user32_dll

- ea: `0x18000333a`
- end: `0x1800033b3`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800033b9`
- `0x1800033cb`
- `0x1800033dd`
- `0x1800033ef`
- `0x180003401`
- `0x180003413`
- `0x180003425`

## callees

- `0x18000333a`
- `0x18000be10`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000333a  mov     [rsp+arg_0], rcx
0x18000333f  mov     [rsp+arg_8], rdx
0x180003344  mov     [rsp+arg_10], r8
0x180003349  mov     [rsp+arg_18], r9
0x18000334e  sub     rsp, 68h
0x180003352  movdqa  [rsp+68h+var_48], xmm0
0x180003358  movdqa  [rsp+68h+var_38], xmm1
0x18000335e  movdqa  [rsp+68h+var_28], xmm2
0x180003364  movdqa  [rsp+68h+var_18], xmm3
0x18000336a  mov     rdx, rax
0x18000336d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180003374  call    __delayLoadHelper2
0x180003379  movdqa  xmm0, [rsp+68h+var_48]
0x18000337f  movdqa  xmm1, [rsp+68h+var_38]
0x180003385  movdqa  xmm2, [rsp+68h+var_28]
0x18000338b  movdqa  xmm3, [rsp+68h+var_18]
0x180003391  mov     rcx, [rsp+68h+arg_0]
0x180003396  mov     rdx, [rsp+68h+arg_8]
0x18000339b  mov     r8, [rsp+68h+arg_10]
0x1800033a3  mov     r9, [rsp+68h+arg_18]
0x1800033ab  add     rsp, 68h
0x1800033af  jmp     short $+2
0x1800033b1  jmp     rax
```
