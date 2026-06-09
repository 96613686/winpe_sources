# __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll

- ea: `0x18000aedb`
- end: `0x18000af54`
- name: `__tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000af5a`

## callees

- `0x180006050`
- `0x18000aedb`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aedb  mov     [rsp+arg_0], rcx
0x18000aee0  mov     [rsp+arg_8], rdx
0x18000aee5  mov     [rsp+arg_10], r8
0x18000aeea  mov     [rsp+arg_18], r9
0x18000aeef  sub     rsp, 68h
0x18000aef3  movdqa  [rsp+68h+var_48], xmm0
0x18000aef9  movdqa  [rsp+68h+var_38], xmm1
0x18000aeff  movdqa  [rsp+68h+var_28], xmm2
0x18000af05  movdqa  [rsp+68h+var_18], xmm3
0x18000af0b  mov     rdx, rax
0x18000af0e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_0_dll
0x18000af15  call    __delayLoadHelper2
0x18000af1a  movdqa  xmm0, [rsp+68h+var_48]
0x18000af20  movdqa  xmm1, [rsp+68h+var_38]
0x18000af26  movdqa  xmm2, [rsp+68h+var_28]
0x18000af2c  movdqa  xmm3, [rsp+68h+var_18]
0x18000af32  mov     rcx, [rsp+68h+arg_0]
0x18000af37  mov     rdx, [rsp+68h+arg_8]
0x18000af3c  mov     r8, [rsp+68h+arg_10]
0x18000af44  mov     r9, [rsp+68h+arg_18]
0x18000af4c  add     rsp, 68h
0x18000af50  jmp     short $+2
0x18000af52  jmp     rax
```
