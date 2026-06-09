# __tailMerge_api_ms_win_service_management_l2_1_0_dll

- ea: `0x18000211c`
- end: `0x180002195`
- name: `__tailMerge_api_ms_win_service_management_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800021a0`

## callees

- `0x18000211c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000211c  mov     [rsp+arg_0], rcx
0x180002121  mov     [rsp+arg_8], rdx
0x180002126  mov     [rsp+arg_10], r8
0x18000212b  mov     [rsp+arg_18], r9
0x180002130  sub     rsp, 68h
0x180002134  movdqa  [rsp+68h+var_48], xmm0
0x18000213a  movdqa  [rsp+68h+var_38], xmm1
0x180002140  movdqa  [rsp+68h+var_28], xmm2
0x180002146  movdqa  [rsp+68h+var_18], xmm3
0x18000214c  mov     rdx, rax
0x18000214f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l2_1_0_dll
0x180002156  call    __delayLoadHelper2
0x18000215b  movdqa  xmm0, [rsp+68h+var_48]
0x180002161  movdqa  xmm1, [rsp+68h+var_38]
0x180002167  movdqa  xmm2, [rsp+68h+var_28]
0x18000216d  movdqa  xmm3, [rsp+68h+var_18]
0x180002173  mov     rcx, [rsp+68h+arg_0]
0x180002178  mov     rdx, [rsp+68h+arg_8]
0x18000217d  mov     r8, [rsp+68h+arg_10]
0x180002185  mov     r9, [rsp+68h+arg_18]
0x18000218d  add     rsp, 68h
0x180002191  jmp     short $+2
0x180002193  jmp     rax
```
