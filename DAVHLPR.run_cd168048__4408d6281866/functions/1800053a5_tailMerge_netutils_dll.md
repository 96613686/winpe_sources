# __tailMerge_netutils_dll

- ea: `0x1800053a5`
- end: `0x18000541e`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005424`
- `0x180005436`

## callees

- `0x180004570`
- `0x1800053a5`

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
0x1800053a5  mov     [rsp+arg_0], rcx
0x1800053aa  mov     [rsp+arg_8], rdx
0x1800053af  mov     [rsp+arg_10], r8
0x1800053b4  mov     [rsp+arg_18], r9
0x1800053b9  sub     rsp, 68h
0x1800053bd  movdqa  [rsp+68h+var_48], xmm0
0x1800053c3  movdqa  [rsp+68h+var_38], xmm1
0x1800053c9  movdqa  [rsp+68h+var_28], xmm2
0x1800053cf  movdqa  [rsp+68h+var_18], xmm3
0x1800053d5  mov     rdx, rax
0x1800053d8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x1800053df  call    __delayLoadHelper2
0x1800053e4  movdqa  xmm0, [rsp+68h+var_48]
0x1800053ea  movdqa  xmm1, [rsp+68h+var_38]
0x1800053f0  movdqa  xmm2, [rsp+68h+var_28]
0x1800053f6  movdqa  xmm3, [rsp+68h+var_18]
0x1800053fc  mov     rcx, [rsp+68h+arg_0]
0x180005401  mov     rdx, [rsp+68h+arg_8]
0x180005406  mov     r8, [rsp+68h+arg_10]
0x18000540e  mov     r9, [rsp+68h+arg_18]
0x180005416  add     rsp, 68h
0x18000541a  jmp     short $+2
0x18000541c  jmp     rax
```
