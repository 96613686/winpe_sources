# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x1800021ce`
- end: `0x180002247`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000224d`

## callees

- `0x1800021ce`
- `0x180020f30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800021ce  mov     [rsp+arg_0], rcx
0x1800021d3  mov     [rsp+arg_8], rdx
0x1800021d8  mov     [rsp+arg_10], r8
0x1800021dd  mov     [rsp+arg_18], r9
0x1800021e2  sub     rsp, 68h
0x1800021e6  movdqa  [rsp+68h+var_48], xmm0
0x1800021ec  movdqa  [rsp+68h+var_38], xmm1
0x1800021f2  movdqa  [rsp+68h+var_28], xmm2
0x1800021f8  movdqa  [rsp+68h+var_18], xmm3
0x1800021fe  mov     rdx, rax
0x180002201  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x180002208  call    __delayLoadHelper2
0x18000220d  movdqa  xmm0, [rsp+68h+var_48]
0x180002213  movdqa  xmm1, [rsp+68h+var_38]
0x180002219  movdqa  xmm2, [rsp+68h+var_28]
0x18000221f  movdqa  xmm3, [rsp+68h+var_18]
0x180002225  mov     rcx, [rsp+68h+arg_0]
0x18000222a  mov     rdx, [rsp+68h+arg_8]
0x18000222f  mov     r8, [rsp+68h+arg_10]
0x180002237  mov     r9, [rsp+68h+arg_18]
0x18000223f  add     rsp, 68h
0x180002243  jmp     short $+2
0x180002245  jmp     rax
```
