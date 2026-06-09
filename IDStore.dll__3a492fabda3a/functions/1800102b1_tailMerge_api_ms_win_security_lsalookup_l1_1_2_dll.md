# __tailMerge_api_ms_win_security_lsalookup_l1_1_2_dll

- ea: `0x1800102b1`
- end: `0x18001032a`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010330`

## callees

- `0x18000e230`
- `0x1800102b1`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800102b1  mov     [rsp+arg_0], rcx
0x1800102b6  mov     [rsp+arg_8], rdx
0x1800102bb  mov     [rsp+arg_10], r8
0x1800102c0  mov     [rsp+arg_18], r9
0x1800102c5  sub     rsp, 68h
0x1800102c9  movdqa  [rsp+68h+var_48], xmm0
0x1800102cf  movdqa  [rsp+68h+var_38], xmm1
0x1800102d5  movdqa  [rsp+68h+var_28], xmm2
0x1800102db  movdqa  [rsp+68h+var_18], xmm3
0x1800102e1  mov     rdx, rax
0x1800102e4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_2_dll
0x1800102eb  call    __delayLoadHelper2
0x1800102f0  movdqa  xmm0, [rsp+68h+var_48]
0x1800102f6  movdqa  xmm1, [rsp+68h+var_38]
0x1800102fc  movdqa  xmm2, [rsp+68h+var_28]
0x180010302  movdqa  xmm3, [rsp+68h+var_18]
0x180010308  mov     rcx, [rsp+68h+arg_0]
0x18001030d  mov     rdx, [rsp+68h+arg_8]
0x180010312  mov     r8, [rsp+68h+arg_10]
0x18001031a  mov     r9, [rsp+68h+arg_18]
0x180010322  add     rsp, 68h
0x180010326  jmp     short $+2
0x180010328  jmp     rax
```
