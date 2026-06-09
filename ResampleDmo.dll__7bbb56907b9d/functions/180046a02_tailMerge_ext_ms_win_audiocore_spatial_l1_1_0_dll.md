# __tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll

- ea: `0x180046a02`
- end: `0x180046a7b`
- name: `__tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046a81`

## callees

- `0x180046a02`
- `0x180084580`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_audiocore_spatial_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_audiocore_spatial_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180046a02  mov     [rsp+arg_0], rcx
0x180046a07  mov     [rsp+arg_8], rdx
0x180046a0c  mov     [rsp+arg_10], r8
0x180046a11  mov     [rsp+arg_18], r9
0x180046a16  sub     rsp, 68h
0x180046a1a  movdqa  [rsp+68h+var_48], xmm0
0x180046a20  movdqa  [rsp+68h+var_38], xmm1
0x180046a26  movdqa  [rsp+68h+var_28], xmm2
0x180046a2c  movdqa  [rsp+68h+var_18], xmm3
0x180046a32  mov     rdx, rax
0x180046a35  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_audiocore_spatial_l1_1_0_dll
0x180046a3c  call    __delayLoadHelper2
0x180046a41  movdqa  xmm0, [rsp+68h+var_48]
0x180046a47  movdqa  xmm1, [rsp+68h+var_38]
0x180046a4d  movdqa  xmm2, [rsp+68h+var_28]
0x180046a53  movdqa  xmm3, [rsp+68h+var_18]
0x180046a59  mov     rcx, [rsp+68h+arg_0]
0x180046a5e  mov     rdx, [rsp+68h+arg_8]
0x180046a63  mov     r8, [rsp+68h+arg_10]
0x180046a6b  mov     r9, [rsp+68h+arg_18]
0x180046a73  add     rsp, 68h
0x180046a77  jmp     short $+2
0x180046a79  jmp     rax
```
