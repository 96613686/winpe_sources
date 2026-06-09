# __tailMerge_api_ms_win_core_com_l1_1_1_dll

- ea: `0x1800149f6`
- end: `0x180014a6f`
- name: `__tailMerge_api_ms_win_core_com_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014a75`

## callees

- `0x18000f260`
- `0x1800149f6`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800149f6  mov     [rsp+arg_0], rcx
0x1800149fb  mov     [rsp+arg_8], rdx
0x180014a00  mov     [rsp+arg_10], r8
0x180014a05  mov     [rsp+arg_18], r9
0x180014a0a  sub     rsp, 68h
0x180014a0e  movdqa  [rsp+68h+var_48], xmm0
0x180014a14  movdqa  [rsp+68h+var_38], xmm1
0x180014a1a  movdqa  [rsp+68h+var_28], xmm2
0x180014a20  movdqa  [rsp+68h+var_18], xmm3
0x180014a26  mov     rdx, rax
0x180014a29  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_1_dll
0x180014a30  call    __delayLoadHelper2
0x180014a35  movdqa  xmm0, [rsp+68h+var_48]
0x180014a3b  movdqa  xmm1, [rsp+68h+var_38]
0x180014a41  movdqa  xmm2, [rsp+68h+var_28]
0x180014a47  movdqa  xmm3, [rsp+68h+var_18]
0x180014a4d  mov     rcx, [rsp+68h+arg_0]
0x180014a52  mov     rdx, [rsp+68h+arg_8]
0x180014a57  mov     r8, [rsp+68h+arg_10]
0x180014a5f  mov     r9, [rsp+68h+arg_18]
0x180014a67  add     rsp, 68h
0x180014a6b  jmp     short $+2
0x180014a6d  jmp     rax
```
