# __tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll

- ea: `0x18000248c`
- end: `0x180002505`
- name: `__tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002510`

## callees

- `0x18000248c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_1_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000248c  mov     [rsp+arg_0], rcx
0x180002491  mov     [rsp+arg_8], rdx
0x180002496  mov     [rsp+arg_10], r8
0x18000249b  mov     [rsp+arg_18], r9
0x1800024a0  sub     rsp, 68h
0x1800024a4  movdqa  [rsp+68h+var_48], xmm0
0x1800024aa  movdqa  [rsp+68h+var_38], xmm1
0x1800024b0  movdqa  [rsp+68h+var_28], xmm2
0x1800024b6  movdqa  [rsp+68h+var_18], xmm3
0x1800024bc  mov     rdx, rax
0x1800024bf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_1_dll
0x1800024c6  call    __delayLoadHelper2
0x1800024cb  movdqa  xmm0, [rsp+68h+var_48]
0x1800024d1  movdqa  xmm1, [rsp+68h+var_38]
0x1800024d7  movdqa  xmm2, [rsp+68h+var_28]
0x1800024dd  movdqa  xmm3, [rsp+68h+var_18]
0x1800024e3  mov     rcx, [rsp+68h+arg_0]
0x1800024e8  mov     rdx, [rsp+68h+arg_8]
0x1800024ed  mov     r8, [rsp+68h+arg_10]
0x1800024f5  mov     r9, [rsp+68h+arg_18]
0x1800024fd  add     rsp, 68h
0x180002501  jmp     short $+2
0x180002503  jmp     rax
```
