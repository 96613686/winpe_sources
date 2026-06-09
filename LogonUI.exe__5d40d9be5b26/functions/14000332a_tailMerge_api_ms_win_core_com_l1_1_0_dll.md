# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x14000332a`
- end: `0x1400033a3`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400033a9`
- `0x1400033bb`
- `0x1400033cd`

## callees

- `0x140001610`
- `0x14000332a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000332a  mov     [rsp+arg_0], rcx
0x14000332f  mov     [rsp+arg_8], rdx
0x140003334  mov     [rsp+arg_10], r8
0x140003339  mov     [rsp+arg_18], r9
0x14000333e  sub     rsp, 68h
0x140003342  movdqa  [rsp+68h+var_48], xmm0
0x140003348  movdqa  [rsp+68h+var_38], xmm1
0x14000334e  movdqa  [rsp+68h+var_28], xmm2
0x140003354  movdqa  [rsp+68h+var_18], xmm3
0x14000335a  mov     rdx, rax
0x14000335d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x140003364  call    __delayLoadHelper2
0x140003369  movdqa  xmm0, [rsp+68h+var_48]
0x14000336f  movdqa  xmm1, [rsp+68h+var_38]
0x140003375  movdqa  xmm2, [rsp+68h+var_28]
0x14000337b  movdqa  xmm3, [rsp+68h+var_18]
0x140003381  mov     rcx, [rsp+68h+arg_0]
0x140003386  mov     rdx, [rsp+68h+arg_8]
0x14000338b  mov     r8, [rsp+68h+arg_10]
0x140003393  mov     r9, [rsp+68h+arg_18]
0x14000339b  add     rsp, 68h
0x14000339f  jmp     short $+2
0x1400033a1  jmp     rax
```
