# __tailMerge_setupapi_dll

- ea: `0x180003b75`
- end: `0x180003bee`
- name: `__tailMerge_setupapi_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180003bf4`
- `0x180003c06`
- `0x180003c18`
- `0x180003c2a`

## callees

- `0x180003b75`
- `0x180016410`

## pseudocode

```c
__int64 __fastcall _tailMerge_setupapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_setupapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003b75  mov     [rsp+arg_0], rcx
0x180003b7a  mov     [rsp+arg_8], rdx
0x180003b7f  mov     [rsp+arg_10], r8
0x180003b84  mov     [rsp+arg_18], r9
0x180003b89  sub     rsp, 68h
0x180003b8d  movdqa  [rsp+68h+var_48], xmm0
0x180003b93  movdqa  [rsp+68h+var_38], xmm1
0x180003b99  movdqa  [rsp+68h+var_28], xmm2
0x180003b9f  movdqa  [rsp+68h+var_18], xmm3
0x180003ba5  mov     rdx, rax
0x180003ba8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_setupapi_dll
0x180003baf  call    __delayLoadHelper2
0x180003bb4  movdqa  xmm0, [rsp+68h+var_48]
0x180003bba  movdqa  xmm1, [rsp+68h+var_38]
0x180003bc0  movdqa  xmm2, [rsp+68h+var_28]
0x180003bc6  movdqa  xmm3, [rsp+68h+var_18]
0x180003bcc  mov     rcx, [rsp+68h+arg_0]
0x180003bd1  mov     rdx, [rsp+68h+arg_8]
0x180003bd6  mov     r8, [rsp+68h+arg_10]
0x180003bde  mov     r9, [rsp+68h+arg_18]
0x180003be6  add     rsp, 68h
0x180003bea  jmp     short $+2
0x180003bec  jmp     rax
```
