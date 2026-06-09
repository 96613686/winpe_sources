# __tailMerge_version_dll

- ea: `0x180002c6d`
- end: `0x180002ce6`
- name: `__tailMerge_version_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002cec`
- `0x180002cfe`
- `0x180002d10`

## callees

- `0x180002c6d`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_version_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_version_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002c6d  mov     [rsp+arg_0], rcx
0x180002c72  mov     [rsp+arg_8], rdx
0x180002c77  mov     [rsp+arg_10], r8
0x180002c7c  mov     [rsp+arg_18], r9
0x180002c81  sub     rsp, 68h
0x180002c85  movdqa  [rsp+68h+var_48], xmm0
0x180002c8b  movdqa  [rsp+68h+var_38], xmm1
0x180002c91  movdqa  [rsp+68h+var_28], xmm2
0x180002c97  movdqa  [rsp+68h+var_18], xmm3
0x180002c9d  mov     rdx, rax
0x180002ca0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_version_dll
0x180002ca7  call    __delayLoadHelper2
0x180002cac  movdqa  xmm0, [rsp+68h+var_48]
0x180002cb2  movdqa  xmm1, [rsp+68h+var_38]
0x180002cb8  movdqa  xmm2, [rsp+68h+var_28]
0x180002cbe  movdqa  xmm3, [rsp+68h+var_18]
0x180002cc4  mov     rcx, [rsp+68h+arg_0]
0x180002cc9  mov     rdx, [rsp+68h+arg_8]
0x180002cce  mov     r8, [rsp+68h+arg_10]
0x180002cd6  mov     r9, [rsp+68h+arg_18]
0x180002cde  add     rsp, 68h
0x180002ce2  jmp     short $+2
0x180002ce4  jmp     rax
```
