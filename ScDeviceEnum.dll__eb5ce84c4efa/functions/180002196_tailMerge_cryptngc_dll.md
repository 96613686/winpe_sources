# __tailMerge_cryptngc_dll

- ea: `0x180002196`
- end: `0x18000220f`
- name: `__tailMerge_cryptngc_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002215`

## callees

- `0x180002196`
- `0x18001d9f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptngc_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_cryptngc_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002196  mov     [rsp+arg_0], rcx
0x18000219b  mov     [rsp+arg_8], rdx
0x1800021a0  mov     [rsp+arg_10], r8
0x1800021a5  mov     [rsp+arg_18], r9
0x1800021aa  sub     rsp, 68h
0x1800021ae  movdqa  [rsp+68h+var_48], xmm0
0x1800021b4  movdqa  [rsp+68h+var_38], xmm1
0x1800021ba  movdqa  [rsp+68h+var_28], xmm2
0x1800021c0  movdqa  [rsp+68h+var_18], xmm3
0x1800021c6  mov     rdx, rax
0x1800021c9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptngc_dll
0x1800021d0  call    __delayLoadHelper2
0x1800021d5  movdqa  xmm0, [rsp+68h+var_48]
0x1800021db  movdqa  xmm1, [rsp+68h+var_38]
0x1800021e1  movdqa  xmm2, [rsp+68h+var_28]
0x1800021e7  movdqa  xmm3, [rsp+68h+var_18]
0x1800021ed  mov     rcx, [rsp+68h+arg_0]
0x1800021f2  mov     rdx, [rsp+68h+arg_8]
0x1800021f7  mov     r8, [rsp+68h+arg_10]
0x1800021ff  mov     r9, [rsp+68h+arg_18]
0x180002207  add     rsp, 68h
0x18000220b  jmp     short $+2
0x18000220d  jmp     rax
```
