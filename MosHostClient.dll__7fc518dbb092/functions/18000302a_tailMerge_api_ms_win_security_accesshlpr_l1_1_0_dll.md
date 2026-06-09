# __tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll

- ea: `0x18000302a`
- end: `0x1800030a3`
- name: `__tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030a9`
- `0x1800030bb`

## callees

- `0x18000302a`
- `0x180010f00`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_accesshlpr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000302a  mov     [rsp+arg_0], rcx
0x18000302f  mov     [rsp+arg_8], rdx
0x180003034  mov     [rsp+arg_10], r8
0x180003039  mov     [rsp+arg_18], r9
0x18000303e  sub     rsp, 68h
0x180003042  movdqa  [rsp+68h+var_48], xmm0
0x180003048  movdqa  [rsp+68h+var_38], xmm1
0x18000304e  movdqa  [rsp+68h+var_28], xmm2
0x180003054  movdqa  [rsp+68h+var_18], xmm3
0x18000305a  mov     rdx, rax
0x18000305d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_accesshlpr_l1_1_0_dll
0x180003064  call    __delayLoadHelper2
0x180003069  movdqa  xmm0, [rsp+68h+var_48]
0x18000306f  movdqa  xmm1, [rsp+68h+var_38]
0x180003075  movdqa  xmm2, [rsp+68h+var_28]
0x18000307b  movdqa  xmm3, [rsp+68h+var_18]
0x180003081  mov     rcx, [rsp+68h+arg_0]
0x180003086  mov     rdx, [rsp+68h+arg_8]
0x18000308b  mov     r8, [rsp+68h+arg_10]
0x180003093  mov     r9, [rsp+68h+arg_18]
0x18000309b  add     rsp, 68h
0x18000309f  jmp     short $+2
0x1800030a1  jmp     rax
```
