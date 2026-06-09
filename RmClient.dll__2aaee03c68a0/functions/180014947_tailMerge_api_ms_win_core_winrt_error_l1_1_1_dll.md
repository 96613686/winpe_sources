# __tailMerge_api_ms_win_core_winrt_error_l1_1_1_dll

- ea: `0x180014947`
- end: `0x1800149c0`
- name: `__tailMerge_api_ms_win_core_winrt_error_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800149c6`
- `0x1800149d8`
- `0x1800149ea`

## callees

- `0x18000f260`
- `0x180014947`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_error_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_error_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180014947  mov     [rsp+arg_0], rcx
0x18001494c  mov     [rsp+arg_8], rdx
0x180014951  mov     [rsp+arg_10], r8
0x180014956  mov     [rsp+arg_18], r9
0x18001495b  sub     rsp, 68h
0x18001495f  movdqa  [rsp+68h+var_48], xmm0
0x180014965  movdqa  [rsp+68h+var_38], xmm1
0x18001496b  movdqa  [rsp+68h+var_28], xmm2
0x180014971  movdqa  [rsp+68h+var_18], xmm3
0x180014977  mov     rdx, rax
0x18001497a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_error_l1_1_1_dll
0x180014981  call    __delayLoadHelper2
0x180014986  movdqa  xmm0, [rsp+68h+var_48]
0x18001498c  movdqa  xmm1, [rsp+68h+var_38]
0x180014992  movdqa  xmm2, [rsp+68h+var_28]
0x180014998  movdqa  xmm3, [rsp+68h+var_18]
0x18001499e  mov     rcx, [rsp+68h+arg_0]
0x1800149a3  mov     rdx, [rsp+68h+arg_8]
0x1800149a8  mov     r8, [rsp+68h+arg_10]
0x1800149b0  mov     r9, [rsp+68h+arg_18]
0x1800149b8  add     rsp, 68h
0x1800149bc  jmp     short $+2
0x1800149be  jmp     rax
```
