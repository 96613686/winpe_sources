# __tailMerge_dui70_dll

- ea: `0x1800024c3`
- end: `0x18000253c`
- name: `__tailMerge_dui70_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `130`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002542`
- `0x180002554`
- `0x180002566`
- `0x180002578`
- `0x18000258a`
- `0x18000259c`
- `0x1800025ae`
- `0x1800025c0`
- `0x1800025d2`
- `0x1800025e4`
- `0x1800025f6`
- `0x180002608`
- `0x18000261a`
- `0x18000262c`
- `0x18000263e`
- `0x180002650`
- `0x180002662`
- `0x180002674`
- `0x180002686`
- `0x180002698`
- `0x1800026aa`
- `0x1800026bc`
- `0x1800026ce`
- `0x1800026e0`
- `0x1800026f2`
- `0x18000271c`
- `0x18000273c`
- `0x18000275c`
- `0x18000276e`
- `0x180002780`
- `0x180002792`
- `0x1800027a4`
- `0x1800027b6`
- `0x1800027c8`
- `0x1800027da`
- `0x1800027ec`
- `0x1800027fe`
- `0x180002810`
- `0x180002822`
- `0x180002834`
- `0x18000285c`
- `0x18000287c`
- `0x18000289c`
- `0x1800028bc`
- `0x1800028dc`
- `0x1800028fc`
- `0x18000291c`
- `0x18000293c`
- `0x18000295c`
- `0x18000297c`

## callees

- `0x1800024c3`
- `0x18000b5f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dui70_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_dui70_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024c3  mov     [rsp+arg_0], rcx
0x1800024c8  mov     [rsp+arg_8], rdx
0x1800024cd  mov     [rsp+arg_10], r8
0x1800024d2  mov     [rsp+arg_18], r9
0x1800024d7  sub     rsp, 68h
0x1800024db  movdqa  [rsp+68h+var_48], xmm0
0x1800024e1  movdqa  [rsp+68h+var_38], xmm1
0x1800024e7  movdqa  [rsp+68h+var_28], xmm2
0x1800024ed  movdqa  [rsp+68h+var_18], xmm3
0x1800024f3  mov     rdx, rax
0x1800024f6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dui70_dll
0x1800024fd  call    __delayLoadHelper2
0x180002502  movdqa  xmm0, [rsp+68h+var_48]
0x180002508  movdqa  xmm1, [rsp+68h+var_38]
0x18000250e  movdqa  xmm2, [rsp+68h+var_28]
0x180002514  movdqa  xmm3, [rsp+68h+var_18]
0x18000251a  mov     rcx, [rsp+68h+arg_0]
0x18000251f  mov     rdx, [rsp+68h+arg_8]
0x180002524  mov     r8, [rsp+68h+arg_10]
0x18000252c  mov     r9, [rsp+68h+arg_18]
0x180002534  add     rsp, 68h
0x180002538  jmp     short $+2
0x18000253a  jmp     rax
```
