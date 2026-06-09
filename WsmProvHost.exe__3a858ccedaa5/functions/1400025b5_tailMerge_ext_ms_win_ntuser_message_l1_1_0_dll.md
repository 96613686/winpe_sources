# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x1400025b5`
- end: `0x14000262e`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002634`
- `0x140002646`
- `0x140002658`
- `0x14000266a`

## callees

- `0x1400025b5`
- `0x140004270`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400025b5  mov     [rsp+arg_0], rcx
0x1400025ba  mov     [rsp+arg_8], rdx
0x1400025bf  mov     [rsp+arg_10], r8
0x1400025c4  mov     [rsp+arg_18], r9
0x1400025c9  sub     rsp, 68h
0x1400025cd  movdqa  [rsp+68h+var_48], xmm0
0x1400025d3  movdqa  [rsp+68h+var_38], xmm1
0x1400025d9  movdqa  [rsp+68h+var_28], xmm2
0x1400025df  movdqa  [rsp+68h+var_18], xmm3
0x1400025e5  mov     rdx, rax
0x1400025e8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x1400025ef  call    __delayLoadHelper2
0x1400025f4  movdqa  xmm0, [rsp+68h+var_48]
0x1400025fa  movdqa  xmm1, [rsp+68h+var_38]
0x140002600  movdqa  xmm2, [rsp+68h+var_28]
0x140002606  movdqa  xmm3, [rsp+68h+var_18]
0x14000260c  mov     rcx, [rsp+68h+arg_0]
0x140002611  mov     rdx, [rsp+68h+arg_8]
0x140002616  mov     r8, [rsp+68h+arg_10]
0x14000261e  mov     r9, [rsp+68h+arg_18]
0x140002626  add     rsp, 68h
0x14000262a  jmp     short $+2
0x14000262c  jmp     rax
```
