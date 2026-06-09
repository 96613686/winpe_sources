# __tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll

- ea: `0x14000247b`
- end: `0x1400024f4`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400024fa`
- `0x14000250c`

## callees

- `0x14000247b`
- `0x140004270`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000247b  mov     [rsp+arg_0], rcx
0x140002480  mov     [rsp+arg_8], rdx
0x140002485  mov     [rsp+arg_10], r8
0x14000248a  mov     [rsp+arg_18], r9
0x14000248f  sub     rsp, 68h
0x140002493  movdqa  [rsp+68h+var_48], xmm0
0x140002499  movdqa  [rsp+68h+var_38], xmm1
0x14000249f  movdqa  [rsp+68h+var_28], xmm2
0x1400024a5  movdqa  [rsp+68h+var_18], xmm3
0x1400024ab  mov     rdx, rax
0x1400024ae  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll
0x1400024b5  call    __delayLoadHelper2
0x1400024ba  movdqa  xmm0, [rsp+68h+var_48]
0x1400024c0  movdqa  xmm1, [rsp+68h+var_38]
0x1400024c6  movdqa  xmm2, [rsp+68h+var_28]
0x1400024cc  movdqa  xmm3, [rsp+68h+var_18]
0x1400024d2  mov     rcx, [rsp+68h+arg_0]
0x1400024d7  mov     rdx, [rsp+68h+arg_8]
0x1400024dc  mov     r8, [rsp+68h+arg_10]
0x1400024e4  mov     r9, [rsp+68h+arg_18]
0x1400024ec  add     rsp, 68h
0x1400024f0  jmp     short $+2
0x1400024f2  jmp     rax
```
