# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x18000531a`
- end: `0x180005393`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180005399`

## callees

- `0x180004570`
- `0x18000531a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000531a  mov     [rsp+arg_0], rcx
0x18000531f  mov     [rsp+arg_8], rdx
0x180005324  mov     [rsp+arg_10], r8
0x180005329  mov     [rsp+arg_18], r9
0x18000532e  sub     rsp, 68h
0x180005332  movdqa  [rsp+68h+var_48], xmm0
0x180005338  movdqa  [rsp+68h+var_38], xmm1
0x18000533e  movdqa  [rsp+68h+var_28], xmm2
0x180005344  movdqa  [rsp+68h+var_18], xmm3
0x18000534a  mov     rdx, rax
0x18000534d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x180005354  call    __delayLoadHelper2
0x180005359  movdqa  xmm0, [rsp+68h+var_48]
0x18000535f  movdqa  xmm1, [rsp+68h+var_38]
0x180005365  movdqa  xmm2, [rsp+68h+var_28]
0x18000536b  movdqa  xmm3, [rsp+68h+var_18]
0x180005371  mov     rcx, [rsp+68h+arg_0]
0x180005376  mov     rdx, [rsp+68h+arg_8]
0x18000537b  mov     r8, [rsp+68h+arg_10]
0x180005383  mov     r9, [rsp+68h+arg_18]
0x18000538b  add     rsp, 68h
0x18000538f  jmp     short $+2
0x180005391  jmp     rax
```
