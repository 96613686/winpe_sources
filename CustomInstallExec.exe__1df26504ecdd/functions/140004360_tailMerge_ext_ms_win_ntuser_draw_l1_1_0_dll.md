# __tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll

- ea: `0x140004360`
- end: `0x1400043d9`
- name: `__tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400043df`
- `0x1400043f1`
- `0x140004403`

## callees

- `0x140004360`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004360  mov     [rsp+arg_0], rcx
0x140004365  mov     [rsp+arg_8], rdx
0x14000436a  mov     [rsp+arg_10], r8
0x14000436f  mov     [rsp+arg_18], r9
0x140004374  sub     rsp, 68h
0x140004378  movdqa  [rsp+68h+var_48], xmm0
0x14000437e  movdqa  [rsp+68h+var_38], xmm1
0x140004384  movdqa  [rsp+68h+var_28], xmm2
0x14000438a  movdqa  [rsp+68h+var_18], xmm3
0x140004390  mov     rdx, rax
0x140004393  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_0_dll
0x14000439a  call    __delayLoadHelper2
0x14000439f  movdqa  xmm0, [rsp+68h+var_48]
0x1400043a5  movdqa  xmm1, [rsp+68h+var_38]
0x1400043ab  movdqa  xmm2, [rsp+68h+var_28]
0x1400043b1  movdqa  xmm3, [rsp+68h+var_18]
0x1400043b7  mov     rcx, [rsp+68h+arg_0]
0x1400043bc  mov     rdx, [rsp+68h+arg_8]
0x1400043c1  mov     r8, [rsp+68h+arg_10]
0x1400043c9  mov     r9, [rsp+68h+arg_18]
0x1400043d1  add     rsp, 68h
0x1400043d5  jmp     short $+2
0x1400043d7  jmp     rax
```
