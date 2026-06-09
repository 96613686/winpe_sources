# __tailMerge_api_ms_win_core_featurestaging_l1_1_0_dll

- ea: `0x18000eaa2`
- end: `0x18000eb1b`
- name: `__tailMerge_api_ms_win_core_featurestaging_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eb30`
- `0x18000eb50`
- `0x18000eb70`

## callees

- `0x18000eaa2`
- `0x180014c80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_featurestaging_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_featurestaging_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000eaa2  mov     [rsp+arg_0], rcx
0x18000eaa7  mov     [rsp+arg_8], rdx
0x18000eaac  mov     [rsp+arg_10], r8
0x18000eab1  mov     [rsp+arg_18], r9
0x18000eab6  sub     rsp, 68h
0x18000eaba  movdqa  [rsp+68h+var_48], xmm0
0x18000eac0  movdqa  [rsp+68h+var_38], xmm1
0x18000eac6  movdqa  [rsp+68h+var_28], xmm2
0x18000eacc  movdqa  [rsp+68h+var_18], xmm3
0x18000ead2  mov     rdx, rax
0x18000ead5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_featurestaging_l1_1_0_dll
0x18000eadc  call    __delayLoadHelper2
0x18000eae1  movdqa  xmm0, [rsp+68h+var_48]
0x18000eae7  movdqa  xmm1, [rsp+68h+var_38]
0x18000eaed  movdqa  xmm2, [rsp+68h+var_28]
0x18000eaf3  movdqa  xmm3, [rsp+68h+var_18]
0x18000eaf9  mov     rcx, [rsp+68h+arg_0]
0x18000eafe  mov     rdx, [rsp+68h+arg_8]
0x18000eb03  mov     r8, [rsp+68h+arg_10]
0x18000eb0b  mov     r9, [rsp+68h+arg_18]
0x18000eb13  add     rsp, 68h
0x18000eb17  jmp     short $+2
0x18000eb19  jmp     rax
```
