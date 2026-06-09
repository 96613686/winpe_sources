# __tailMerge_ext_ms_win_ole32_bindctx_l1_1_0_dll

- ea: `0x1800042ea`
- end: `0x180004363`
- name: `__tailMerge_ext_ms_win_ole32_bindctx_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004369`

## callees

- `0x1800042ea`
- `0x180027c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ole32_bindctx_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ole32_bindctx_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800042ea  mov     [rsp+arg_0], rcx
0x1800042ef  mov     [rsp+arg_8], rdx
0x1800042f4  mov     [rsp+arg_10], r8
0x1800042f9  mov     [rsp+arg_18], r9
0x1800042fe  sub     rsp, 68h
0x180004302  movdqa  [rsp+68h+var_48], xmm0
0x180004308  movdqa  [rsp+68h+var_38], xmm1
0x18000430e  movdqa  [rsp+68h+var_28], xmm2
0x180004314  movdqa  [rsp+68h+var_18], xmm3
0x18000431a  mov     rdx, rax
0x18000431d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ole32_bindctx_l1_1_0_dll
0x180004324  call    __delayLoadHelper2
0x180004329  movdqa  xmm0, [rsp+68h+var_48]
0x18000432f  movdqa  xmm1, [rsp+68h+var_38]
0x180004335  movdqa  xmm2, [rsp+68h+var_28]
0x18000433b  movdqa  xmm3, [rsp+68h+var_18]
0x180004341  mov     rcx, [rsp+68h+arg_0]
0x180004346  mov     rdx, [rsp+68h+arg_8]
0x18000434b  mov     r8, [rsp+68h+arg_10]
0x180004353  mov     r9, [rsp+68h+arg_18]
0x18000435b  add     rsp, 68h
0x18000435f  jmp     short $+2
0x180004361  jmp     rax
```
