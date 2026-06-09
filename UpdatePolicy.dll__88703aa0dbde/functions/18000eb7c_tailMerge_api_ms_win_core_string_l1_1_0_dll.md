# __tailMerge_api_ms_win_core_string_l1_1_0_dll

- ea: `0x18000eb7c`
- end: `0x18000ebf5`
- name: `__tailMerge_api_ms_win_core_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ebfb`

## callees

- `0x18000eb7c`
- `0x180014c80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_string_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000eb7c  mov     [rsp+arg_0], rcx
0x18000eb81  mov     [rsp+arg_8], rdx
0x18000eb86  mov     [rsp+arg_10], r8
0x18000eb8b  mov     [rsp+arg_18], r9
0x18000eb90  sub     rsp, 68h
0x18000eb94  movdqa  [rsp+68h+var_48], xmm0
0x18000eb9a  movdqa  [rsp+68h+var_38], xmm1
0x18000eba0  movdqa  [rsp+68h+var_28], xmm2
0x18000eba6  movdqa  [rsp+68h+var_18], xmm3
0x18000ebac  mov     rdx, rax
0x18000ebaf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_string_l1_1_0_dll
0x18000ebb6  call    __delayLoadHelper2
0x18000ebbb  movdqa  xmm0, [rsp+68h+var_48]
0x18000ebc1  movdqa  xmm1, [rsp+68h+var_38]
0x18000ebc7  movdqa  xmm2, [rsp+68h+var_28]
0x18000ebcd  movdqa  xmm3, [rsp+68h+var_18]
0x18000ebd3  mov     rcx, [rsp+68h+arg_0]
0x18000ebd8  mov     rdx, [rsp+68h+arg_8]
0x18000ebdd  mov     r8, [rsp+68h+arg_10]
0x18000ebe5  mov     r9, [rsp+68h+arg_18]
0x18000ebed  add     rsp, 68h
0x18000ebf1  jmp     short $+2
0x18000ebf3  jmp     rax
```
