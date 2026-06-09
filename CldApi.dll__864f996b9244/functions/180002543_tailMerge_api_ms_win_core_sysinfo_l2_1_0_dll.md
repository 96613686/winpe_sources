# __tailMerge_api_ms_win_core_sysinfo_l2_1_0_dll

- ea: `0x180002543`
- end: `0x1800025bc`
- name: `__tailMerge_api_ms_win_core_sysinfo_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025c2`

## callees

- `0x180002543`
- `0x18001bb20`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_sysinfo_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_sysinfo_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002543  mov     [rsp+arg_0], rcx
0x180002548  mov     [rsp+arg_8], rdx
0x18000254d  mov     [rsp+arg_10], r8
0x180002552  mov     [rsp+arg_18], r9
0x180002557  sub     rsp, 68h
0x18000255b  movdqa  [rsp+68h+var_48], xmm0
0x180002561  movdqa  [rsp+68h+var_38], xmm1
0x180002567  movdqa  [rsp+68h+var_28], xmm2
0x18000256d  movdqa  [rsp+68h+var_18], xmm3
0x180002573  mov     rdx, rax
0x180002576  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_sysinfo_l2_1_0_dll
0x18000257d  call    __delayLoadHelper2
0x180002582  movdqa  xmm0, [rsp+68h+var_48]
0x180002588  movdqa  xmm1, [rsp+68h+var_38]
0x18000258e  movdqa  xmm2, [rsp+68h+var_28]
0x180002594  movdqa  xmm3, [rsp+68h+var_18]
0x18000259a  mov     rcx, [rsp+68h+arg_0]
0x18000259f  mov     rdx, [rsp+68h+arg_8]
0x1800025a4  mov     r8, [rsp+68h+arg_10]
0x1800025ac  mov     r9, [rsp+68h+arg_18]
0x1800025b4  add     rsp, 68h
0x1800025b8  jmp     short $+2
0x1800025ba  jmp     rax
```
