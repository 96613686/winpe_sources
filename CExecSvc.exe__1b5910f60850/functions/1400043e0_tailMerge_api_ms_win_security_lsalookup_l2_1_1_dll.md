# __tailMerge_api_ms_win_security_lsalookup_l2_1_1_dll

- ea: `0x1400043e0`
- end: `0x140004459`
- name: `__tailMerge_api_ms_win_security_lsalookup_l2_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000445f`

## callees

- `0x1400043e0`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_lsalookup_l2_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400043e0  mov     [rsp+arg_0], rcx
0x1400043e5  mov     [rsp+arg_8], rdx
0x1400043ea  mov     [rsp+arg_10], r8
0x1400043ef  mov     [rsp+arg_18], r9
0x1400043f4  sub     rsp, 68h
0x1400043f8  movdqa  [rsp+68h+var_48], xmm0
0x1400043fe  movdqa  [rsp+68h+var_38], xmm1
0x140004404  movdqa  [rsp+68h+var_28], xmm2
0x14000440a  movdqa  [rsp+68h+var_18], xmm3
0x140004410  mov     rdx, rax
0x140004413  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_lsalookup_l2_1_1_dll
0x14000441a  call    __delayLoadHelper2
0x14000441f  movdqa  xmm0, [rsp+68h+var_48]
0x140004425  movdqa  xmm1, [rsp+68h+var_38]
0x14000442b  movdqa  xmm2, [rsp+68h+var_28]
0x140004431  movdqa  xmm3, [rsp+68h+var_18]
0x140004437  mov     rcx, [rsp+68h+arg_0]
0x14000443c  mov     rdx, [rsp+68h+arg_8]
0x140004441  mov     r8, [rsp+68h+arg_10]
0x140004449  mov     r9, [rsp+68h+arg_18]
0x140004451  add     rsp, 68h
0x140004455  jmp     short $+2
0x140004457  jmp     rax
```
