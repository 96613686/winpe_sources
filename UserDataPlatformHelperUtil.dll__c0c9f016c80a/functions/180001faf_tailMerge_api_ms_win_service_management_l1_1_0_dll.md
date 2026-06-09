# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180001faf`
- end: `0x180002028`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000202e`
- `0x180002040`
- `0x180002052`
- `0x1800022a2`

## callees

- `0x180001faf`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001faf  mov     [rsp+arg_0], rcx
0x180001fb4  mov     [rsp+arg_8], rdx
0x180001fb9  mov     [rsp+arg_10], r8
0x180001fbe  mov     [rsp+arg_18], r9
0x180001fc3  sub     rsp, 68h
0x180001fc7  movdqa  [rsp+68h+var_48], xmm0
0x180001fcd  movdqa  [rsp+68h+var_38], xmm1
0x180001fd3  movdqa  [rsp+68h+var_28], xmm2
0x180001fd9  movdqa  [rsp+68h+var_18], xmm3
0x180001fdf  mov     rdx, rax
0x180001fe2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180001fe9  call    __delayLoadHelper2
0x180001fee  movdqa  xmm0, [rsp+68h+var_48]
0x180001ff4  movdqa  xmm1, [rsp+68h+var_38]
0x180001ffa  movdqa  xmm2, [rsp+68h+var_28]
0x180002000  movdqa  xmm3, [rsp+68h+var_18]
0x180002006  mov     rcx, [rsp+68h+arg_0]
0x18000200b  mov     rdx, [rsp+68h+arg_8]
0x180002010  mov     r8, [rsp+68h+arg_10]
0x180002018  mov     r9, [rsp+68h+arg_18]
0x180002020  add     rsp, 68h
0x180002024  jmp     short $+2
0x180002026  jmp     rax
```
