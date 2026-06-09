# __tailMerge_sspicli_dll

- ea: `0x1800032d0`
- end: `0x180003349`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000334f`
- `0x180003361`
- `0x180003373`

## callees

- `0x1800032d0`
- `0x180005a70`

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
0x1800032d0  mov     [rsp+arg_0], rcx
0x1800032d5  mov     [rsp+arg_8], rdx
0x1800032da  mov     [rsp+arg_10], r8
0x1800032df  mov     [rsp+arg_18], r9
0x1800032e4  sub     rsp, 68h
0x1800032e8  movdqa  [rsp+68h+var_48], xmm0
0x1800032ee  movdqa  [rsp+68h+var_38], xmm1
0x1800032f4  movdqa  [rsp+68h+var_28], xmm2
0x1800032fa  movdqa  [rsp+68h+var_18], xmm3
0x180003300  mov     rdx, rax
0x180003303  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x18000330a  call    __delayLoadHelper2
0x18000330f  movdqa  xmm0, [rsp+68h+var_48]
0x180003315  movdqa  xmm1, [rsp+68h+var_38]
0x18000331b  movdqa  xmm2, [rsp+68h+var_28]
0x180003321  movdqa  xmm3, [rsp+68h+var_18]
0x180003327  mov     rcx, [rsp+68h+arg_0]
0x18000332c  mov     rdx, [rsp+68h+arg_8]
0x180003331  mov     r8, [rsp+68h+arg_10]
0x180003339  mov     r9, [rsp+68h+arg_18]
0x180003341  add     rsp, 68h
0x180003345  jmp     short $+2
0x180003347  jmp     rax
```
