# __tailMerge_rtutils_dll

- ea: `0x180015b27`
- end: `0x180015ba0`
- name: `__tailMerge_rtutils_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015ba6`
- `0x180015d70`
- `0x180015d82`

## callees

- `0x180014230`
- `0x180015b27`

## pseudocode

```c
__int64 __fastcall _tailMerge_rtutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rtutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015b27  mov     [rsp+arg_0], rcx
0x180015b2c  mov     [rsp+arg_8], rdx
0x180015b31  mov     [rsp+arg_10], r8
0x180015b36  mov     [rsp+arg_18], r9
0x180015b3b  sub     rsp, 68h
0x180015b3f  movdqa  [rsp+68h+var_48], xmm0
0x180015b45  movdqa  [rsp+68h+var_38], xmm1
0x180015b4b  movdqa  [rsp+68h+var_28], xmm2
0x180015b51  movdqa  [rsp+68h+var_18], xmm3
0x180015b57  mov     rdx, rax
0x180015b5a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rtutils_dll
0x180015b61  call    __delayLoadHelper2
0x180015b66  movdqa  xmm0, [rsp+68h+var_48]
0x180015b6c  movdqa  xmm1, [rsp+68h+var_38]
0x180015b72  movdqa  xmm2, [rsp+68h+var_28]
0x180015b78  movdqa  xmm3, [rsp+68h+var_18]
0x180015b7e  mov     rcx, [rsp+68h+arg_0]
0x180015b83  mov     rdx, [rsp+68h+arg_8]
0x180015b88  mov     r8, [rsp+68h+arg_10]
0x180015b90  mov     r9, [rsp+68h+arg_18]
0x180015b98  add     rsp, 68h
0x180015b9c  jmp     short $+2
0x180015b9e  jmp     rax
```
