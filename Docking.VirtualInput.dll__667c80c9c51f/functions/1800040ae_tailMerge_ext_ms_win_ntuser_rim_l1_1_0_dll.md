# __tailMerge_ext_ms_win_ntuser_rim_l1_1_0_dll

- ea: `0x1800040ae`
- end: `0x180004127`
- name: `__tailMerge_ext_ms_win_ntuser_rim_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000412d`
- `0x18000413f`
- `0x180004151`

## callees

- `0x1800040ae`
- `0x18001b2a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_rim_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_rim_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800040ae  mov     [rsp+arg_0], rcx
0x1800040b3  mov     [rsp+arg_8], rdx
0x1800040b8  mov     [rsp+arg_10], r8
0x1800040bd  mov     [rsp+arg_18], r9
0x1800040c2  sub     rsp, 68h
0x1800040c6  movdqa  [rsp+68h+var_48], xmm0
0x1800040cc  movdqa  [rsp+68h+var_38], xmm1
0x1800040d2  movdqa  [rsp+68h+var_28], xmm2
0x1800040d8  movdqa  [rsp+68h+var_18], xmm3
0x1800040de  mov     rdx, rax
0x1800040e1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_rim_l1_1_0_dll
0x1800040e8  call    __delayLoadHelper2
0x1800040ed  movdqa  xmm0, [rsp+68h+var_48]
0x1800040f3  movdqa  xmm1, [rsp+68h+var_38]
0x1800040f9  movdqa  xmm2, [rsp+68h+var_28]
0x1800040ff  movdqa  xmm3, [rsp+68h+var_18]
0x180004105  mov     rcx, [rsp+68h+arg_0]
0x18000410a  mov     rdx, [rsp+68h+arg_8]
0x18000410f  mov     r8, [rsp+68h+arg_10]
0x180004117  mov     r9, [rsp+68h+arg_18]
0x18000411f  add     rsp, 68h
0x180004123  jmp     short $+2
0x180004125  jmp     rax
```
