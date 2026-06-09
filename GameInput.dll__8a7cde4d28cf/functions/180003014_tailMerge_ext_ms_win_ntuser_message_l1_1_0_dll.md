# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x180003014`
- end: `0x18000308d`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003093`
- `0x1800030a5`
- `0x1800030b7`
- `0x1800030c9`
- `0x1800030db`

## callees

- `0x180003014`
- `0x180047d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003014  mov     [rsp+arg_0], rcx
0x180003019  mov     [rsp+arg_8], rdx
0x18000301e  mov     [rsp+arg_10], r8
0x180003023  mov     [rsp+arg_18], r9
0x180003028  sub     rsp, 68h
0x18000302c  movdqa  [rsp+68h+var_48], xmm0
0x180003032  movdqa  [rsp+68h+var_38], xmm1
0x180003038  movdqa  [rsp+68h+var_28], xmm2
0x18000303e  movdqa  [rsp+68h+var_18], xmm3
0x180003044  mov     rdx, rax
0x180003047  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x18000304e  call    __delayLoadHelper2
0x180003053  movdqa  xmm0, [rsp+68h+var_48]
0x180003059  movdqa  xmm1, [rsp+68h+var_38]
0x18000305f  movdqa  xmm2, [rsp+68h+var_28]
0x180003065  movdqa  xmm3, [rsp+68h+var_18]
0x18000306b  mov     rcx, [rsp+68h+arg_0]
0x180003070  mov     rdx, [rsp+68h+arg_8]
0x180003075  mov     r8, [rsp+68h+arg_10]
0x18000307d  mov     r9, [rsp+68h+arg_18]
0x180003085  add     rsp, 68h
0x180003089  jmp     short $+2
0x18000308b  jmp     rax
```
