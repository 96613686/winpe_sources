# __tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll

- ea: `0x1800022e4`
- end: `0x18000235d`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002363`
- `0x180002375`

## callees

- `0x1800022e4`
- `0x180020f30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022e4  mov     [rsp+arg_0], rcx
0x1800022e9  mov     [rsp+arg_8], rdx
0x1800022ee  mov     [rsp+arg_10], r8
0x1800022f3  mov     [rsp+arg_18], r9
0x1800022f8  sub     rsp, 68h
0x1800022fc  movdqa  [rsp+68h+var_48], xmm0
0x180002302  movdqa  [rsp+68h+var_38], xmm1
0x180002308  movdqa  [rsp+68h+var_28], xmm2
0x18000230e  movdqa  [rsp+68h+var_18], xmm3
0x180002314  mov     rdx, rax
0x180002317  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_dc_access_l1_1_0_dll
0x18000231e  call    __delayLoadHelper2
0x180002323  movdqa  xmm0, [rsp+68h+var_48]
0x180002329  movdqa  xmm1, [rsp+68h+var_38]
0x18000232f  movdqa  xmm2, [rsp+68h+var_28]
0x180002335  movdqa  xmm3, [rsp+68h+var_18]
0x18000233b  mov     rcx, [rsp+68h+arg_0]
0x180002340  mov     rdx, [rsp+68h+arg_8]
0x180002345  mov     r8, [rsp+68h+arg_10]
0x18000234d  mov     r9, [rsp+68h+arg_18]
0x180002355  add     rsp, 68h
0x180002359  jmp     short $+2
0x18000235b  jmp     rax
```
