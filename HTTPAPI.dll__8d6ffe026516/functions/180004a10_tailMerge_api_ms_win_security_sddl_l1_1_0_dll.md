# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x180004a10`
- end: `0x180004a89`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004a8f`
- `0x180004aa1`

## callees

- `0x180004a10`
- `0x18000a480`

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
0x180004a10  mov     [rsp+arg_0], rcx
0x180004a15  mov     [rsp+arg_8], rdx
0x180004a1a  mov     [rsp+arg_10], r8
0x180004a1f  mov     [rsp+arg_18], r9
0x180004a24  sub     rsp, 68h
0x180004a28  movdqa  [rsp+68h+var_48], xmm0
0x180004a2e  movdqa  [rsp+68h+var_38], xmm1
0x180004a34  movdqa  [rsp+68h+var_28], xmm2
0x180004a3a  movdqa  [rsp+68h+var_18], xmm3
0x180004a40  mov     rdx, rax
0x180004a43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x180004a4a  call    __delayLoadHelper2
0x180004a4f  movdqa  xmm0, [rsp+68h+var_48]
0x180004a55  movdqa  xmm1, [rsp+68h+var_38]
0x180004a5b  movdqa  xmm2, [rsp+68h+var_28]
0x180004a61  movdqa  xmm3, [rsp+68h+var_18]
0x180004a67  mov     rcx, [rsp+68h+arg_0]
0x180004a6c  mov     rdx, [rsp+68h+arg_8]
0x180004a71  mov     r8, [rsp+68h+arg_10]
0x180004a79  mov     r9, [rsp+68h+arg_18]
0x180004a81  add     rsp, 68h
0x180004a85  jmp     short $+2
0x180004a87  jmp     rax
```
