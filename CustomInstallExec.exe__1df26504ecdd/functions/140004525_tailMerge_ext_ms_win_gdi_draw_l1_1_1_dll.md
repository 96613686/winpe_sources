# __tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll

- ea: `0x140004525`
- end: `0x14000459e`
- name: `__tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400045a4`

## callees

- `0x140004525`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_draw_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004525  mov     [rsp+arg_0], rcx
0x14000452a  mov     [rsp+arg_8], rdx
0x14000452f  mov     [rsp+arg_10], r8
0x140004534  mov     [rsp+arg_18], r9
0x140004539  sub     rsp, 68h
0x14000453d  movdqa  [rsp+68h+var_48], xmm0
0x140004543  movdqa  [rsp+68h+var_38], xmm1
0x140004549  movdqa  [rsp+68h+var_28], xmm2
0x14000454f  movdqa  [rsp+68h+var_18], xmm3
0x140004555  mov     rdx, rax
0x140004558  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_draw_l1_1_1_dll
0x14000455f  call    __delayLoadHelper2
0x140004564  movdqa  xmm0, [rsp+68h+var_48]
0x14000456a  movdqa  xmm1, [rsp+68h+var_38]
0x140004570  movdqa  xmm2, [rsp+68h+var_28]
0x140004576  movdqa  xmm3, [rsp+68h+var_18]
0x14000457c  mov     rcx, [rsp+68h+arg_0]
0x140004581  mov     rdx, [rsp+68h+arg_8]
0x140004586  mov     r8, [rsp+68h+arg_10]
0x14000458e  mov     r9, [rsp+68h+arg_18]
0x140004596  add     rsp, 68h
0x14000459a  jmp     short $+2
0x14000459c  jmp     rax
```
