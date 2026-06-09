# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x140001c76`
- end: `0x140001cef`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001cf5`
- `0x140001d07`

## callees

- `0x140001c76`
- `0x14000fc40`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001c76  mov     [rsp+arg_0], rcx
0x140001c7b  mov     [rsp+arg_8], rdx
0x140001c80  mov     [rsp+arg_10], r8
0x140001c85  mov     [rsp+arg_18], r9
0x140001c8a  sub     rsp, 68h
0x140001c8e  movdqa  [rsp+68h+var_48], xmm0
0x140001c94  movdqa  [rsp+68h+var_38], xmm1
0x140001c9a  movdqa  [rsp+68h+var_28], xmm2
0x140001ca0  movdqa  [rsp+68h+var_18], xmm3
0x140001ca6  mov     rdx, rax
0x140001ca9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x140001cb0  call    __delayLoadHelper2
0x140001cb5  movdqa  xmm0, [rsp+68h+var_48]
0x140001cbb  movdqa  xmm1, [rsp+68h+var_38]
0x140001cc1  movdqa  xmm2, [rsp+68h+var_28]
0x140001cc7  movdqa  xmm3, [rsp+68h+var_18]
0x140001ccd  mov     rcx, [rsp+68h+arg_0]
0x140001cd2  mov     rdx, [rsp+68h+arg_8]
0x140001cd7  mov     r8, [rsp+68h+arg_10]
0x140001cdf  mov     r9, [rsp+68h+arg_18]
0x140001ce7  add     rsp, 68h
0x140001ceb  jmp     short $+2
0x140001ced  jmp     rax
```
