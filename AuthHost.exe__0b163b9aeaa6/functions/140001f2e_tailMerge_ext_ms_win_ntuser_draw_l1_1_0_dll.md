# __tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll

- ea: `0x140001f2e`
- end: `0x140001fa7`
- name: `__tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001fad`

## callees

- `0x140001f2e`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001f2e  mov     [rsp+arg_0], rcx
0x140001f33  mov     [rsp+arg_8], rdx
0x140001f38  mov     [rsp+arg_10], r8
0x140001f3d  mov     [rsp+arg_18], r9
0x140001f42  sub     rsp, 68h
0x140001f46  movdqa  [rsp+68h+var_48], xmm0
0x140001f4c  movdqa  [rsp+68h+var_38], xmm1
0x140001f52  movdqa  [rsp+68h+var_28], xmm2
0x140001f58  movdqa  [rsp+68h+var_18], xmm3
0x140001f5e  mov     rdx, rax
0x140001f61  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_0_dll
0x140001f68  call    __delayLoadHelper2
0x140001f6d  movdqa  xmm0, [rsp+68h+var_48]
0x140001f73  movdqa  xmm1, [rsp+68h+var_38]
0x140001f79  movdqa  xmm2, [rsp+68h+var_28]
0x140001f7f  movdqa  xmm3, [rsp+68h+var_18]
0x140001f85  mov     rcx, [rsp+68h+arg_0]
0x140001f8a  mov     rdx, [rsp+68h+arg_8]
0x140001f8f  mov     r8, [rsp+68h+arg_10]
0x140001f97  mov     r9, [rsp+68h+arg_18]
0x140001f9f  add     rsp, 68h
0x140001fa3  jmp     short $+2
0x140001fa5  jmp     rax
```
