# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x1800033c7`
- end: `0x180003440`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003446`
- `0x180003458`
- `0x18000346a`
- `0x18000347c`

## callees

- `0x1800033c7`
- `0x180047d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800033c7  mov     [rsp+arg_0], rcx
0x1800033cc  mov     [rsp+arg_8], rdx
0x1800033d1  mov     [rsp+arg_10], r8
0x1800033d6  mov     [rsp+arg_18], r9
0x1800033db  sub     rsp, 68h
0x1800033df  movdqa  [rsp+68h+var_48], xmm0
0x1800033e5  movdqa  [rsp+68h+var_38], xmm1
0x1800033eb  movdqa  [rsp+68h+var_28], xmm2
0x1800033f1  movdqa  [rsp+68h+var_18], xmm3
0x1800033f7  mov     rdx, rax
0x1800033fa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x180003401  call    __delayLoadHelper2
0x180003406  movdqa  xmm0, [rsp+68h+var_48]
0x18000340c  movdqa  xmm1, [rsp+68h+var_38]
0x180003412  movdqa  xmm2, [rsp+68h+var_28]
0x180003418  movdqa  xmm3, [rsp+68h+var_18]
0x18000341e  mov     rcx, [rsp+68h+arg_0]
0x180003423  mov     rdx, [rsp+68h+arg_8]
0x180003428  mov     r8, [rsp+68h+arg_10]
0x180003430  mov     r9, [rsp+68h+arg_18]
0x180003438  add     rsp, 68h
0x18000343c  jmp     short $+2
0x18000343e  jmp     rax
```
