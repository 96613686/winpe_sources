# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x180004736`
- end: `0x1800047af`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800047b5`
- `0x1800047dc`
- `0x1800047fc`
- `0x18000482c`
- `0x18000484c`
- `0x18000487c`
- `0x18000489c`
- `0x1800048bc`

## callees

- `0x180002420`
- `0x180004736`

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
0x180004736  mov     [rsp+arg_0], rcx
0x18000473b  mov     [rsp+arg_8], rdx
0x180004740  mov     [rsp+arg_10], r8
0x180004745  mov     [rsp+arg_18], r9
0x18000474a  sub     rsp, 68h
0x18000474e  movdqa  [rsp+68h+var_48], xmm0
0x180004754  movdqa  [rsp+68h+var_38], xmm1
0x18000475a  movdqa  [rsp+68h+var_28], xmm2
0x180004760  movdqa  [rsp+68h+var_18], xmm3
0x180004766  mov     rdx, rax
0x180004769  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x180004770  call    __delayLoadHelper2
0x180004775  movdqa  xmm0, [rsp+68h+var_48]
0x18000477b  movdqa  xmm1, [rsp+68h+var_38]
0x180004781  movdqa  xmm2, [rsp+68h+var_28]
0x180004787  movdqa  xmm3, [rsp+68h+var_18]
0x18000478d  mov     rcx, [rsp+68h+arg_0]
0x180004792  mov     rdx, [rsp+68h+arg_8]
0x180004797  mov     r8, [rsp+68h+arg_10]
0x18000479f  mov     r9, [rsp+68h+arg_18]
0x1800047a7  add     rsp, 68h
0x1800047ab  jmp     short $+2
0x1800047ad  jmp     rax
```
