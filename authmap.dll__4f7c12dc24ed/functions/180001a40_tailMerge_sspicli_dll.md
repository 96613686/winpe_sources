# __tailMerge_sspicli_dll

- ea: `0x180001a40`
- end: `0x180001ab9`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001abf`
- `0x180001ad1`
- `0x180001ae3`

## callees

- `0x180001a40`
- `0x180006cb0`

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
0x180001a40  mov     [rsp+arg_0], rcx
0x180001a45  mov     [rsp+arg_8], rdx
0x180001a4a  mov     [rsp+arg_10], r8
0x180001a4f  mov     [rsp+arg_18], r9
0x180001a54  sub     rsp, 68h
0x180001a58  movdqa  [rsp+68h+var_48], xmm0
0x180001a5e  movdqa  [rsp+68h+var_38], xmm1
0x180001a64  movdqa  [rsp+68h+var_28], xmm2
0x180001a6a  movdqa  [rsp+68h+var_18], xmm3
0x180001a70  mov     rdx, rax
0x180001a73  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x180001a7a  call    __delayLoadHelper2
0x180001a7f  movdqa  xmm0, [rsp+68h+var_48]
0x180001a85  movdqa  xmm1, [rsp+68h+var_38]
0x180001a8b  movdqa  xmm2, [rsp+68h+var_28]
0x180001a91  movdqa  xmm3, [rsp+68h+var_18]
0x180001a97  mov     rcx, [rsp+68h+arg_0]
0x180001a9c  mov     rdx, [rsp+68h+arg_8]
0x180001aa1  mov     r8, [rsp+68h+arg_10]
0x180001aa9  mov     r9, [rsp+68h+arg_18]
0x180001ab1  add     rsp, 68h
0x180001ab5  jmp     short $+2
0x180001ab7  jmp     rax
```
