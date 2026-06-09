# __tailMerge_version_dll

- ea: `0x180001db0`
- end: `0x180001e29`
- name: `__tailMerge_version_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e2f`
- `0x180001e41`
- `0x180001e53`

## callees

- `0x180001db0`
- `0x18003cfd0`

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
0x180001db0  mov     [rsp+arg_0], rcx
0x180001db5  mov     [rsp+arg_8], rdx
0x180001dba  mov     [rsp+arg_10], r8
0x180001dbf  mov     [rsp+arg_18], r9
0x180001dc4  sub     rsp, 68h
0x180001dc8  movdqa  [rsp+68h+var_48], xmm0
0x180001dce  movdqa  [rsp+68h+var_38], xmm1
0x180001dd4  movdqa  [rsp+68h+var_28], xmm2
0x180001dda  movdqa  [rsp+68h+var_18], xmm3
0x180001de0  mov     rdx, rax
0x180001de3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_version_dll
0x180001dea  call    __delayLoadHelper2
0x180001def  movdqa  xmm0, [rsp+68h+var_48]
0x180001df5  movdqa  xmm1, [rsp+68h+var_38]
0x180001dfb  movdqa  xmm2, [rsp+68h+var_28]
0x180001e01  movdqa  xmm3, [rsp+68h+var_18]
0x180001e07  mov     rcx, [rsp+68h+arg_0]
0x180001e0c  mov     rdx, [rsp+68h+arg_8]
0x180001e11  mov     r8, [rsp+68h+arg_10]
0x180001e19  mov     r9, [rsp+68h+arg_18]
0x180001e21  add     rsp, 68h
0x180001e25  jmp     short $+2
0x180001e27  jmp     rax
```
