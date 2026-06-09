# __tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll

- ea: `0x1400040b6`
- end: `0x14000412f`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004135`

## callees

- `0x1400040b6`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400040b6  mov     [rsp+arg_0], rcx
0x1400040bb  mov     [rsp+arg_8], rdx
0x1400040c0  mov     [rsp+arg_10], r8
0x1400040c5  mov     [rsp+arg_18], r9
0x1400040ca  sub     rsp, 68h
0x1400040ce  movdqa  [rsp+68h+var_48], xmm0
0x1400040d4  movdqa  [rsp+68h+var_38], xmm1
0x1400040da  movdqa  [rsp+68h+var_28], xmm2
0x1400040e0  movdqa  [rsp+68h+var_18], xmm3
0x1400040e6  mov     rdx, rax
0x1400040e9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll
0x1400040f0  call    __delayLoadHelper2
0x1400040f5  movdqa  xmm0, [rsp+68h+var_48]
0x1400040fb  movdqa  xmm1, [rsp+68h+var_38]
0x140004101  movdqa  xmm2, [rsp+68h+var_28]
0x140004107  movdqa  xmm3, [rsp+68h+var_18]
0x14000410d  mov     rcx, [rsp+68h+arg_0]
0x140004112  mov     rdx, [rsp+68h+arg_8]
0x140004117  mov     r8, [rsp+68h+arg_10]
0x14000411f  mov     r9, [rsp+68h+arg_18]
0x140004127  add     rsp, 68h
0x14000412b  jmp     short $+2
0x14000412d  jmp     rax
```
