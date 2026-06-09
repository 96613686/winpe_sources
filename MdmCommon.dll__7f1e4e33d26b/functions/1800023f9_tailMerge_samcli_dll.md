# __tailMerge_samcli_dll

- ea: `0x1800023f9`
- end: `0x180002472`
- name: `__tailMerge_samcli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002478`
- `0x180002515`
- `0x180002527`

## callees

- `0x1800023f9`
- `0x18001d370`

## pseudocode

```c
__int64 __fastcall _tailMerge_samcli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_samcli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800023f9  mov     [rsp+arg_0], rcx
0x1800023fe  mov     [rsp+arg_8], rdx
0x180002403  mov     [rsp+arg_10], r8
0x180002408  mov     [rsp+arg_18], r9
0x18000240d  sub     rsp, 68h
0x180002411  movdqa  [rsp+68h+var_48], xmm0
0x180002417  movdqa  [rsp+68h+var_38], xmm1
0x18000241d  movdqa  [rsp+68h+var_28], xmm2
0x180002423  movdqa  [rsp+68h+var_18], xmm3
0x180002429  mov     rdx, rax
0x18000242c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samcli_dll
0x180002433  call    __delayLoadHelper2
0x180002438  movdqa  xmm0, [rsp+68h+var_48]
0x18000243e  movdqa  xmm1, [rsp+68h+var_38]
0x180002444  movdqa  xmm2, [rsp+68h+var_28]
0x18000244a  movdqa  xmm3, [rsp+68h+var_18]
0x180002450  mov     rcx, [rsp+68h+arg_0]
0x180002455  mov     rdx, [rsp+68h+arg_8]
0x18000245a  mov     r8, [rsp+68h+arg_10]
0x180002462  mov     r9, [rsp+68h+arg_18]
0x18000246a  add     rsp, 68h
0x18000246e  jmp     short $+2
0x180002470  jmp     rax
```
