# __tailMerge_ext_ms_win_ntuser_synch_l1_1_0_dll

- ea: `0x140002828`
- end: `0x1400028a1`
- name: `__tailMerge_ext_ms_win_ntuser_synch_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400028a7`

## callees

- `0x140002828`
- `0x140004270`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_synch_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_synch_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002828  mov     [rsp+arg_0], rcx
0x14000282d  mov     [rsp+arg_8], rdx
0x140002832  mov     [rsp+arg_10], r8
0x140002837  mov     [rsp+arg_18], r9
0x14000283c  sub     rsp, 68h
0x140002840  movdqa  [rsp+68h+var_48], xmm0
0x140002846  movdqa  [rsp+68h+var_38], xmm1
0x14000284c  movdqa  [rsp+68h+var_28], xmm2
0x140002852  movdqa  [rsp+68h+var_18], xmm3
0x140002858  mov     rdx, rax
0x14000285b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_synch_l1_1_0_dll
0x140002862  call    __delayLoadHelper2
0x140002867  movdqa  xmm0, [rsp+68h+var_48]
0x14000286d  movdqa  xmm1, [rsp+68h+var_38]
0x140002873  movdqa  xmm2, [rsp+68h+var_28]
0x140002879  movdqa  xmm3, [rsp+68h+var_18]
0x14000287f  mov     rcx, [rsp+68h+arg_0]
0x140002884  mov     rdx, [rsp+68h+arg_8]
0x140002889  mov     r8, [rsp+68h+arg_10]
0x140002891  mov     r9, [rsp+68h+arg_18]
0x140002899  add     rsp, 68h
0x14000289d  jmp     short $+2
0x14000289f  jmp     rax
```
