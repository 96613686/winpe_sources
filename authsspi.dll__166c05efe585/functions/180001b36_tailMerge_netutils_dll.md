# __tailMerge_netutils_dll

- ea: `0x180001b36`
- end: `0x180001baf`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001bb5`

## callees

- `0x180001b36`
- `0x180008a70`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001b36  mov     [rsp+arg_0], rcx
0x180001b3b  mov     [rsp+arg_8], rdx
0x180001b40  mov     [rsp+arg_10], r8
0x180001b45  mov     [rsp+arg_18], r9
0x180001b4a  sub     rsp, 68h
0x180001b4e  movdqa  [rsp+68h+var_48], xmm0
0x180001b54  movdqa  [rsp+68h+var_38], xmm1
0x180001b5a  movdqa  [rsp+68h+var_28], xmm2
0x180001b60  movdqa  [rsp+68h+var_18], xmm3
0x180001b66  mov     rdx, rax
0x180001b69  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x180001b70  call    __delayLoadHelper2
0x180001b75  movdqa  xmm0, [rsp+68h+var_48]
0x180001b7b  movdqa  xmm1, [rsp+68h+var_38]
0x180001b81  movdqa  xmm2, [rsp+68h+var_28]
0x180001b87  movdqa  xmm3, [rsp+68h+var_18]
0x180001b8d  mov     rcx, [rsp+68h+arg_0]
0x180001b92  mov     rdx, [rsp+68h+arg_8]
0x180001b97  mov     r8, [rsp+68h+arg_10]
0x180001b9f  mov     r9, [rsp+68h+arg_18]
0x180001ba7  add     rsp, 68h
0x180001bab  jmp     short $+2
0x180001bad  jmp     rax
```
