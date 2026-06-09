# __tailMerge_esent_dll

- ea: `0x180002308`
- end: `0x180002381`
- name: `__tailMerge_esent_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002387`
- `0x180002399`

## callees

- `0x180002308`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_esent_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_esent_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002308  mov     [rsp+arg_0], rcx
0x18000230d  mov     [rsp+arg_8], rdx
0x180002312  mov     [rsp+arg_10], r8
0x180002317  mov     [rsp+arg_18], r9
0x18000231c  sub     rsp, 68h
0x180002320  movdqa  [rsp+68h+var_48], xmm0
0x180002326  movdqa  [rsp+68h+var_38], xmm1
0x18000232c  movdqa  [rsp+68h+var_28], xmm2
0x180002332  movdqa  [rsp+68h+var_18], xmm3
0x180002338  mov     rdx, rax
0x18000233b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_esent_dll
0x180002342  call    __delayLoadHelper2
0x180002347  movdqa  xmm0, [rsp+68h+var_48]
0x18000234d  movdqa  xmm1, [rsp+68h+var_38]
0x180002353  movdqa  xmm2, [rsp+68h+var_28]
0x180002359  movdqa  xmm3, [rsp+68h+var_18]
0x18000235f  mov     rcx, [rsp+68h+arg_0]
0x180002364  mov     rdx, [rsp+68h+arg_8]
0x180002369  mov     r8, [rsp+68h+arg_10]
0x180002371  mov     r9, [rsp+68h+arg_18]
0x180002379  add     rsp, 68h
0x18000237d  jmp     short $+2
0x18000237f  jmp     rax
```
