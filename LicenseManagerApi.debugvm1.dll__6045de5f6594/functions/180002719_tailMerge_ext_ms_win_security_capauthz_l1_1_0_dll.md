# __tailMerge_ext_ms_win_security_capauthz_l1_1_0_dll

- ea: `0x180002719`
- end: `0x180002792`
- name: `__tailMerge_ext_ms_win_security_capauthz_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002798`

## callees

- `0x180002719`
- `0x180011cc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_capauthz_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_capauthz_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002719  mov     [rsp+arg_0], rcx
0x18000271e  mov     [rsp+arg_8], rdx
0x180002723  mov     [rsp+arg_10], r8
0x180002728  mov     [rsp+arg_18], r9
0x18000272d  sub     rsp, 68h
0x180002731  movdqa  [rsp+68h+var_48], xmm0
0x180002737  movdqa  [rsp+68h+var_38], xmm1
0x18000273d  movdqa  [rsp+68h+var_28], xmm2
0x180002743  movdqa  [rsp+68h+var_18], xmm3
0x180002749  mov     rdx, rax
0x18000274c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_capauthz_l1_1_0_dll
0x180002753  call    __delayLoadHelper2
0x180002758  movdqa  xmm0, [rsp+68h+var_48]
0x18000275e  movdqa  xmm1, [rsp+68h+var_38]
0x180002764  movdqa  xmm2, [rsp+68h+var_28]
0x18000276a  movdqa  xmm3, [rsp+68h+var_18]
0x180002770  mov     rcx, [rsp+68h+arg_0]
0x180002775  mov     rdx, [rsp+68h+arg_8]
0x18000277a  mov     r8, [rsp+68h+arg_10]
0x180002782  mov     r9, [rsp+68h+arg_18]
0x18000278a  add     rsp, 68h
0x18000278e  jmp     short $+2
0x180002790  jmp     rax
```
