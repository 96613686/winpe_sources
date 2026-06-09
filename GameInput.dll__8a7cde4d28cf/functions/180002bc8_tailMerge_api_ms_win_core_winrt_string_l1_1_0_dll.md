# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x180002bc8`
- end: `0x180002c41`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c47`
- `0x180002c59`
- `0x180002c6b`
- `0x180002c7d`

## callees

- `0x180002bc8`
- `0x180047d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002bc8  mov     [rsp+arg_0], rcx
0x180002bcd  mov     [rsp+arg_8], rdx
0x180002bd2  mov     [rsp+arg_10], r8
0x180002bd7  mov     [rsp+arg_18], r9
0x180002bdc  sub     rsp, 68h
0x180002be0  movdqa  [rsp+68h+var_48], xmm0
0x180002be6  movdqa  [rsp+68h+var_38], xmm1
0x180002bec  movdqa  [rsp+68h+var_28], xmm2
0x180002bf2  movdqa  [rsp+68h+var_18], xmm3
0x180002bf8  mov     rdx, rax
0x180002bfb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x180002c02  call    __delayLoadHelper2
0x180002c07  movdqa  xmm0, [rsp+68h+var_48]
0x180002c0d  movdqa  xmm1, [rsp+68h+var_38]
0x180002c13  movdqa  xmm2, [rsp+68h+var_28]
0x180002c19  movdqa  xmm3, [rsp+68h+var_18]
0x180002c1f  mov     rcx, [rsp+68h+arg_0]
0x180002c24  mov     rdx, [rsp+68h+arg_8]
0x180002c29  mov     r8, [rsp+68h+arg_10]
0x180002c31  mov     r9, [rsp+68h+arg_18]
0x180002c39  add     rsp, 68h
0x180002c3d  jmp     short $+2
0x180002c3f  jmp     rax
```
