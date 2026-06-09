# __tailMerge_cryptsp_dll

- ea: `0x180001b24`
- end: `0x180001b9d`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ba3`
- `0x180001bb5`
- `0x180001bc7`
- `0x180001bd9`
- `0x180001beb`

## callees

- `0x180001b24`
- `0x18000c450`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001b24  mov     [rsp+arg_0], rcx
0x180001b29  mov     [rsp+arg_8], rdx
0x180001b2e  mov     [rsp+arg_10], r8
0x180001b33  mov     [rsp+arg_18], r9
0x180001b38  sub     rsp, 68h
0x180001b3c  movdqa  [rsp+68h+var_48], xmm0
0x180001b42  movdqa  [rsp+68h+var_38], xmm1
0x180001b48  movdqa  [rsp+68h+var_28], xmm2
0x180001b4e  movdqa  [rsp+68h+var_18], xmm3
0x180001b54  mov     rdx, rax
0x180001b57  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x180001b5e  call    __delayLoadHelper2
0x180001b63  movdqa  xmm0, [rsp+68h+var_48]
0x180001b69  movdqa  xmm1, [rsp+68h+var_38]
0x180001b6f  movdqa  xmm2, [rsp+68h+var_28]
0x180001b75  movdqa  xmm3, [rsp+68h+var_18]
0x180001b7b  mov     rcx, [rsp+68h+arg_0]
0x180001b80  mov     rdx, [rsp+68h+arg_8]
0x180001b85  mov     r8, [rsp+68h+arg_10]
0x180001b8d  mov     r9, [rsp+68h+arg_18]
0x180001b95  add     rsp, 68h
0x180001b99  jmp     short $+2
0x180001b9b  jmp     rax
```
