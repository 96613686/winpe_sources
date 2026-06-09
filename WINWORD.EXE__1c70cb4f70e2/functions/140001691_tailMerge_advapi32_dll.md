# __tailMerge_advapi32_dll

- ea: `0x140001691`
- end: `0x14000170b`
- name: `__tailMerge_advapi32_dll`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000170b`
- `0x140001717`
- `0x140001723`
- `0x14000172f`
- `0x14000302a`

## callees

- `0x140001691`
- `0x140002d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001691  mov     [rsp+arg_0], rcx
0x140001696  mov     [rsp+arg_8], rdx
0x14000169b  mov     [rsp+arg_10], r8
0x1400016a0  mov     [rsp+arg_18], r9
0x1400016a5  sub     rsp, 68h
0x1400016a9  movdqa  [rsp+68h+var_48], xmm0
0x1400016af  movdqa  [rsp+68h+var_38], xmm1
0x1400016b5  movdqa  [rsp+68h+var_28], xmm2
0x1400016bb  movdqa  [rsp+68h+var_18], xmm3
0x1400016c1  mov     rdx, rax
0x1400016c4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x1400016cb  call    __delayLoadHelper2
0x1400016d0  movdqa  xmm0, [rsp+68h+var_48]
0x1400016d6  movdqa  xmm1, [rsp+68h+var_38]
0x1400016dc  movdqa  xmm2, [rsp+68h+var_28]
0x1400016e2  movdqa  xmm3, [rsp+68h+var_18]
0x1400016e8  mov     rcx, [rsp+68h+arg_0]
0x1400016ed  mov     rdx, [rsp+68h+arg_8]
0x1400016f2  mov     r8, [rsp+68h+arg_10]
0x1400016fa  mov     r9, [rsp+68h+arg_18]
0x140001702  add     rsp, 68h
0x140001706  jmp     short loc_140001709
0x140001709  jmp     rax
```
