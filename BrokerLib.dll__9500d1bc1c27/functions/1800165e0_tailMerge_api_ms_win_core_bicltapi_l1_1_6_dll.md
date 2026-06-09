# __tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll

- ea: `0x1800165e0`
- end: `0x180016659`
- name: `__tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001665f`
- `0x180016671`
- `0x180016683`
- `0x180016695`
- `0x1800166a7`
- `0x1800166b9`
- `0x1800166cb`
- `0x1800166dd`
- `0x1800166ef`

## callees

- `0x180011810`
- `0x1800165e0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_bicltapi_l1_1_6_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800165e0  mov     [rsp+arg_0], rcx
0x1800165e5  mov     [rsp+arg_8], rdx
0x1800165ea  mov     [rsp+arg_10], r8
0x1800165ef  mov     [rsp+arg_18], r9
0x1800165f4  sub     rsp, 68h
0x1800165f8  movdqa  [rsp+68h+var_48], xmm0
0x1800165fe  movdqa  [rsp+68h+var_38], xmm1
0x180016604  movdqa  [rsp+68h+var_28], xmm2
0x18001660a  movdqa  [rsp+68h+var_18], xmm3
0x180016610  mov     rdx, rax
0x180016613  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_bicltapi_l1_1_6_dll
0x18001661a  call    __delayLoadHelper2
0x18001661f  movdqa  xmm0, [rsp+68h+var_48]
0x180016625  movdqa  xmm1, [rsp+68h+var_38]
0x18001662b  movdqa  xmm2, [rsp+68h+var_28]
0x180016631  movdqa  xmm3, [rsp+68h+var_18]
0x180016637  mov     rcx, [rsp+68h+arg_0]
0x18001663c  mov     rdx, [rsp+68h+arg_8]
0x180016641  mov     r8, [rsp+68h+arg_10]
0x180016649  mov     r9, [rsp+68h+arg_18]
0x180016651  add     rsp, 68h
0x180016655  jmp     short $+2
0x180016657  jmp     rax
```
