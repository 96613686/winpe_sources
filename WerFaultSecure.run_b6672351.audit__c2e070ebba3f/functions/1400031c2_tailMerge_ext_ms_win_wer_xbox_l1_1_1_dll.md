# __tailMerge_ext_ms_win_wer_xbox_l1_1_1_dll

- ea: `0x1400031c2`
- end: `0x14000323b`
- name: `__tailMerge_ext_ms_win_wer_xbox_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003241`
- `0x140003253`

## callees

- `0x1400031c2`
- `0x140010620`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_wer_xbox_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_wer_xbox_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400031c2  mov     [rsp+arg_0], rcx
0x1400031c7  mov     [rsp+arg_8], rdx
0x1400031cc  mov     [rsp+arg_10], r8
0x1400031d1  mov     [rsp+arg_18], r9
0x1400031d6  sub     rsp, 68h
0x1400031da  movdqa  [rsp+68h+var_48], xmm0
0x1400031e0  movdqa  [rsp+68h+var_38], xmm1
0x1400031e6  movdqa  [rsp+68h+var_28], xmm2
0x1400031ec  movdqa  [rsp+68h+var_18], xmm3
0x1400031f2  mov     rdx, rax
0x1400031f5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_wer_xbox_l1_1_1_dll
0x1400031fc  call    __delayLoadHelper2
0x140003201  movdqa  xmm0, [rsp+68h+var_48]
0x140003207  movdqa  xmm1, [rsp+68h+var_38]
0x14000320d  movdqa  xmm2, [rsp+68h+var_28]
0x140003213  movdqa  xmm3, [rsp+68h+var_18]
0x140003219  mov     rcx, [rsp+68h+arg_0]
0x14000321e  mov     rdx, [rsp+68h+arg_8]
0x140003223  mov     r8, [rsp+68h+arg_10]
0x14000322b  mov     r9, [rsp+68h+arg_18]
0x140003233  add     rsp, 68h
0x140003237  jmp     short $+2
0x140003239  jmp     rax
```
