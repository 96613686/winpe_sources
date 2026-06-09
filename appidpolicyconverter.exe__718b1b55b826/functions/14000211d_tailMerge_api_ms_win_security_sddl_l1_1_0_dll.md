# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x14000211d`
- end: `0x140002196`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000219c`

## callees

- `0x14000211d`
- `0x140009150`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000211d  mov     [rsp+arg_0], rcx
0x140002122  mov     [rsp+arg_8], rdx
0x140002127  mov     [rsp+arg_10], r8
0x14000212c  mov     [rsp+arg_18], r9
0x140002131  sub     rsp, 68h
0x140002135  movdqa  [rsp+68h+var_48], xmm0
0x14000213b  movdqa  [rsp+68h+var_38], xmm1
0x140002141  movdqa  [rsp+68h+var_28], xmm2
0x140002147  movdqa  [rsp+68h+var_18], xmm3
0x14000214d  mov     rdx, rax
0x140002150  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x140002157  call    __delayLoadHelper2
0x14000215c  movdqa  xmm0, [rsp+68h+var_48]
0x140002162  movdqa  xmm1, [rsp+68h+var_38]
0x140002168  movdqa  xmm2, [rsp+68h+var_28]
0x14000216e  movdqa  xmm3, [rsp+68h+var_18]
0x140002174  mov     rcx, [rsp+68h+arg_0]
0x140002179  mov     rdx, [rsp+68h+arg_8]
0x14000217e  mov     r8, [rsp+68h+arg_10]
0x140002186  mov     r9, [rsp+68h+arg_18]
0x14000218e  add     rsp, 68h
0x140002192  jmp     short $+2
0x140002194  jmp     rax
```
