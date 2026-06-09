# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180055401`
- end: `0x18005547a`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055480`
- `0x180055492`
- `0x1800554a4`
- `0x1800554b6`
- `0x1800554c8`
- `0x1800554da`
- `0x1800554ec`
- `0x1800554fe`
- `0x180055510`

## callees

- `0x180044730`
- `0x180055401`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180055401  mov     [rsp+arg_0], rcx
0x180055406  mov     [rsp+arg_8], rdx
0x18005540b  mov     [rsp+arg_10], r8
0x180055410  mov     [rsp+arg_18], r9
0x180055415  sub     rsp, 68h
0x180055419  movdqa  [rsp+68h+var_48], xmm0
0x18005541f  movdqa  [rsp+68h+var_38], xmm1
0x180055425  movdqa  [rsp+68h+var_28], xmm2
0x18005542b  movdqa  [rsp+68h+var_18], xmm3
0x180055431  mov     rdx, rax
0x180055434  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18005543b  call    __delayLoadHelper2
0x180055440  movdqa  xmm0, [rsp+68h+var_48]
0x180055446  movdqa  xmm1, [rsp+68h+var_38]
0x18005544c  movdqa  xmm2, [rsp+68h+var_28]
0x180055452  movdqa  xmm3, [rsp+68h+var_18]
0x180055458  mov     rcx, [rsp+68h+arg_0]
0x18005545d  mov     rdx, [rsp+68h+arg_8]
0x180055462  mov     r8, [rsp+68h+arg_10]
0x18005546a  mov     r9, [rsp+68h+arg_18]
0x180055472  add     rsp, 68h
0x180055476  jmp     short $+2
0x180055478  jmp     rax
```
