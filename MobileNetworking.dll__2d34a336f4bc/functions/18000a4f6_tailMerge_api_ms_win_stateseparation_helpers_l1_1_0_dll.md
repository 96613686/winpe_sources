# __tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll

- ea: `0x18000a4f6`
- end: `0x18000a56f`
- name: `__tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a575`

## callees

- `0x180007cd0`
- `0x18000a4f6`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_stateseparation_helpers_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a4f6  mov     [rsp+arg_0], rcx
0x18000a4fb  mov     [rsp+arg_8], rdx
0x18000a500  mov     [rsp+arg_10], r8
0x18000a505  mov     [rsp+arg_18], r9
0x18000a50a  sub     rsp, 68h
0x18000a50e  movdqa  [rsp+68h+var_48], xmm0
0x18000a514  movdqa  [rsp+68h+var_38], xmm1
0x18000a51a  movdqa  [rsp+68h+var_28], xmm2
0x18000a520  movdqa  [rsp+68h+var_18], xmm3
0x18000a526  mov     rdx, rax
0x18000a529  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_stateseparation_helpers_l1_1_0_dll
0x18000a530  call    __delayLoadHelper2
0x18000a535  movdqa  xmm0, [rsp+68h+var_48]
0x18000a53b  movdqa  xmm1, [rsp+68h+var_38]
0x18000a541  movdqa  xmm2, [rsp+68h+var_28]
0x18000a547  movdqa  xmm3, [rsp+68h+var_18]
0x18000a54d  mov     rcx, [rsp+68h+arg_0]
0x18000a552  mov     rdx, [rsp+68h+arg_8]
0x18000a557  mov     r8, [rsp+68h+arg_10]
0x18000a55f  mov     r9, [rsp+68h+arg_18]
0x18000a567  add     rsp, 68h
0x18000a56b  jmp     short $+2
0x18000a56d  jmp     rax
```
