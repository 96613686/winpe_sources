# __tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll

- ea: `0x1400046c6`
- end: `0x14000473f`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004745`

## callees

- `0x1400046c6`
- `0x14000ea00`

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
0x1400046c6  mov     [rsp+arg_0], rcx
0x1400046cb  mov     [rsp+arg_8], rdx
0x1400046d0  mov     [rsp+arg_10], r8
0x1400046d5  mov     [rsp+arg_18], r9
0x1400046da  sub     rsp, 68h
0x1400046de  movdqa  [rsp+68h+var_48], xmm0
0x1400046e4  movdqa  [rsp+68h+var_38], xmm1
0x1400046ea  movdqa  [rsp+68h+var_28], xmm2
0x1400046f0  movdqa  [rsp+68h+var_18], xmm3
0x1400046f6  mov     rdx, rax
0x1400046f9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll
0x140004700  call    __delayLoadHelper2
0x140004705  movdqa  xmm0, [rsp+68h+var_48]
0x14000470b  movdqa  xmm1, [rsp+68h+var_38]
0x140004711  movdqa  xmm2, [rsp+68h+var_28]
0x140004717  movdqa  xmm3, [rsp+68h+var_18]
0x14000471d  mov     rcx, [rsp+68h+arg_0]
0x140004722  mov     rdx, [rsp+68h+arg_8]
0x140004727  mov     r8, [rsp+68h+arg_10]
0x14000472f  mov     r9, [rsp+68h+arg_18]
0x140004737  add     rsp, 68h
0x14000473b  jmp     short $+2
0x14000473d  jmp     rax
```
