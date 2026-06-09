# __tailMerge_ext_ms_win_globalization_input_l1_1_3_dll

- ea: `0x18000453a`
- end: `0x1800045b3`
- name: `__tailMerge_ext_ms_win_globalization_input_l1_1_3_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800045b9`

## callees

- `0x18000453a`
- `0x180027c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_globalization_input_l1_1_3_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_globalization_input_l1_1_3_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000453a  mov     [rsp+arg_0], rcx
0x18000453f  mov     [rsp+arg_8], rdx
0x180004544  mov     [rsp+arg_10], r8
0x180004549  mov     [rsp+arg_18], r9
0x18000454e  sub     rsp, 68h
0x180004552  movdqa  [rsp+68h+var_48], xmm0
0x180004558  movdqa  [rsp+68h+var_38], xmm1
0x18000455e  movdqa  [rsp+68h+var_28], xmm2
0x180004564  movdqa  [rsp+68h+var_18], xmm3
0x18000456a  mov     rdx, rax
0x18000456d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_globalization_input_l1_1_3_dll
0x180004574  call    __delayLoadHelper2
0x180004579  movdqa  xmm0, [rsp+68h+var_48]
0x18000457f  movdqa  xmm1, [rsp+68h+var_38]
0x180004585  movdqa  xmm2, [rsp+68h+var_28]
0x18000458b  movdqa  xmm3, [rsp+68h+var_18]
0x180004591  mov     rcx, [rsp+68h+arg_0]
0x180004596  mov     rdx, [rsp+68h+arg_8]
0x18000459b  mov     r8, [rsp+68h+arg_10]
0x1800045a3  mov     r9, [rsp+68h+arg_18]
0x1800045ab  add     rsp, 68h
0x1800045af  jmp     short $+2
0x1800045b1  jmp     rax
```
