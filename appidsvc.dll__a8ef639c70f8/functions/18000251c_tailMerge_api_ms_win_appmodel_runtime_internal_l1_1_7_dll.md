# __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_7_dll

- ea: `0x18000251c`
- end: `0x180002595`
- name: `__tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_7_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025a0`

## callees

- `0x18000251c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_7_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_7_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000251c  mov     [rsp+arg_0], rcx
0x180002521  mov     [rsp+arg_8], rdx
0x180002526  mov     [rsp+arg_10], r8
0x18000252b  mov     [rsp+arg_18], r9
0x180002530  sub     rsp, 68h
0x180002534  movdqa  [rsp+68h+var_48], xmm0
0x18000253a  movdqa  [rsp+68h+var_38], xmm1
0x180002540  movdqa  [rsp+68h+var_28], xmm2
0x180002546  movdqa  [rsp+68h+var_18], xmm3
0x18000254c  mov     rdx, rax
0x18000254f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_7_dll
0x180002556  call    __delayLoadHelper2
0x18000255b  movdqa  xmm0, [rsp+68h+var_48]
0x180002561  movdqa  xmm1, [rsp+68h+var_38]
0x180002567  movdqa  xmm2, [rsp+68h+var_28]
0x18000256d  movdqa  xmm3, [rsp+68h+var_18]
0x180002573  mov     rcx, [rsp+68h+arg_0]
0x180002578  mov     rdx, [rsp+68h+arg_8]
0x18000257d  mov     r8, [rsp+68h+arg_10]
0x180002585  mov     r9, [rsp+68h+arg_18]
0x18000258d  add     rsp, 68h
0x180002591  jmp     short $+2
0x180002593  jmp     rax
```
