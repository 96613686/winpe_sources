# __tailMerge_shell32_dll

- ea: `0x180003332`
- end: `0x1800033ab`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800033b1`

## callees

- `0x180003332`
- `0x180015930`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((unsigned int *)&_DELAY_IMPORT_DESCRIPTOR_shell32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003332  mov     [rsp+arg_0], rcx
0x180003337  mov     [rsp+arg_8], rdx
0x18000333c  mov     [rsp+arg_10], r8
0x180003341  mov     [rsp+arg_18], r9
0x180003346  sub     rsp, 68h
0x18000334a  movdqa  [rsp+68h+var_48], xmm0
0x180003350  movdqa  [rsp+68h+var_38], xmm1
0x180003356  movdqa  [rsp+68h+var_28], xmm2
0x18000335c  movdqa  [rsp+68h+var_18], xmm3
0x180003362  mov     rdx, rax
0x180003365  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x18000336c  call    __delayLoadHelper2
0x180003371  movdqa  xmm0, [rsp+68h+var_48]
0x180003377  movdqa  xmm1, [rsp+68h+var_38]
0x18000337d  movdqa  xmm2, [rsp+68h+var_28]
0x180003383  movdqa  xmm3, [rsp+68h+var_18]
0x180003389  mov     rcx, [rsp+68h+arg_0]
0x18000338e  mov     rdx, [rsp+68h+arg_8]
0x180003393  mov     r8, [rsp+68h+arg_10]
0x18000339b  mov     r9, [rsp+68h+arg_18]
0x1800033a3  add     rsp, 68h
0x1800033a7  jmp     short $+2
0x1800033a9  jmp     rax
```
