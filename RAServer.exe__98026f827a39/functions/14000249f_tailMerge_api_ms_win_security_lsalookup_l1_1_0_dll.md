# __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll

- ea: `0x14000249f`
- end: `0x140002518`
- name: `__tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000251e`

## callees

- `0x14000249f`
- `0x140015970`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000249f  mov     [rsp+arg_0], rcx
0x1400024a4  mov     [rsp+arg_8], rdx
0x1400024a9  mov     [rsp+arg_10], r8
0x1400024ae  mov     [rsp+arg_18], r9
0x1400024b3  sub     rsp, 68h
0x1400024b7  movdqa  [rsp+68h+var_48], xmm0
0x1400024bd  movdqa  [rsp+68h+var_38], xmm1
0x1400024c3  movdqa  [rsp+68h+var_28], xmm2
0x1400024c9  movdqa  [rsp+68h+var_18], xmm3
0x1400024cf  mov     rdx, rax
0x1400024d2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l1_1_0_dll
0x1400024d9  call    __delayLoadHelper2
0x1400024de  movdqa  xmm0, [rsp+68h+var_48]
0x1400024e4  movdqa  xmm1, [rsp+68h+var_38]
0x1400024ea  movdqa  xmm2, [rsp+68h+var_28]
0x1400024f0  movdqa  xmm3, [rsp+68h+var_18]
0x1400024f6  mov     rcx, [rsp+68h+arg_0]
0x1400024fb  mov     rdx, [rsp+68h+arg_8]
0x140002500  mov     r8, [rsp+68h+arg_10]
0x140002508  mov     r9, [rsp+68h+arg_18]
0x140002510  add     rsp, 68h
0x140002514  jmp     short $+2
0x140002516  jmp     rax
```
