# __tailMerge_rpcrt4_dll

- ea: `0x180002bb6`
- end: `0x180002c2f`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c35`
- `0x180002c47`
- `0x180002c59`
- `0x180002feb`
- `0x18000300c`
- `0x18000302c`

## callees

- `0x180002bb6`
- `0x180017cd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002bb6  mov     [rsp+arg_0], rcx
0x180002bbb  mov     [rsp+arg_8], rdx
0x180002bc0  mov     [rsp+arg_10], r8
0x180002bc5  mov     [rsp+arg_18], r9
0x180002bca  sub     rsp, 68h
0x180002bce  movdqa  [rsp+68h+var_48], xmm0
0x180002bd4  movdqa  [rsp+68h+var_38], xmm1
0x180002bda  movdqa  [rsp+68h+var_28], xmm2
0x180002be0  movdqa  [rsp+68h+var_18], xmm3
0x180002be6  mov     rdx, rax
0x180002be9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180002bf0  call    __delayLoadHelper2
0x180002bf5  movdqa  xmm0, [rsp+68h+var_48]
0x180002bfb  movdqa  xmm1, [rsp+68h+var_38]
0x180002c01  movdqa  xmm2, [rsp+68h+var_28]
0x180002c07  movdqa  xmm3, [rsp+68h+var_18]
0x180002c0d  mov     rcx, [rsp+68h+arg_0]
0x180002c12  mov     rdx, [rsp+68h+arg_8]
0x180002c17  mov     r8, [rsp+68h+arg_10]
0x180002c1f  mov     r9, [rsp+68h+arg_18]
0x180002c27  add     rsp, 68h
0x180002c2b  jmp     short $+2
0x180002c2d  jmp     rax
```
