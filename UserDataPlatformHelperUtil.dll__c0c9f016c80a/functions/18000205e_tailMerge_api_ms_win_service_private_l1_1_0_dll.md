# __tailMerge_api_ms_win_service_private_l1_1_0_dll

- ea: `0x18000205e`
- end: `0x1800020d7`
- name: `__tailMerge_api_ms_win_service_private_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800020dd`

## callees

- `0x18000205e`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_private_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000205e  mov     [rsp+arg_0], rcx
0x180002063  mov     [rsp+arg_8], rdx
0x180002068  mov     [rsp+arg_10], r8
0x18000206d  mov     [rsp+arg_18], r9
0x180002072  sub     rsp, 68h
0x180002076  movdqa  [rsp+68h+var_48], xmm0
0x18000207c  movdqa  [rsp+68h+var_38], xmm1
0x180002082  movdqa  [rsp+68h+var_28], xmm2
0x180002088  movdqa  [rsp+68h+var_18], xmm3
0x18000208e  mov     rdx, rax
0x180002091  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_0_dll
0x180002098  call    __delayLoadHelper2
0x18000209d  movdqa  xmm0, [rsp+68h+var_48]
0x1800020a3  movdqa  xmm1, [rsp+68h+var_38]
0x1800020a9  movdqa  xmm2, [rsp+68h+var_28]
0x1800020af  movdqa  xmm3, [rsp+68h+var_18]
0x1800020b5  mov     rcx, [rsp+68h+arg_0]
0x1800020ba  mov     rdx, [rsp+68h+arg_8]
0x1800020bf  mov     r8, [rsp+68h+arg_10]
0x1800020c7  mov     r9, [rsp+68h+arg_18]
0x1800020cf  add     rsp, 68h
0x1800020d3  jmp     short $+2
0x1800020d5  jmp     rax
```
