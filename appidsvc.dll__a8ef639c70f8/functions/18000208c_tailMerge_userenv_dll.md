# __tailMerge_userenv_dll

- ea: `0x18000208c`
- end: `0x180002105`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002110`
- `0x1800021c0`

## callees

- `0x18000208c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_userenv_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000208c  mov     [rsp+arg_0], rcx
0x180002091  mov     [rsp+arg_8], rdx
0x180002096  mov     [rsp+arg_10], r8
0x18000209b  mov     [rsp+arg_18], r9
0x1800020a0  sub     rsp, 68h
0x1800020a4  movdqa  [rsp+68h+var_48], xmm0
0x1800020aa  movdqa  [rsp+68h+var_38], xmm1
0x1800020b0  movdqa  [rsp+68h+var_28], xmm2
0x1800020b6  movdqa  [rsp+68h+var_18], xmm3
0x1800020bc  mov     rdx, rax
0x1800020bf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x1800020c6  call    __delayLoadHelper2
0x1800020cb  movdqa  xmm0, [rsp+68h+var_48]
0x1800020d1  movdqa  xmm1, [rsp+68h+var_38]
0x1800020d7  movdqa  xmm2, [rsp+68h+var_28]
0x1800020dd  movdqa  xmm3, [rsp+68h+var_18]
0x1800020e3  mov     rcx, [rsp+68h+arg_0]
0x1800020e8  mov     rdx, [rsp+68h+arg_8]
0x1800020ed  mov     r8, [rsp+68h+arg_10]
0x1800020f5  mov     r9, [rsp+68h+arg_18]
0x1800020fd  add     rsp, 68h
0x180002101  jmp     short $+2
0x180002103  jmp     rax
```
