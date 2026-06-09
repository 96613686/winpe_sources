# __tailMerge_api_ms_win_core_kernel32_legacy_l1_1_0_dll

- ea: `0x18000aacd`
- end: `0x18000ab46`
- name: `__tailMerge_api_ms_win_core_kernel32_legacy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ab4c`

## callees

- `0x180007cd0`
- `0x18000aacd`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_kernel32_legacy_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_kernel32_legacy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aacd  mov     [rsp+arg_0], rcx
0x18000aad2  mov     [rsp+arg_8], rdx
0x18000aad7  mov     [rsp+arg_10], r8
0x18000aadc  mov     [rsp+arg_18], r9
0x18000aae1  sub     rsp, 68h
0x18000aae5  movdqa  [rsp+68h+var_48], xmm0
0x18000aaeb  movdqa  [rsp+68h+var_38], xmm1
0x18000aaf1  movdqa  [rsp+68h+var_28], xmm2
0x18000aaf7  movdqa  [rsp+68h+var_18], xmm3
0x18000aafd  mov     rdx, rax
0x18000ab00  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_kernel32_legacy_l1_1_0_dll
0x18000ab07  call    __delayLoadHelper2
0x18000ab0c  movdqa  xmm0, [rsp+68h+var_48]
0x18000ab12  movdqa  xmm1, [rsp+68h+var_38]
0x18000ab18  movdqa  xmm2, [rsp+68h+var_28]
0x18000ab1e  movdqa  xmm3, [rsp+68h+var_18]
0x18000ab24  mov     rcx, [rsp+68h+arg_0]
0x18000ab29  mov     rdx, [rsp+68h+arg_8]
0x18000ab2e  mov     r8, [rsp+68h+arg_10]
0x18000ab36  mov     r9, [rsp+68h+arg_18]
0x18000ab3e  add     rsp, 68h
0x18000ab42  jmp     short $+2
0x18000ab44  jmp     rax
```
