# __tailMerge_api_ms_win_service_management_l2_1_0_dll

- ea: `0x18000f484`
- end: `0x18000f4fd`
- name: `__tailMerge_api_ms_win_service_management_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000f503`
- `0x18000f515`
- `0x18000f527`

## callees

- `0x18000a5e0`
- `0x18000f484`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f484  mov     [rsp+arg_0], rcx
0x18000f489  mov     [rsp+arg_8], rdx
0x18000f48e  mov     [rsp+arg_10], r8
0x18000f493  mov     [rsp+arg_18], r9
0x18000f498  sub     rsp, 68h
0x18000f49c  movdqa  [rsp+68h+var_48], xmm0
0x18000f4a2  movdqa  [rsp+68h+var_38], xmm1
0x18000f4a8  movdqa  [rsp+68h+var_28], xmm2
0x18000f4ae  movdqa  [rsp+68h+var_18], xmm3
0x18000f4b4  mov     rdx, rax
0x18000f4b7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll
0x18000f4be  call    __delayLoadHelper2
0x18000f4c3  movdqa  xmm0, [rsp+68h+var_48]
0x18000f4c9  movdqa  xmm1, [rsp+68h+var_38]
0x18000f4cf  movdqa  xmm2, [rsp+68h+var_28]
0x18000f4d5  movdqa  xmm3, [rsp+68h+var_18]
0x18000f4db  mov     rcx, [rsp+68h+arg_0]
0x18000f4e0  mov     rdx, [rsp+68h+arg_8]
0x18000f4e5  mov     r8, [rsp+68h+arg_10]
0x18000f4ed  mov     r9, [rsp+68h+arg_18]
0x18000f4f5  add     rsp, 68h
0x18000f4f9  jmp     short $+2
0x18000f4fb  jmp     rax
```
