# __tailMerge_api_ms_win_appmodel_identity_l1_2_0_dll

- ea: `0x1400023e1`
- end: `0x14000245a`
- name: `__tailMerge_api_ms_win_appmodel_identity_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002460`
- `0x140002472`

## callees

- `0x1400023e1`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_identity_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_identity_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400023e1  mov     [rsp+arg_0], rcx
0x1400023e6  mov     [rsp+arg_8], rdx
0x1400023eb  mov     [rsp+arg_10], r8
0x1400023f0  mov     [rsp+arg_18], r9
0x1400023f5  sub     rsp, 68h
0x1400023f9  movdqa  [rsp+68h+var_48], xmm0
0x1400023ff  movdqa  [rsp+68h+var_38], xmm1
0x140002405  movdqa  [rsp+68h+var_28], xmm2
0x14000240b  movdqa  [rsp+68h+var_18], xmm3
0x140002411  mov     rdx, rax
0x140002414  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_identity_l1_2_0_dll
0x14000241b  call    __delayLoadHelper2
0x140002420  movdqa  xmm0, [rsp+68h+var_48]
0x140002426  movdqa  xmm1, [rsp+68h+var_38]
0x14000242c  movdqa  xmm2, [rsp+68h+var_28]
0x140002432  movdqa  xmm3, [rsp+68h+var_18]
0x140002438  mov     rcx, [rsp+68h+arg_0]
0x14000243d  mov     rdx, [rsp+68h+arg_8]
0x140002442  mov     r8, [rsp+68h+arg_10]
0x14000244a  mov     r9, [rsp+68h+arg_18]
0x140002452  add     rsp, 68h
0x140002456  jmp     short $+2
0x140002458  jmp     rax
```
