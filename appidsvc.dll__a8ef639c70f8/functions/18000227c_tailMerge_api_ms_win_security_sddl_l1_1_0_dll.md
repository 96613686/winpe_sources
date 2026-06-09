# __tailMerge_api_ms_win_security_sddl_l1_1_0_dll

- ea: `0x18000227c`
- end: `0x1800022f5`
- name: `__tailMerge_api_ms_win_security_sddl_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x18000227c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_sddl_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000227c  mov     [rsp+arg_0], rcx
0x180002281  mov     [rsp+arg_8], rdx
0x180002286  mov     [rsp+arg_10], r8
0x18000228b  mov     [rsp+arg_18], r9
0x180002290  sub     rsp, 68h
0x180002294  movdqa  [rsp+68h+var_48], xmm0
0x18000229a  movdqa  [rsp+68h+var_38], xmm1
0x1800022a0  movdqa  [rsp+68h+var_28], xmm2
0x1800022a6  movdqa  [rsp+68h+var_18], xmm3
0x1800022ac  mov     rdx, rax
0x1800022af  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_sddl_l1_1_0_dll
0x1800022b6  call    __delayLoadHelper2
0x1800022bb  movdqa  xmm0, [rsp+68h+var_48]
0x1800022c1  movdqa  xmm1, [rsp+68h+var_38]
0x1800022c7  movdqa  xmm2, [rsp+68h+var_28]
0x1800022cd  movdqa  xmm3, [rsp+68h+var_18]
0x1800022d3  mov     rcx, [rsp+68h+arg_0]
0x1800022d8  mov     rdx, [rsp+68h+arg_8]
0x1800022dd  mov     r8, [rsp+68h+arg_10]
0x1800022e5  mov     r9, [rsp+68h+arg_18]
0x1800022ed  add     rsp, 68h
0x1800022f1  jmp     short $+2
0x1800022f3  jmp     rax
```
