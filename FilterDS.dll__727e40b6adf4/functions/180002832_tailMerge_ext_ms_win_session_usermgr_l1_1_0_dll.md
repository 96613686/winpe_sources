# __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll

- ea: `0x180002832`
- end: `0x1800028ab`
- name: `__tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800028b1`
- `0x180002918`

## callees

- `0x180002832`
- `0x1800216e0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002832  mov     [rsp+arg_0], rcx
0x180002837  mov     [rsp+arg_8], rdx
0x18000283c  mov     [rsp+arg_10], r8
0x180002841  mov     [rsp+arg_18], r9
0x180002846  sub     rsp, 68h
0x18000284a  movdqa  [rsp+68h+var_48], xmm0
0x180002850  movdqa  [rsp+68h+var_38], xmm1
0x180002856  movdqa  [rsp+68h+var_28], xmm2
0x18000285c  movdqa  [rsp+68h+var_18], xmm3
0x180002862  mov     rdx, rax
0x180002865  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usermgr_l1_1_0_dll
0x18000286c  call    __delayLoadHelper2
0x180002871  movdqa  xmm0, [rsp+68h+var_48]
0x180002877  movdqa  xmm1, [rsp+68h+var_38]
0x18000287d  movdqa  xmm2, [rsp+68h+var_28]
0x180002883  movdqa  xmm3, [rsp+68h+var_18]
0x180002889  mov     rcx, [rsp+68h+arg_0]
0x18000288e  mov     rdx, [rsp+68h+arg_8]
0x180002893  mov     r8, [rsp+68h+arg_10]
0x18000289b  mov     r9, [rsp+68h+arg_18]
0x1800028a3  add     rsp, 68h
0x1800028a7  jmp     short $+2
0x1800028a9  jmp     rax
```
