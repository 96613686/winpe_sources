# __tailMerge_mfplat_dll

- ea: `0x180001445`
- end: `0x1800014be`
- name: `__tailMerge_mfplat_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800014c4`
- `0x1800014d6`
- `0x1800014e8`

## callees

- `0x180001445`
- `0x180022c50`

## pseudocode

```c
__int64 __fastcall _tailMerge_mfplat_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mfplat_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001445  mov     [rsp+arg_0], rcx
0x18000144a  mov     [rsp+arg_8], rdx
0x18000144f  mov     [rsp+arg_10], r8
0x180001454  mov     [rsp+arg_18], r9
0x180001459  sub     rsp, 68h
0x18000145d  movdqa  [rsp+68h+var_48], xmm0
0x180001463  movdqa  [rsp+68h+var_38], xmm1
0x180001469  movdqa  [rsp+68h+var_28], xmm2
0x18000146f  movdqa  [rsp+68h+var_18], xmm3
0x180001475  mov     rdx, rax
0x180001478  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mfplat_dll
0x18000147f  call    __delayLoadHelper2
0x180001484  movdqa  xmm0, [rsp+68h+var_48]
0x18000148a  movdqa  xmm1, [rsp+68h+var_38]
0x180001490  movdqa  xmm2, [rsp+68h+var_28]
0x180001496  movdqa  xmm3, [rsp+68h+var_18]
0x18000149c  mov     rcx, [rsp+68h+arg_0]
0x1800014a1  mov     rdx, [rsp+68h+arg_8]
0x1800014a6  mov     r8, [rsp+68h+arg_10]
0x1800014ae  mov     r9, [rsp+68h+arg_18]
0x1800014b6  add     rsp, 68h
0x1800014ba  jmp     short $+2
0x1800014bc  jmp     rax
```
