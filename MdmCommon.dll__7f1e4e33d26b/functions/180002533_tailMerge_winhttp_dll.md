# __tailMerge_winhttp_dll

- ea: `0x180002533`
- end: `0x1800025ac`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025b2`
- `0x1800025c4`
- `0x1800025d6`
- `0x1800025e8`
- `0x1800025fa`
- `0x18000260c`
- `0x18000261e`
- `0x180002630`
- `0x180002642`
- `0x180002654`
- `0x180002666`

## callees

- `0x180002533`
- `0x18001d370`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002533  mov     [rsp+arg_0], rcx
0x180002538  mov     [rsp+arg_8], rdx
0x18000253d  mov     [rsp+arg_10], r8
0x180002542  mov     [rsp+arg_18], r9
0x180002547  sub     rsp, 68h
0x18000254b  movdqa  [rsp+68h+var_48], xmm0
0x180002551  movdqa  [rsp+68h+var_38], xmm1
0x180002557  movdqa  [rsp+68h+var_28], xmm2
0x18000255d  movdqa  [rsp+68h+var_18], xmm3
0x180002563  mov     rdx, rax
0x180002566  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x18000256d  call    __delayLoadHelper2
0x180002572  movdqa  xmm0, [rsp+68h+var_48]
0x180002578  movdqa  xmm1, [rsp+68h+var_38]
0x18000257e  movdqa  xmm2, [rsp+68h+var_28]
0x180002584  movdqa  xmm3, [rsp+68h+var_18]
0x18000258a  mov     rcx, [rsp+68h+arg_0]
0x18000258f  mov     rdx, [rsp+68h+arg_8]
0x180002594  mov     r8, [rsp+68h+arg_10]
0x18000259c  mov     r9, [rsp+68h+arg_18]
0x1800025a4  add     rsp, 68h
0x1800025a8  jmp     short $+2
0x1800025aa  jmp     rax
```
