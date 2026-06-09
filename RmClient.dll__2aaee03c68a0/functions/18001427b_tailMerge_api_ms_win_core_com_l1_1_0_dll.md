# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18001427b`
- end: `0x1800142f4`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800142fa`
- `0x18001431e`
- `0x180014a99`
- `0x180014aab`
- `0x180014abd`
- `0x180014acf`
- `0x180014ae1`

## callees

- `0x18000f260`
- `0x18001427b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001427b  mov     [rsp+arg_0], rcx
0x180014280  mov     [rsp+arg_8], rdx
0x180014285  mov     [rsp+arg_10], r8
0x18001428a  mov     [rsp+arg_18], r9
0x18001428f  sub     rsp, 68h
0x180014293  movdqa  [rsp+68h+var_48], xmm0
0x180014299  movdqa  [rsp+68h+var_38], xmm1
0x18001429f  movdqa  [rsp+68h+var_28], xmm2
0x1800142a5  movdqa  [rsp+68h+var_18], xmm3
0x1800142ab  mov     rdx, rax
0x1800142ae  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x1800142b5  call    __delayLoadHelper2
0x1800142ba  movdqa  xmm0, [rsp+68h+var_48]
0x1800142c0  movdqa  xmm1, [rsp+68h+var_38]
0x1800142c6  movdqa  xmm2, [rsp+68h+var_28]
0x1800142cc  movdqa  xmm3, [rsp+68h+var_18]
0x1800142d2  mov     rcx, [rsp+68h+arg_0]
0x1800142d7  mov     rdx, [rsp+68h+arg_8]
0x1800142dc  mov     r8, [rsp+68h+arg_10]
0x1800142e4  mov     r9, [rsp+68h+arg_18]
0x1800142ec  add     rsp, 68h
0x1800142f0  jmp     short $+2
0x1800142f2  jmp     rax
```
