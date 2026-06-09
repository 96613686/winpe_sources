# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x140002e66`
- end: `0x140002edf`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140002ee5`

## callees

- `0x140002e66`
- `0x140010d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002e66  mov     [rsp+arg_0], rcx
0x140002e6b  mov     [rsp+arg_8], rdx
0x140002e70  mov     [rsp+arg_10], r8
0x140002e75  mov     [rsp+arg_18], r9
0x140002e7a  sub     rsp, 68h
0x140002e7e  movdqa  [rsp+68h+var_48], xmm0
0x140002e84  movdqa  [rsp+68h+var_38], xmm1
0x140002e8a  movdqa  [rsp+68h+var_28], xmm2
0x140002e90  movdqa  [rsp+68h+var_18], xmm3
0x140002e96  mov     rdx, rax
0x140002e99  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x140002ea0  call    __delayLoadHelper2
0x140002ea5  movdqa  xmm0, [rsp+68h+var_48]
0x140002eab  movdqa  xmm1, [rsp+68h+var_38]
0x140002eb1  movdqa  xmm2, [rsp+68h+var_28]
0x140002eb7  movdqa  xmm3, [rsp+68h+var_18]
0x140002ebd  mov     rcx, [rsp+68h+arg_0]
0x140002ec2  mov     rdx, [rsp+68h+arg_8]
0x140002ec7  mov     r8, [rsp+68h+arg_10]
0x140002ecf  mov     r9, [rsp+68h+arg_18]
0x140002ed7  add     rsp, 68h
0x140002edb  jmp     short $+2
0x140002edd  jmp     rax
```
