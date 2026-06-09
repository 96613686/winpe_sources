# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x180003747`
- end: `0x1800037c0`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800037c6`
- `0x1800037d8`

## callees

- `0x180003747`
- `0x180010a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003747  mov     [rsp+arg_0], rcx
0x18000374c  mov     [rsp+arg_8], rdx
0x180003751  mov     [rsp+arg_10], r8
0x180003756  mov     [rsp+arg_18], r9
0x18000375b  sub     rsp, 68h
0x18000375f  movdqa  [rsp+68h+var_48], xmm0
0x180003765  movdqa  [rsp+68h+var_38], xmm1
0x18000376b  movdqa  [rsp+68h+var_28], xmm2
0x180003771  movdqa  [rsp+68h+var_18], xmm3
0x180003777  mov     rdx, rax
0x18000377a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x180003781  call    __delayLoadHelper2
0x180003786  movdqa  xmm0, [rsp+68h+var_48]
0x18000378c  movdqa  xmm1, [rsp+68h+var_38]
0x180003792  movdqa  xmm2, [rsp+68h+var_28]
0x180003798  movdqa  xmm3, [rsp+68h+var_18]
0x18000379e  mov     rcx, [rsp+68h+arg_0]
0x1800037a3  mov     rdx, [rsp+68h+arg_8]
0x1800037a8  mov     r8, [rsp+68h+arg_10]
0x1800037b0  mov     r9, [rsp+68h+arg_18]
0x1800037b8  add     rsp, 68h
0x1800037bc  jmp     short $+2
0x1800037be  jmp     rax
```
