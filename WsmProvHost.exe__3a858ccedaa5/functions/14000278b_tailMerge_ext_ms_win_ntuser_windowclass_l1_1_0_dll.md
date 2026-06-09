# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x14000278b`
- end: `0x140002804`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000280a`
- `0x14000281c`

## callees

- `0x14000278b`
- `0x140004270`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000278b  mov     [rsp+arg_0], rcx
0x140002790  mov     [rsp+arg_8], rdx
0x140002795  mov     [rsp+arg_10], r8
0x14000279a  mov     [rsp+arg_18], r9
0x14000279f  sub     rsp, 68h
0x1400027a3  movdqa  [rsp+68h+var_48], xmm0
0x1400027a9  movdqa  [rsp+68h+var_38], xmm1
0x1400027af  movdqa  [rsp+68h+var_28], xmm2
0x1400027b5  movdqa  [rsp+68h+var_18], xmm3
0x1400027bb  mov     rdx, rax
0x1400027be  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x1400027c5  call    __delayLoadHelper2
0x1400027ca  movdqa  xmm0, [rsp+68h+var_48]
0x1400027d0  movdqa  xmm1, [rsp+68h+var_38]
0x1400027d6  movdqa  xmm2, [rsp+68h+var_28]
0x1400027dc  movdqa  xmm3, [rsp+68h+var_18]
0x1400027e2  mov     rcx, [rsp+68h+arg_0]
0x1400027e7  mov     rdx, [rsp+68h+arg_8]
0x1400027ec  mov     r8, [rsp+68h+arg_10]
0x1400027f4  mov     r9, [rsp+68h+arg_18]
0x1400027fc  add     rsp, 68h
0x140002800  jmp     short $+2
0x140002802  jmp     rax
```
