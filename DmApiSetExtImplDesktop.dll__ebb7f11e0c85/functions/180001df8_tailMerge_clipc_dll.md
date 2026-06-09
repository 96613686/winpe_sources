# __tailMerge_clipc_dll

- ea: `0x180001df8`
- end: `0x180001e71`
- name: `__tailMerge_clipc_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e77`

## callees

- `0x180001df8`
- `0x180009a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_clipc_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_clipc_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001df8  mov     [rsp+arg_0], rcx
0x180001dfd  mov     [rsp+arg_8], rdx
0x180001e02  mov     [rsp+arg_10], r8
0x180001e07  mov     [rsp+arg_18], r9
0x180001e0c  sub     rsp, 68h
0x180001e10  movdqa  [rsp+68h+var_48], xmm0
0x180001e16  movdqa  [rsp+68h+var_38], xmm1
0x180001e1c  movdqa  [rsp+68h+var_28], xmm2
0x180001e22  movdqa  [rsp+68h+var_18], xmm3
0x180001e28  mov     rdx, rax
0x180001e2b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_clipc_dll
0x180001e32  call    __delayLoadHelper2
0x180001e37  movdqa  xmm0, [rsp+68h+var_48]
0x180001e3d  movdqa  xmm1, [rsp+68h+var_38]
0x180001e43  movdqa  xmm2, [rsp+68h+var_28]
0x180001e49  movdqa  xmm3, [rsp+68h+var_18]
0x180001e4f  mov     rcx, [rsp+68h+arg_0]
0x180001e54  mov     rdx, [rsp+68h+arg_8]
0x180001e59  mov     r8, [rsp+68h+arg_10]
0x180001e61  mov     r9, [rsp+68h+arg_18]
0x180001e69  add     rsp, 68h
0x180001e6d  jmp     short $+2
0x180001e6f  jmp     rax
```
