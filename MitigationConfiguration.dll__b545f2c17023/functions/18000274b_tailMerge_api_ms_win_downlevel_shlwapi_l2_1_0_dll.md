# __tailMerge_api_ms_win_downlevel_shlwapi_l2_1_0_dll

- ea: `0x18000274b`
- end: `0x1800027c4`
- name: `__tailMerge_api_ms_win_downlevel_shlwapi_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027ca`

## callees

- `0x18000274b`
- `0x180013920`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_downlevel_shlwapi_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_downlevel_shlwapi_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000274b  mov     [rsp+arg_0], rcx
0x180002750  mov     [rsp+arg_8], rdx
0x180002755  mov     [rsp+arg_10], r8
0x18000275a  mov     [rsp+arg_18], r9
0x18000275f  sub     rsp, 68h
0x180002763  movdqa  [rsp+68h+var_48], xmm0
0x180002769  movdqa  [rsp+68h+var_38], xmm1
0x18000276f  movdqa  [rsp+68h+var_28], xmm2
0x180002775  movdqa  [rsp+68h+var_18], xmm3
0x18000277b  mov     rdx, rax
0x18000277e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_downlevel_shlwapi_l2_1_0_dll
0x180002785  call    __delayLoadHelper2
0x18000278a  movdqa  xmm0, [rsp+68h+var_48]
0x180002790  movdqa  xmm1, [rsp+68h+var_38]
0x180002796  movdqa  xmm2, [rsp+68h+var_28]
0x18000279c  movdqa  xmm3, [rsp+68h+var_18]
0x1800027a2  mov     rcx, [rsp+68h+arg_0]
0x1800027a7  mov     rdx, [rsp+68h+arg_8]
0x1800027ac  mov     r8, [rsp+68h+arg_10]
0x1800027b4  mov     r9, [rsp+68h+arg_18]
0x1800027bc  add     rsp, 68h
0x1800027c0  jmp     short $+2
0x1800027c2  jmp     rax
```
