# __tailMerge_rpcrt4_dll

- ea: `0x180025579`
- end: `0x1800255f2`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800255f8`
- `0x18002560a`
- `0x18002561c`
- `0x18002562e`
- `0x180025640`
- `0x180025652`
- `0x180025664`
- `0x180025676`
- `0x180025688`
- `0x18002569a`
- `0x180025749`
- `0x18002575b`

## callees

- `0x18001d4b0`
- `0x180025579`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180025579  mov     [rsp+arg_0], rcx
0x18002557e  mov     [rsp+arg_8], rdx
0x180025583  mov     [rsp+arg_10], r8
0x180025588  mov     [rsp+arg_18], r9
0x18002558d  sub     rsp, 68h
0x180025591  movdqa  [rsp+68h+var_48], xmm0
0x180025597  movdqa  [rsp+68h+var_38], xmm1
0x18002559d  movdqa  [rsp+68h+var_28], xmm2
0x1800255a3  movdqa  [rsp+68h+var_18], xmm3
0x1800255a9  mov     rdx, rax
0x1800255ac  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x1800255b3  call    __delayLoadHelper2
0x1800255b8  movdqa  xmm0, [rsp+68h+var_48]
0x1800255be  movdqa  xmm1, [rsp+68h+var_38]
0x1800255c4  movdqa  xmm2, [rsp+68h+var_28]
0x1800255ca  movdqa  xmm3, [rsp+68h+var_18]
0x1800255d0  mov     rcx, [rsp+68h+arg_0]
0x1800255d5  mov     rdx, [rsp+68h+arg_8]
0x1800255da  mov     r8, [rsp+68h+arg_10]
0x1800255e2  mov     r9, [rsp+68h+arg_18]
0x1800255ea  add     rsp, 68h
0x1800255ee  jmp     short $+2
0x1800255f0  jmp     rax
```
