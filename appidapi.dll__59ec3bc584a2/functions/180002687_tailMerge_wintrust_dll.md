# __tailMerge_wintrust_dll

- ea: `0x180002687`
- end: `0x180002700`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002706`
- `0x180002718`
- `0x18000272a`
- `0x18000273c`
- `0x18000274e`
- `0x180002760`
- `0x180002772`
- `0x180002784`
- `0x180002796`
- `0x1800027a8`

## callees

- `0x180002687`
- `0x180009440`

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
0x180002687  mov     [rsp+arg_0], rcx
0x18000268c  mov     [rsp+arg_8], rdx
0x180002691  mov     [rsp+arg_10], r8
0x180002696  mov     [rsp+arg_18], r9
0x18000269b  sub     rsp, 68h
0x18000269f  movdqa  [rsp+68h+var_48], xmm0
0x1800026a5  movdqa  [rsp+68h+var_38], xmm1
0x1800026ab  movdqa  [rsp+68h+var_28], xmm2
0x1800026b1  movdqa  [rsp+68h+var_18], xmm3
0x1800026b7  mov     rdx, rax
0x1800026ba  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x1800026c1  call    __delayLoadHelper2
0x1800026c6  movdqa  xmm0, [rsp+68h+var_48]
0x1800026cc  movdqa  xmm1, [rsp+68h+var_38]
0x1800026d2  movdqa  xmm2, [rsp+68h+var_28]
0x1800026d8  movdqa  xmm3, [rsp+68h+var_18]
0x1800026de  mov     rcx, [rsp+68h+arg_0]
0x1800026e3  mov     rdx, [rsp+68h+arg_8]
0x1800026e8  mov     r8, [rsp+68h+arg_10]
0x1800026f0  mov     r9, [rsp+68h+arg_18]
0x1800026f8  add     rsp, 68h
0x1800026fc  jmp     short $+2
0x1800026fe  jmp     rax
```
