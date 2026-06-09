# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x1800028c9`
- end: `0x180002942`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002948`
- `0x1800029f7`
- `0x180002a09`
- `0x180002a1b`

## callees

- `0x1800028c9`
- `0x18000e1a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028c9  mov     [rsp+arg_0], rcx
0x1800028ce  mov     [rsp+arg_8], rdx
0x1800028d3  mov     [rsp+arg_10], r8
0x1800028d8  mov     [rsp+arg_18], r9
0x1800028dd  sub     rsp, 68h
0x1800028e1  movdqa  [rsp+68h+var_48], xmm0
0x1800028e7  movdqa  [rsp+68h+var_38], xmm1
0x1800028ed  movdqa  [rsp+68h+var_28], xmm2
0x1800028f3  movdqa  [rsp+68h+var_18], xmm3
0x1800028f9  mov     rdx, rax
0x1800028fc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180002903  call    __delayLoadHelper2
0x180002908  movdqa  xmm0, [rsp+68h+var_48]
0x18000290e  movdqa  xmm1, [rsp+68h+var_38]
0x180002914  movdqa  xmm2, [rsp+68h+var_28]
0x18000291a  movdqa  xmm3, [rsp+68h+var_18]
0x180002920  mov     rcx, [rsp+68h+arg_0]
0x180002925  mov     rdx, [rsp+68h+arg_8]
0x18000292a  mov     r8, [rsp+68h+arg_10]
0x180002932  mov     r9, [rsp+68h+arg_18]
0x18000293a  add     rsp, 68h
0x18000293e  jmp     short $+2
0x180002940  jmp     rax
```
