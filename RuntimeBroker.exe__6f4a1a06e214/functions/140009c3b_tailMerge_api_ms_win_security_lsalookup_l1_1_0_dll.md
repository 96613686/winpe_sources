# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x140009c3b`
- end: `0x140009cb4`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009cba`
- `0x140009ccc`
- `0x140009d69`
- `0x140009d7b`

## callees

- `0x140006ad0`
- `0x140009c3b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140009c3b  mov     [rsp+arg_0], rcx
0x140009c40  mov     [rsp+arg_8], rdx
0x140009c45  mov     [rsp+arg_10], r8
0x140009c4a  mov     [rsp+arg_18], r9
0x140009c4f  sub     rsp, 68h
0x140009c53  movdqa  [rsp+68h+var_48], xmm0
0x140009c59  movdqa  [rsp+68h+var_38], xmm1
0x140009c5f  movdqa  [rsp+68h+var_28], xmm2
0x140009c65  movdqa  [rsp+68h+var_18], xmm3
0x140009c6b  mov     rdx, rax
0x140009c6e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x140009c75  call    __delayLoadHelper2
0x140009c7a  movdqa  xmm0, [rsp+68h+var_48]
0x140009c80  movdqa  xmm1, [rsp+68h+var_38]
0x140009c86  movdqa  xmm2, [rsp+68h+var_28]
0x140009c8c  movdqa  xmm3, [rsp+68h+var_18]
0x140009c92  mov     rcx, [rsp+68h+arg_0]
0x140009c97  mov     rdx, [rsp+68h+arg_8]
0x140009c9c  mov     r8, [rsp+68h+arg_10]
0x140009ca4  mov     r9, [rsp+68h+arg_18]
0x140009cac  add     rsp, 68h
0x140009cb0  jmp     short $+2
0x140009cb2  jmp     rax
```
