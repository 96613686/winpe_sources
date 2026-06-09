# __tailMerge_ext_ms_win_advapi32_lsa_l1_1_0_dll

- ea: `0x18001004a`
- end: `0x1800100c3`
- name: `__tailMerge_ext_ms_win_advapi32_lsa_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800100c9`

## callees

- `0x18000e230`
- `0x18001004a`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_advapi32_lsa_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_advapi32_lsa_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001004a  mov     [rsp+arg_0], rcx
0x18001004f  mov     [rsp+arg_8], rdx
0x180010054  mov     [rsp+arg_10], r8
0x180010059  mov     [rsp+arg_18], r9
0x18001005e  sub     rsp, 68h
0x180010062  movdqa  [rsp+68h+var_48], xmm0
0x180010068  movdqa  [rsp+68h+var_38], xmm1
0x18001006e  movdqa  [rsp+68h+var_28], xmm2
0x180010074  movdqa  [rsp+68h+var_18], xmm3
0x18001007a  mov     rdx, rax
0x18001007d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_advapi32_lsa_l1_1_0_dll
0x180010084  call    __delayLoadHelper2
0x180010089  movdqa  xmm0, [rsp+68h+var_48]
0x18001008f  movdqa  xmm1, [rsp+68h+var_38]
0x180010095  movdqa  xmm2, [rsp+68h+var_28]
0x18001009b  movdqa  xmm3, [rsp+68h+var_18]
0x1800100a1  mov     rcx, [rsp+68h+arg_0]
0x1800100a6  mov     rdx, [rsp+68h+arg_8]
0x1800100ab  mov     r8, [rsp+68h+arg_10]
0x1800100b3  mov     r9, [rsp+68h+arg_18]
0x1800100bb  add     rsp, 68h
0x1800100bf  jmp     short $+2
0x1800100c1  jmp     rax
```
