# __tailMerge_sspicli_dll

- ea: `0x180001f8f`
- end: `0x180002008`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000200e`
- `0x180002020`
- `0x180002032`
- `0x180002044`
- `0x180002056`

## callees

- `0x180001f8f`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f8f  mov     [rsp+arg_0], rcx
0x180001f94  mov     [rsp+arg_8], rdx
0x180001f99  mov     [rsp+arg_10], r8
0x180001f9e  mov     [rsp+arg_18], r9
0x180001fa3  sub     rsp, 68h
0x180001fa7  movdqa  [rsp+68h+var_48], xmm0
0x180001fad  movdqa  [rsp+68h+var_38], xmm1
0x180001fb3  movdqa  [rsp+68h+var_28], xmm2
0x180001fb9  movdqa  [rsp+68h+var_18], xmm3
0x180001fbf  mov     rdx, rax
0x180001fc2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180001fc9  call    __delayLoadHelper2
0x180001fce  movdqa  xmm0, [rsp+68h+var_48]
0x180001fd4  movdqa  xmm1, [rsp+68h+var_38]
0x180001fda  movdqa  xmm2, [rsp+68h+var_28]
0x180001fe0  movdqa  xmm3, [rsp+68h+var_18]
0x180001fe6  mov     rcx, [rsp+68h+arg_0]
0x180001feb  mov     rdx, [rsp+68h+arg_8]
0x180001ff0  mov     r8, [rsp+68h+arg_10]
0x180001ff8  mov     r9, [rsp+68h+arg_18]
0x180002000  add     rsp, 68h
0x180002004  jmp     short $+2
0x180002006  jmp     rax
```
