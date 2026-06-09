# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x140001fb9`
- end: `0x140002032`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002038`
- `0x14000204a`
- `0x14000205c`
- `0x14000206e`

## callees

- `0x140001fb9`
- `0x140012e70`

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
0x140001fb9  mov     [rsp+arg_0], rcx
0x140001fbe  mov     [rsp+arg_8], rdx
0x140001fc3  mov     [rsp+arg_10], r8
0x140001fc8  mov     [rsp+arg_18], r9
0x140001fcd  sub     rsp, 68h
0x140001fd1  movdqa  [rsp+68h+var_48], xmm0
0x140001fd7  movdqa  [rsp+68h+var_38], xmm1
0x140001fdd  movdqa  [rsp+68h+var_28], xmm2
0x140001fe3  movdqa  [rsp+68h+var_18], xmm3
0x140001fe9  mov     rdx, rax
0x140001fec  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x140001ff3  call    __delayLoadHelper2
0x140001ff8  movdqa  xmm0, [rsp+68h+var_48]
0x140001ffe  movdqa  xmm1, [rsp+68h+var_38]
0x140002004  movdqa  xmm2, [rsp+68h+var_28]
0x14000200a  movdqa  xmm3, [rsp+68h+var_18]
0x140002010  mov     rcx, [rsp+68h+arg_0]
0x140002015  mov     rdx, [rsp+68h+arg_8]
0x14000201a  mov     r8, [rsp+68h+arg_10]
0x140002022  mov     r9, [rsp+68h+arg_18]
0x14000202a  add     rsp, 68h
0x14000202e  jmp     short $+2
0x140002030  jmp     rax
```
