# __tailMerge_slc_dll

- ea: `0x18000269c`
- end: `0x180002715`
- name: `__tailMerge_slc_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002720`
- `0x180002740`

## callees

- `0x18000269c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_slc_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_slc_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000269c  mov     [rsp+arg_0], rcx
0x1800026a1  mov     [rsp+arg_8], rdx
0x1800026a6  mov     [rsp+arg_10], r8
0x1800026ab  mov     [rsp+arg_18], r9
0x1800026b0  sub     rsp, 68h
0x1800026b4  movdqa  [rsp+68h+var_48], xmm0
0x1800026ba  movdqa  [rsp+68h+var_38], xmm1
0x1800026c0  movdqa  [rsp+68h+var_28], xmm2
0x1800026c6  movdqa  [rsp+68h+var_18], xmm3
0x1800026cc  mov     rdx, rax
0x1800026cf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_slc_dll
0x1800026d6  call    __delayLoadHelper2
0x1800026db  movdqa  xmm0, [rsp+68h+var_48]
0x1800026e1  movdqa  xmm1, [rsp+68h+var_38]
0x1800026e7  movdqa  xmm2, [rsp+68h+var_28]
0x1800026ed  movdqa  xmm3, [rsp+68h+var_18]
0x1800026f3  mov     rcx, [rsp+68h+arg_0]
0x1800026f8  mov     rdx, [rsp+68h+arg_8]
0x1800026fd  mov     r8, [rsp+68h+arg_10]
0x180002705  mov     r9, [rsp+68h+arg_18]
0x18000270d  add     rsp, 68h
0x180002711  jmp     short $+2
0x180002713  jmp     rax
```
