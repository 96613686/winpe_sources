# __tailMerge_wintrust_dll

- ea: `0x180002746`
- end: `0x1800027bf`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027c5`
- `0x1800027d7`
- `0x1800027e9`

## callees

- `0x180002746`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wintrust_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002746  mov     [rsp+arg_0], rcx
0x18000274b  mov     [rsp+arg_8], rdx
0x180002750  mov     [rsp+arg_10], r8
0x180002755  mov     [rsp+arg_18], r9
0x18000275a  sub     rsp, 68h
0x18000275e  movdqa  [rsp+68h+var_48], xmm0
0x180002764  movdqa  [rsp+68h+var_38], xmm1
0x18000276a  movdqa  [rsp+68h+var_28], xmm2
0x180002770  movdqa  [rsp+68h+var_18], xmm3
0x180002776  mov     rdx, rax
0x180002779  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x180002780  call    __delayLoadHelper2
0x180002785  movdqa  xmm0, [rsp+68h+var_48]
0x18000278b  movdqa  xmm1, [rsp+68h+var_38]
0x180002791  movdqa  xmm2, [rsp+68h+var_28]
0x180002797  movdqa  xmm3, [rsp+68h+var_18]
0x18000279d  mov     rcx, [rsp+68h+arg_0]
0x1800027a2  mov     rdx, [rsp+68h+arg_8]
0x1800027a7  mov     r8, [rsp+68h+arg_10]
0x1800027af  mov     r9, [rsp+68h+arg_18]
0x1800027b7  add     rsp, 68h
0x1800027bb  jmp     short $+2
0x1800027bd  jmp     rax
```
