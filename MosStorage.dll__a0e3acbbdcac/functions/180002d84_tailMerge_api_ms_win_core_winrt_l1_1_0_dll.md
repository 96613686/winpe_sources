# __tailMerge_api_ms_win_core_winrt_l1_1_0_dll

- ea: `0x180002d84`
- end: `0x180002dfd`
- name: `__tailMerge_api_ms_win_core_winrt_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e03`

## callees

- `0x180002d84`
- `0x18000e1a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002d84  mov     [rsp+arg_0], rcx
0x180002d89  mov     [rsp+arg_8], rdx
0x180002d8e  mov     [rsp+arg_10], r8
0x180002d93  mov     [rsp+arg_18], r9
0x180002d98  sub     rsp, 68h
0x180002d9c  movdqa  [rsp+68h+var_48], xmm0
0x180002da2  movdqa  [rsp+68h+var_38], xmm1
0x180002da8  movdqa  [rsp+68h+var_28], xmm2
0x180002dae  movdqa  [rsp+68h+var_18], xmm3
0x180002db4  mov     rdx, rax
0x180002db7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll
0x180002dbe  call    __delayLoadHelper2
0x180002dc3  movdqa  xmm0, [rsp+68h+var_48]
0x180002dc9  movdqa  xmm1, [rsp+68h+var_38]
0x180002dcf  movdqa  xmm2, [rsp+68h+var_28]
0x180002dd5  movdqa  xmm3, [rsp+68h+var_18]
0x180002ddb  mov     rcx, [rsp+68h+arg_0]
0x180002de0  mov     rdx, [rsp+68h+arg_8]
0x180002de5  mov     r8, [rsp+68h+arg_10]
0x180002ded  mov     r9, [rsp+68h+arg_18]
0x180002df5  add     rsp, 68h
0x180002df9  jmp     short $+2
0x180002dfb  jmp     rax
```
