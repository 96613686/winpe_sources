# __tailMerge_userdatatypehelperutil_dll

- ea: `0x1800026b2`
- end: `0x18000272b`
- name: `__tailMerge_userdatatypehelperutil_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002731`

## callees

- `0x1800026b2`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_userdatatypehelperutil_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_userdatatypehelperutil_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026b2  mov     [rsp+arg_0], rcx
0x1800026b7  mov     [rsp+arg_8], rdx
0x1800026bc  mov     [rsp+arg_10], r8
0x1800026c1  mov     [rsp+arg_18], r9
0x1800026c6  sub     rsp, 68h
0x1800026ca  movdqa  [rsp+68h+var_48], xmm0
0x1800026d0  movdqa  [rsp+68h+var_38], xmm1
0x1800026d6  movdqa  [rsp+68h+var_28], xmm2
0x1800026dc  movdqa  [rsp+68h+var_18], xmm3
0x1800026e2  mov     rdx, rax
0x1800026e5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userdatatypehelperutil_dll
0x1800026ec  call    __delayLoadHelper2
0x1800026f1  movdqa  xmm0, [rsp+68h+var_48]
0x1800026f7  movdqa  xmm1, [rsp+68h+var_38]
0x1800026fd  movdqa  xmm2, [rsp+68h+var_28]
0x180002703  movdqa  xmm3, [rsp+68h+var_18]
0x180002709  mov     rcx, [rsp+68h+arg_0]
0x18000270e  mov     rdx, [rsp+68h+arg_8]
0x180002713  mov     r8, [rsp+68h+arg_10]
0x18000271b  mov     r9, [rsp+68h+arg_18]
0x180002723  add     rsp, 68h
0x180002727  jmp     short $+2
0x180002729  jmp     rax
```
