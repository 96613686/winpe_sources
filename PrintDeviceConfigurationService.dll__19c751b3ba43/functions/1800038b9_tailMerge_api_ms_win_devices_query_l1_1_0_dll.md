# __tailMerge_api_ms_win_devices_query_l1_1_0_dll

- ea: `0x1800038b9`
- end: `0x180003932`
- name: `__tailMerge_api_ms_win_devices_query_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003938`
- `0x18000394a`
- `0x18000395c`
- `0x180003a96`
- `0x180003aa8`

## callees

- `0x1800038b9`
- `0x180016410`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800038b9  mov     [rsp+arg_0], rcx
0x1800038be  mov     [rsp+arg_8], rdx
0x1800038c3  mov     [rsp+arg_10], r8
0x1800038c8  mov     [rsp+arg_18], r9
0x1800038cd  sub     rsp, 68h
0x1800038d1  movdqa  [rsp+68h+var_48], xmm0
0x1800038d7  movdqa  [rsp+68h+var_38], xmm1
0x1800038dd  movdqa  [rsp+68h+var_28], xmm2
0x1800038e3  movdqa  [rsp+68h+var_18], xmm3
0x1800038e9  mov     rdx, rax
0x1800038ec  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll
0x1800038f3  call    __delayLoadHelper2
0x1800038f8  movdqa  xmm0, [rsp+68h+var_48]
0x1800038fe  movdqa  xmm1, [rsp+68h+var_38]
0x180003904  movdqa  xmm2, [rsp+68h+var_28]
0x18000390a  movdqa  xmm3, [rsp+68h+var_18]
0x180003910  mov     rcx, [rsp+68h+arg_0]
0x180003915  mov     rdx, [rsp+68h+arg_8]
0x18000391a  mov     r8, [rsp+68h+arg_10]
0x180003922  mov     r9, [rsp+68h+arg_18]
0x18000392a  add     rsp, 68h
0x18000392e  jmp     short $+2
0x180003930  jmp     rax
```
