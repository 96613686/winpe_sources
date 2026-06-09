# __tailMerge_api_ms_win_power_setting_l1_1_0_dll

- ea: `0x140009725`
- end: `0x14000979e`
- name: `__tailMerge_api_ms_win_power_setting_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400097a4`
- `0x140009b4a`

## callees

- `0x140006ad0`
- `0x140009725`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_power_setting_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_setting_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140009725  mov     [rsp+arg_0], rcx
0x14000972a  mov     [rsp+arg_8], rdx
0x14000972f  mov     [rsp+arg_10], r8
0x140009734  mov     [rsp+arg_18], r9
0x140009739  sub     rsp, 68h
0x14000973d  movdqa  [rsp+68h+var_48], xmm0
0x140009743  movdqa  [rsp+68h+var_38], xmm1
0x140009749  movdqa  [rsp+68h+var_28], xmm2
0x14000974f  movdqa  [rsp+68h+var_18], xmm3
0x140009755  mov     rdx, rax
0x140009758  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_power_setting_l1_1_0_dll
0x14000975f  call    __delayLoadHelper2
0x140009764  movdqa  xmm0, [rsp+68h+var_48]
0x14000976a  movdqa  xmm1, [rsp+68h+var_38]
0x140009770  movdqa  xmm2, [rsp+68h+var_28]
0x140009776  movdqa  xmm3, [rsp+68h+var_18]
0x14000977c  mov     rcx, [rsp+68h+arg_0]
0x140009781  mov     rdx, [rsp+68h+arg_8]
0x140009786  mov     r8, [rsp+68h+arg_10]
0x14000978e  mov     r9, [rsp+68h+arg_18]
0x140009796  add     rsp, 68h
0x14000979a  jmp     short $+2
0x14000979c  jmp     rax
```
