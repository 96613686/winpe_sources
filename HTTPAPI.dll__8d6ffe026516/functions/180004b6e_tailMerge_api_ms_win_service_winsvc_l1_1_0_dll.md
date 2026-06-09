# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x180004b6e`
- end: `0x180004be7`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180004bed`

## callees

- `0x180004b6e`
- `0x18000a480`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004b6e  mov     [rsp+arg_0], rcx
0x180004b73  mov     [rsp+arg_8], rdx
0x180004b78  mov     [rsp+arg_10], r8
0x180004b7d  mov     [rsp+arg_18], r9
0x180004b82  sub     rsp, 68h
0x180004b86  movdqa  [rsp+68h+var_48], xmm0
0x180004b8c  movdqa  [rsp+68h+var_38], xmm1
0x180004b92  movdqa  [rsp+68h+var_28], xmm2
0x180004b98  movdqa  [rsp+68h+var_18], xmm3
0x180004b9e  mov     rdx, rax
0x180004ba1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x180004ba8  call    __delayLoadHelper2
0x180004bad  movdqa  xmm0, [rsp+68h+var_48]
0x180004bb3  movdqa  xmm1, [rsp+68h+var_38]
0x180004bb9  movdqa  xmm2, [rsp+68h+var_28]
0x180004bbf  movdqa  xmm3, [rsp+68h+var_18]
0x180004bc5  mov     rcx, [rsp+68h+arg_0]
0x180004bca  mov     rdx, [rsp+68h+arg_8]
0x180004bcf  mov     r8, [rsp+68h+arg_10]
0x180004bd7  mov     r9, [rsp+68h+arg_18]
0x180004bdf  add     rsp, 68h
0x180004be3  jmp     short $+2
0x180004be5  jmp     rax
```
