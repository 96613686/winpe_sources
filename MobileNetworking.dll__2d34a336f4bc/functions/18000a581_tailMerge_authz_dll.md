# __tailMerge_authz_dll

- ea: `0x18000a581`
- end: `0x18000a5fa`
- name: `__tailMerge_authz_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a600`
- `0x18000ae50`
- `0x18000ae62`

## callees

- `0x180007cd0`
- `0x18000a581`

## pseudocode

```c
__int64 __fastcall _tailMerge_authz_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_authz_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a581  mov     [rsp+arg_0], rcx
0x18000a586  mov     [rsp+arg_8], rdx
0x18000a58b  mov     [rsp+arg_10], r8
0x18000a590  mov     [rsp+arg_18], r9
0x18000a595  sub     rsp, 68h
0x18000a599  movdqa  [rsp+68h+var_48], xmm0
0x18000a59f  movdqa  [rsp+68h+var_38], xmm1
0x18000a5a5  movdqa  [rsp+68h+var_28], xmm2
0x18000a5ab  movdqa  [rsp+68h+var_18], xmm3
0x18000a5b1  mov     rdx, rax
0x18000a5b4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_authz_dll
0x18000a5bb  call    __delayLoadHelper2
0x18000a5c0  movdqa  xmm0, [rsp+68h+var_48]
0x18000a5c6  movdqa  xmm1, [rsp+68h+var_38]
0x18000a5cc  movdqa  xmm2, [rsp+68h+var_28]
0x18000a5d2  movdqa  xmm3, [rsp+68h+var_18]
0x18000a5d8  mov     rcx, [rsp+68h+arg_0]
0x18000a5dd  mov     rdx, [rsp+68h+arg_8]
0x18000a5e2  mov     r8, [rsp+68h+arg_10]
0x18000a5ea  mov     r9, [rsp+68h+arg_18]
0x18000a5f2  add     rsp, 68h
0x18000a5f6  jmp     short $+2
0x18000a5f8  jmp     rax
```
