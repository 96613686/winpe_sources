# __tailMerge_ext_ms_win_core_licensemanager_l1_1_0_dll

- ea: `0x18000421a`
- end: `0x180004293`
- name: `__tailMerge_ext_ms_win_core_licensemanager_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004299`

## callees

- `0x18000421a`
- `0x1800172b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_licensemanager_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_licensemanager_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000421a  mov     [rsp+arg_0], rcx
0x18000421f  mov     [rsp+arg_8], rdx
0x180004224  mov     [rsp+arg_10], r8
0x180004229  mov     [rsp+arg_18], r9
0x18000422e  sub     rsp, 68h
0x180004232  movdqa  [rsp+68h+var_48], xmm0
0x180004238  movdqa  [rsp+68h+var_38], xmm1
0x18000423e  movdqa  [rsp+68h+var_28], xmm2
0x180004244  movdqa  [rsp+68h+var_18], xmm3
0x18000424a  mov     rdx, rax
0x18000424d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_licensemanager_l1_1_0_dll
0x180004254  call    __delayLoadHelper2
0x180004259  movdqa  xmm0, [rsp+68h+var_48]
0x18000425f  movdqa  xmm1, [rsp+68h+var_38]
0x180004265  movdqa  xmm2, [rsp+68h+var_28]
0x18000426b  movdqa  xmm3, [rsp+68h+var_18]
0x180004271  mov     rcx, [rsp+68h+arg_0]
0x180004276  mov     rdx, [rsp+68h+arg_8]
0x18000427b  mov     r8, [rsp+68h+arg_10]
0x180004283  mov     r9, [rsp+68h+arg_18]
0x18000428b  add     rsp, 68h
0x18000428f  jmp     short $+2
0x180004291  jmp     rax
```
