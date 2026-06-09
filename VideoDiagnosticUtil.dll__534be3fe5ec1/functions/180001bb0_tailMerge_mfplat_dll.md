# __tailMerge_mfplat_dll

- ea: `0x180001bb0`
- end: `0x180001c29`
- name: `__tailMerge_mfplat_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c2f`
- `0x180001c41`
- `0x180001c53`

## callees

- `0x180001bb0`
- `0x180009080`

## pseudocode

```c
__int64 __fastcall _tailMerge_mfplat_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_mfplat_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001bb0  mov     [rsp+arg_0], rcx
0x180001bb5  mov     [rsp+arg_8], rdx
0x180001bba  mov     [rsp+arg_10], r8
0x180001bbf  mov     [rsp+arg_18], r9
0x180001bc4  sub     rsp, 68h
0x180001bc8  movdqa  [rsp+68h+var_48], xmm0
0x180001bce  movdqa  [rsp+68h+var_38], xmm1
0x180001bd4  movdqa  [rsp+68h+var_28], xmm2
0x180001bda  movdqa  [rsp+68h+var_18], xmm3
0x180001be0  mov     rdx, rax
0x180001be3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mfplat_dll
0x180001bea  call    __delayLoadHelper2
0x180001bef  movdqa  xmm0, [rsp+68h+var_48]
0x180001bf5  movdqa  xmm1, [rsp+68h+var_38]
0x180001bfb  movdqa  xmm2, [rsp+68h+var_28]
0x180001c01  movdqa  xmm3, [rsp+68h+var_18]
0x180001c07  mov     rcx, [rsp+68h+arg_0]
0x180001c0c  mov     rdx, [rsp+68h+arg_8]
0x180001c11  mov     r8, [rsp+68h+arg_10]
0x180001c19  mov     r9, [rsp+68h+arg_18]
0x180001c21  add     rsp, 68h
0x180001c25  jmp     short $+2
0x180001c27  jmp     rax
```
