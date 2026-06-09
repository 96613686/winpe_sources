# __tailMerge_wintrust_dll

- ea: `0x18000274c`
- end: `0x1800027c5`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027d0`
- `0x1800027f0`
- `0x180002810`
- `0x180002830`
- `0x180002850`
- `0x180002870`
- `0x180002890`
- `0x1800028b0`
- `0x1800028d0`
- `0x1800028f0`

## callees

- `0x18000274c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_wintrust_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000274c  mov     [rsp+arg_0], rcx
0x180002751  mov     [rsp+arg_8], rdx
0x180002756  mov     [rsp+arg_10], r8
0x18000275b  mov     [rsp+arg_18], r9
0x180002760  sub     rsp, 68h
0x180002764  movdqa  [rsp+68h+var_48], xmm0
0x18000276a  movdqa  [rsp+68h+var_38], xmm1
0x180002770  movdqa  [rsp+68h+var_28], xmm2
0x180002776  movdqa  [rsp+68h+var_18], xmm3
0x18000277c  mov     rdx, rax
0x18000277f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x180002786  call    __delayLoadHelper2
0x18000278b  movdqa  xmm0, [rsp+68h+var_48]
0x180002791  movdqa  xmm1, [rsp+68h+var_38]
0x180002797  movdqa  xmm2, [rsp+68h+var_28]
0x18000279d  movdqa  xmm3, [rsp+68h+var_18]
0x1800027a3  mov     rcx, [rsp+68h+arg_0]
0x1800027a8  mov     rdx, [rsp+68h+arg_8]
0x1800027ad  mov     r8, [rsp+68h+arg_10]
0x1800027b5  mov     r9, [rsp+68h+arg_18]
0x1800027bd  add     rsp, 68h
0x1800027c1  jmp     short $+2
0x1800027c3  jmp     rax
```
