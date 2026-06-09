# __tailMerge_api_ms_win_core_winrt_error_l1_1_0_dll

- ea: `0x1400097c2`
- end: `0x14000983b`
- name: `__tailMerge_api_ms_win_core_winrt_error_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009841`
- `0x140009a96`
- `0x140009af0`
- `0x140009b26`

## callees

- `0x140006ad0`
- `0x1400097c2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_error_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_error_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400097c2  mov     [rsp+arg_0], rcx
0x1400097c7  mov     [rsp+arg_8], rdx
0x1400097cc  mov     [rsp+arg_10], r8
0x1400097d1  mov     [rsp+arg_18], r9
0x1400097d6  sub     rsp, 68h
0x1400097da  movdqa  [rsp+68h+var_48], xmm0
0x1400097e0  movdqa  [rsp+68h+var_38], xmm1
0x1400097e6  movdqa  [rsp+68h+var_28], xmm2
0x1400097ec  movdqa  [rsp+68h+var_18], xmm3
0x1400097f2  mov     rdx, rax
0x1400097f5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_error_l1_1_0_dll
0x1400097fc  call    __delayLoadHelper2
0x140009801  movdqa  xmm0, [rsp+68h+var_48]
0x140009807  movdqa  xmm1, [rsp+68h+var_38]
0x14000980d  movdqa  xmm2, [rsp+68h+var_28]
0x140009813  movdqa  xmm3, [rsp+68h+var_18]
0x140009819  mov     rcx, [rsp+68h+arg_0]
0x14000981e  mov     rdx, [rsp+68h+arg_8]
0x140009823  mov     r8, [rsp+68h+arg_10]
0x14000982b  mov     r9, [rsp+68h+arg_18]
0x140009833  add     rsp, 68h
0x140009837  jmp     short $+2
0x140009839  jmp     rax
```
