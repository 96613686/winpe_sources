# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x18000ad88`
- end: `0x18000ae01`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000ae07`
- `0x18000ae3d`
- `0x18000aefe`
- `0x18000af10`

## callees

- `0x180001530`
- `0x18000ad88`

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
0x18000ad88  mov     [rsp+arg_0], rcx
0x18000ad8d  mov     [rsp+arg_8], rdx
0x18000ad92  mov     [rsp+arg_10], r8
0x18000ad97  mov     [rsp+arg_18], r9
0x18000ad9c  sub     rsp, 68h
0x18000ada0  movdqa  [rsp+68h+var_48], xmm0
0x18000ada6  movdqa  [rsp+68h+var_38], xmm1
0x18000adac  movdqa  [rsp+68h+var_28], xmm2
0x18000adb2  movdqa  [rsp+68h+var_18], xmm3
0x18000adb8  mov     rdx, rax
0x18000adbb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x18000adc2  call    __delayLoadHelper2
0x18000adc7  movdqa  xmm0, [rsp+68h+var_48]
0x18000adcd  movdqa  xmm1, [rsp+68h+var_38]
0x18000add3  movdqa  xmm2, [rsp+68h+var_28]
0x18000add9  movdqa  xmm3, [rsp+68h+var_18]
0x18000addf  mov     rcx, [rsp+68h+arg_0]
0x18000ade4  mov     rdx, [rsp+68h+arg_8]
0x18000ade9  mov     r8, [rsp+68h+arg_10]
0x18000adf1  mov     r9, [rsp+68h+arg_18]
0x18000adf9  add     rsp, 68h
0x18000adfd  jmp     short $+2
0x18000adff  jmp     rax
```
