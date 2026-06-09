# __tailMerge_api_ms_win_service_private_l1_1_3_dll

- ea: `0x1800020e9`
- end: `0x180002162`
- name: `__tailMerge_api_ms_win_service_private_l1_1_3_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002168`

## callees

- `0x1800020e9`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_private_l1_1_3_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_3_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800020e9  mov     [rsp+arg_0], rcx
0x1800020ee  mov     [rsp+arg_8], rdx
0x1800020f3  mov     [rsp+arg_10], r8
0x1800020f8  mov     [rsp+arg_18], r9
0x1800020fd  sub     rsp, 68h
0x180002101  movdqa  [rsp+68h+var_48], xmm0
0x180002107  movdqa  [rsp+68h+var_38], xmm1
0x18000210d  movdqa  [rsp+68h+var_28], xmm2
0x180002113  movdqa  [rsp+68h+var_18], xmm3
0x180002119  mov     rdx, rax
0x18000211c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_3_dll
0x180002123  call    __delayLoadHelper2
0x180002128  movdqa  xmm0, [rsp+68h+var_48]
0x18000212e  movdqa  xmm1, [rsp+68h+var_38]
0x180002134  movdqa  xmm2, [rsp+68h+var_28]
0x18000213a  movdqa  xmm3, [rsp+68h+var_18]
0x180002140  mov     rcx, [rsp+68h+arg_0]
0x180002145  mov     rdx, [rsp+68h+arg_8]
0x18000214a  mov     r8, [rsp+68h+arg_10]
0x180002152  mov     r9, [rsp+68h+arg_18]
0x18000215a  add     rsp, 68h
0x18000215e  jmp     short $+2
0x180002160  jmp     rax
```
