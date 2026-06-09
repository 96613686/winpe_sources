# __tailMerge_ext_ms_win_imm_l1_1_0_dll

- ea: `0x140003102`
- end: `0x14000317b`
- name: `__tailMerge_ext_ms_win_imm_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003181`

## callees

- `0x140003102`
- `0x1400171b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_imm_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_imm_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003102  mov     [rsp+arg_0], rcx
0x140003107  mov     [rsp+arg_8], rdx
0x14000310c  mov     [rsp+arg_10], r8
0x140003111  mov     [rsp+arg_18], r9
0x140003116  sub     rsp, 68h
0x14000311a  movdqa  [rsp+68h+var_48], xmm0
0x140003120  movdqa  [rsp+68h+var_38], xmm1
0x140003126  movdqa  [rsp+68h+var_28], xmm2
0x14000312c  movdqa  [rsp+68h+var_18], xmm3
0x140003132  mov     rdx, rax
0x140003135  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_imm_l1_1_0_dll
0x14000313c  call    __delayLoadHelper2
0x140003141  movdqa  xmm0, [rsp+68h+var_48]
0x140003147  movdqa  xmm1, [rsp+68h+var_38]
0x14000314d  movdqa  xmm2, [rsp+68h+var_28]
0x140003153  movdqa  xmm3, [rsp+68h+var_18]
0x140003159  mov     rcx, [rsp+68h+arg_0]
0x14000315e  mov     rdx, [rsp+68h+arg_8]
0x140003163  mov     r8, [rsp+68h+arg_10]
0x14000316b  mov     r9, [rsp+68h+arg_18]
0x140003173  add     rsp, 68h
0x140003177  jmp     short $+2
0x140003179  jmp     rax
```
