# __tailMerge_api_ms_win_service_private_l1_1_2_dll

- ea: `0x180002174`
- end: `0x1800021ed`
- name: `__tailMerge_api_ms_win_service_private_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800021f3`

## callees

- `0x180002174`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_private_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002174  mov     [rsp+arg_0], rcx
0x180002179  mov     [rsp+arg_8], rdx
0x18000217e  mov     [rsp+arg_10], r8
0x180002183  mov     [rsp+arg_18], r9
0x180002188  sub     rsp, 68h
0x18000218c  movdqa  [rsp+68h+var_48], xmm0
0x180002192  movdqa  [rsp+68h+var_38], xmm1
0x180002198  movdqa  [rsp+68h+var_28], xmm2
0x18000219e  movdqa  [rsp+68h+var_18], xmm3
0x1800021a4  mov     rdx, rax
0x1800021a7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_2_dll
0x1800021ae  call    __delayLoadHelper2
0x1800021b3  movdqa  xmm0, [rsp+68h+var_48]
0x1800021b9  movdqa  xmm1, [rsp+68h+var_38]
0x1800021bf  movdqa  xmm2, [rsp+68h+var_28]
0x1800021c5  movdqa  xmm3, [rsp+68h+var_18]
0x1800021cb  mov     rcx, [rsp+68h+arg_0]
0x1800021d0  mov     rdx, [rsp+68h+arg_8]
0x1800021d5  mov     r8, [rsp+68h+arg_10]
0x1800021dd  mov     r9, [rsp+68h+arg_18]
0x1800021e5  add     rsp, 68h
0x1800021e9  jmp     short $+2
0x1800021eb  jmp     rax
```
