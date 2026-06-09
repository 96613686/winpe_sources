# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180004aad`
- end: `0x180004b26`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180004b2c`
- `0x180004b3e`
- `0x180004b50`
- `0x180004b62`

## callees

- `0x180004aad`
- `0x18000a480`

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
0x180004aad  mov     [rsp+arg_0], rcx
0x180004ab2  mov     [rsp+arg_8], rdx
0x180004ab7  mov     [rsp+arg_10], r8
0x180004abc  mov     [rsp+arg_18], r9
0x180004ac1  sub     rsp, 68h
0x180004ac5  movdqa  [rsp+68h+var_48], xmm0
0x180004acb  movdqa  [rsp+68h+var_38], xmm1
0x180004ad1  movdqa  [rsp+68h+var_28], xmm2
0x180004ad7  movdqa  [rsp+68h+var_18], xmm3
0x180004add  mov     rdx, rax
0x180004ae0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180004ae7  call    __delayLoadHelper2
0x180004aec  movdqa  xmm0, [rsp+68h+var_48]
0x180004af2  movdqa  xmm1, [rsp+68h+var_38]
0x180004af8  movdqa  xmm2, [rsp+68h+var_28]
0x180004afe  movdqa  xmm3, [rsp+68h+var_18]
0x180004b04  mov     rcx, [rsp+68h+arg_0]
0x180004b09  mov     rdx, [rsp+68h+arg_8]
0x180004b0e  mov     r8, [rsp+68h+arg_10]
0x180004b16  mov     r9, [rsp+68h+arg_18]
0x180004b1e  add     rsp, 68h
0x180004b22  jmp     short $+2
0x180004b24  jmp     rax
```
