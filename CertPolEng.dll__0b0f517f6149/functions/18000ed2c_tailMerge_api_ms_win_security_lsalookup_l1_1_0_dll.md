# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x18000ed2c`
- end: `0x18000eda5`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000edab`

## callees

- `0x180008870`
- `0x18000ed2c`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ed2c  mov     [rsp+arg_0], rcx
0x18000ed31  mov     [rsp+arg_8], rdx
0x18000ed36  mov     [rsp+arg_10], r8
0x18000ed3b  mov     [rsp+arg_18], r9
0x18000ed40  sub     rsp, 68h
0x18000ed44  movdqa  [rsp+68h+var_48], xmm0
0x18000ed4a  movdqa  [rsp+68h+var_38], xmm1
0x18000ed50  movdqa  [rsp+68h+var_28], xmm2
0x18000ed56  movdqa  [rsp+68h+var_18], xmm3
0x18000ed5c  mov     rdx, rax
0x18000ed5f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x18000ed66  call    __delayLoadHelper2
0x18000ed6b  movdqa  xmm0, [rsp+68h+var_48]
0x18000ed71  movdqa  xmm1, [rsp+68h+var_38]
0x18000ed77  movdqa  xmm2, [rsp+68h+var_28]
0x18000ed7d  movdqa  xmm3, [rsp+68h+var_18]
0x18000ed83  mov     rcx, [rsp+68h+arg_0]
0x18000ed88  mov     rdx, [rsp+68h+arg_8]
0x18000ed8d  mov     r8, [rsp+68h+arg_10]
0x18000ed95  mov     r9, [rsp+68h+arg_18]
0x18000ed9d  add     rsp, 68h
0x18000eda1  jmp     short $+2
0x18000eda3  jmp     rax
```
