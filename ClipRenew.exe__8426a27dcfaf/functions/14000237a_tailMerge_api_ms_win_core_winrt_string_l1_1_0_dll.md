# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x14000237a`
- end: `0x1400023f3`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400023f9`
- `0x1400024a8`
- `0x1400024cc`

## callees

- `0x14000237a`
- `0x140013380`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000237a  mov     [rsp+arg_0], rcx
0x14000237f  mov     [rsp+arg_8], rdx
0x140002384  mov     [rsp+arg_10], r8
0x140002389  mov     [rsp+arg_18], r9
0x14000238e  sub     rsp, 68h
0x140002392  movdqa  [rsp+68h+var_48], xmm0
0x140002398  movdqa  [rsp+68h+var_38], xmm1
0x14000239e  movdqa  [rsp+68h+var_28], xmm2
0x1400023a4  movdqa  [rsp+68h+var_18], xmm3
0x1400023aa  mov     rdx, rax
0x1400023ad  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x1400023b4  call    __delayLoadHelper2
0x1400023b9  movdqa  xmm0, [rsp+68h+var_48]
0x1400023bf  movdqa  xmm1, [rsp+68h+var_38]
0x1400023c5  movdqa  xmm2, [rsp+68h+var_28]
0x1400023cb  movdqa  xmm3, [rsp+68h+var_18]
0x1400023d1  mov     rcx, [rsp+68h+arg_0]
0x1400023d6  mov     rdx, [rsp+68h+arg_8]
0x1400023db  mov     r8, [rsp+68h+arg_10]
0x1400023e3  mov     r9, [rsp+68h+arg_18]
0x1400023eb  add     rsp, 68h
0x1400023ef  jmp     short $+2
0x1400023f1  jmp     rax
```
