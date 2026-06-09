# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180011366`
- end: `0x1800113df`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800113e5`
- `0x180011494`
- `0x1800114a6`

## callees

- `0x18000f240`
- `0x180011366`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180011366  mov     [rsp+arg_0], rcx
0x18001136b  mov     [rsp+arg_8], rdx
0x180011370  mov     [rsp+arg_10], r8
0x180011375  mov     [rsp+arg_18], r9
0x18001137a  sub     rsp, 68h
0x18001137e  movdqa  [rsp+68h+var_48], xmm0
0x180011384  movdqa  [rsp+68h+var_38], xmm1
0x18001138a  movdqa  [rsp+68h+var_28], xmm2
0x180011390  movdqa  [rsp+68h+var_18], xmm3
0x180011396  mov     rdx, rax
0x180011399  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x1800113a0  call    __delayLoadHelper2
0x1800113a5  movdqa  xmm0, [rsp+68h+var_48]
0x1800113ab  movdqa  xmm1, [rsp+68h+var_38]
0x1800113b1  movdqa  xmm2, [rsp+68h+var_28]
0x1800113b7  movdqa  xmm3, [rsp+68h+var_18]
0x1800113bd  mov     rcx, [rsp+68h+arg_0]
0x1800113c2  mov     rdx, [rsp+68h+arg_8]
0x1800113c7  mov     r8, [rsp+68h+arg_10]
0x1800113cf  mov     r9, [rsp+68h+arg_18]
0x1800113d7  add     rsp, 68h
0x1800113db  jmp     short $+2
0x1800113dd  jmp     rax
```
