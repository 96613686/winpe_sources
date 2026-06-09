# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000238b`
- end: `0x180002404`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000240a`
- `0x180002440`

## callees

- `0x18000238b`
- `0x18002cea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000238b  mov     [rsp+arg_0], rcx
0x180002390  mov     [rsp+arg_8], rdx
0x180002395  mov     [rsp+arg_10], r8
0x18000239a  mov     [rsp+arg_18], r9
0x18000239f  sub     rsp, 68h
0x1800023a3  movdqa  [rsp+68h+var_48], xmm0
0x1800023a9  movdqa  [rsp+68h+var_38], xmm1
0x1800023af  movdqa  [rsp+68h+var_28], xmm2
0x1800023b5  movdqa  [rsp+68h+var_18], xmm3
0x1800023bb  mov     rdx, rax
0x1800023be  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x1800023c5  call    __delayLoadHelper2
0x1800023ca  movdqa  xmm0, [rsp+68h+var_48]
0x1800023d0  movdqa  xmm1, [rsp+68h+var_38]
0x1800023d6  movdqa  xmm2, [rsp+68h+var_28]
0x1800023dc  movdqa  xmm3, [rsp+68h+var_18]
0x1800023e2  mov     rcx, [rsp+68h+arg_0]
0x1800023e7  mov     rdx, [rsp+68h+arg_8]
0x1800023ec  mov     r8, [rsp+68h+arg_10]
0x1800023f4  mov     r9, [rsp+68h+arg_18]
0x1800023fc  add     rsp, 68h
0x180002400  jmp     short $+2
0x180002402  jmp     rax
```
