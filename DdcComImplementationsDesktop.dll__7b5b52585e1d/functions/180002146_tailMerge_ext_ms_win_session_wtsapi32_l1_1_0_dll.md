# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x180002146`
- end: `0x1800021bf`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800021c5`
- `0x18000222c`
- `0x18000223e`

## callees

- `0x180002146`
- `0x18000b5c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002146  mov     [rsp+arg_0], rcx
0x18000214b  mov     [rsp+arg_8], rdx
0x180002150  mov     [rsp+arg_10], r8
0x180002155  mov     [rsp+arg_18], r9
0x18000215a  sub     rsp, 68h
0x18000215e  movdqa  [rsp+68h+var_48], xmm0
0x180002164  movdqa  [rsp+68h+var_38], xmm1
0x18000216a  movdqa  [rsp+68h+var_28], xmm2
0x180002170  movdqa  [rsp+68h+var_18], xmm3
0x180002176  mov     rdx, rax
0x180002179  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x180002180  call    __delayLoadHelper2
0x180002185  movdqa  xmm0, [rsp+68h+var_48]
0x18000218b  movdqa  xmm1, [rsp+68h+var_38]
0x180002191  movdqa  xmm2, [rsp+68h+var_28]
0x180002197  movdqa  xmm3, [rsp+68h+var_18]
0x18000219d  mov     rcx, [rsp+68h+arg_0]
0x1800021a2  mov     rdx, [rsp+68h+arg_8]
0x1800021a7  mov     r8, [rsp+68h+arg_10]
0x1800021af  mov     r9, [rsp+68h+arg_18]
0x1800021b7  add     rsp, 68h
0x1800021bb  jmp     short $+2
0x1800021bd  jmp     rax
```
