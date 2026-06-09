# __tailMerge_faultrep_dll

- ea: `0x1800035a6`
- end: `0x18000361f`
- name: `__tailMerge_faultrep_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003625`

## callees

- `0x1800035a6`
- `0x180010a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_faultrep_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_faultrep_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800035a6  mov     [rsp+arg_0], rcx
0x1800035ab  mov     [rsp+arg_8], rdx
0x1800035b0  mov     [rsp+arg_10], r8
0x1800035b5  mov     [rsp+arg_18], r9
0x1800035ba  sub     rsp, 68h
0x1800035be  movdqa  [rsp+68h+var_48], xmm0
0x1800035c4  movdqa  [rsp+68h+var_38], xmm1
0x1800035ca  movdqa  [rsp+68h+var_28], xmm2
0x1800035d0  movdqa  [rsp+68h+var_18], xmm3
0x1800035d6  mov     rdx, rax
0x1800035d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_faultrep_dll
0x1800035e0  call    __delayLoadHelper2
0x1800035e5  movdqa  xmm0, [rsp+68h+var_48]
0x1800035eb  movdqa  xmm1, [rsp+68h+var_38]
0x1800035f1  movdqa  xmm2, [rsp+68h+var_28]
0x1800035f7  movdqa  xmm3, [rsp+68h+var_18]
0x1800035fd  mov     rcx, [rsp+68h+arg_0]
0x180003602  mov     rdx, [rsp+68h+arg_8]
0x180003607  mov     r8, [rsp+68h+arg_10]
0x18000360f  mov     r9, [rsp+68h+arg_18]
0x180003617  add     rsp, 68h
0x18000361b  jmp     short $+2
0x18000361d  jmp     rax
```
