# __tailMerge_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll

- ea: `0x18002266e`
- end: `0x1800226e7`
- name: `__tailMerge_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800226ed`
- `0x1800226ff`
- `0x180022711`

## callees

- `0x18002266e`
- `0x180032ce0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18002266e  mov     [rsp+arg_0], rcx
0x180022673  mov     [rsp+arg_8], rdx
0x180022678  mov     [rsp+arg_10], r8
0x18002267d  mov     [rsp+arg_18], r9
0x180022682  sub     rsp, 68h
0x180022686  movdqa  [rsp+68h+var_48], xmm0
0x18002268c  movdqa  [rsp+68h+var_38], xmm1
0x180022692  movdqa  [rsp+68h+var_28], xmm2
0x180022698  movdqa  [rsp+68h+var_18], xmm3
0x18002269e  mov     rdx, rax
0x1800226a1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_rectangle_ext_l1_1_0_dll
0x1800226a8  call    __delayLoadHelper2
0x1800226ad  movdqa  xmm0, [rsp+68h+var_48]
0x1800226b3  movdqa  xmm1, [rsp+68h+var_38]
0x1800226b9  movdqa  xmm2, [rsp+68h+var_28]
0x1800226bf  movdqa  xmm3, [rsp+68h+var_18]
0x1800226c5  mov     rcx, [rsp+68h+arg_0]
0x1800226ca  mov     rdx, [rsp+68h+arg_8]
0x1800226cf  mov     r8, [rsp+68h+arg_10]
0x1800226d7  mov     r9, [rsp+68h+arg_18]
0x1800226df  add     rsp, 68h
0x1800226e3  jmp     short $+2
0x1800226e5  jmp     rax
```
