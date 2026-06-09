# __tailMerge_api_ms_win_core_localization_l1_2_0_dll

- ea: `0x18000e98c`
- end: `0x18000ea05`
- name: `__tailMerge_api_ms_win_core_localization_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ea0b`
- `0x18001500b`
- `0x18001501d`

## callees

- `0x18000e98c`
- `0x180014c80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_localization_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_localization_l1_2_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e98c  mov     [rsp+arg_0], rcx
0x18000e991  mov     [rsp+arg_8], rdx
0x18000e996  mov     [rsp+arg_10], r8
0x18000e99b  mov     [rsp+arg_18], r9
0x18000e9a0  sub     rsp, 68h
0x18000e9a4  movdqa  [rsp+68h+var_48], xmm0
0x18000e9aa  movdqa  [rsp+68h+var_38], xmm1
0x18000e9b0  movdqa  [rsp+68h+var_28], xmm2
0x18000e9b6  movdqa  [rsp+68h+var_18], xmm3
0x18000e9bc  mov     rdx, rax
0x18000e9bf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_localization_l1_2_0_dll
0x18000e9c6  call    __delayLoadHelper2
0x18000e9cb  movdqa  xmm0, [rsp+68h+var_48]
0x18000e9d1  movdqa  xmm1, [rsp+68h+var_38]
0x18000e9d7  movdqa  xmm2, [rsp+68h+var_28]
0x18000e9dd  movdqa  xmm3, [rsp+68h+var_18]
0x18000e9e3  mov     rcx, [rsp+68h+arg_0]
0x18000e9e8  mov     rdx, [rsp+68h+arg_8]
0x18000e9ed  mov     r8, [rsp+68h+arg_10]
0x18000e9f5  mov     r9, [rsp+68h+arg_18]
0x18000e9fd  add     rsp, 68h
0x18000ea01  jmp     short $+2
0x18000ea03  jmp     rax
```
