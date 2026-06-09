# __tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll

- ea: `0x140001cbf`
- end: `0x140001d38`
- name: `__tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001d3e`
- `0x140001d50`

## callees

- `0x140001cbf`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shcore_obsolete_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_obsolete_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001cbf  mov     [rsp+arg_0], rcx
0x140001cc4  mov     [rsp+arg_8], rdx
0x140001cc9  mov     [rsp+arg_10], r8
0x140001cce  mov     [rsp+arg_18], r9
0x140001cd3  sub     rsp, 68h
0x140001cd7  movdqa  [rsp+68h+var_48], xmm0
0x140001cdd  movdqa  [rsp+68h+var_38], xmm1
0x140001ce3  movdqa  [rsp+68h+var_28], xmm2
0x140001ce9  movdqa  [rsp+68h+var_18], xmm3
0x140001cef  mov     rdx, rax
0x140001cf2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_obsolete_l1_1_0_dll
0x140001cf9  call    __delayLoadHelper2
0x140001cfe  movdqa  xmm0, [rsp+68h+var_48]
0x140001d04  movdqa  xmm1, [rsp+68h+var_38]
0x140001d0a  movdqa  xmm2, [rsp+68h+var_28]
0x140001d10  movdqa  xmm3, [rsp+68h+var_18]
0x140001d16  mov     rcx, [rsp+68h+arg_0]
0x140001d1b  mov     rdx, [rsp+68h+arg_8]
0x140001d20  mov     r8, [rsp+68h+arg_10]
0x140001d28  mov     r9, [rsp+68h+arg_18]
0x140001d30  add     rsp, 68h
0x140001d34  jmp     short $+2
0x140001d36  jmp     rax
```
