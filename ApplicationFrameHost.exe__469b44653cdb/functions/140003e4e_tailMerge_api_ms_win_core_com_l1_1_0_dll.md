# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x140003e4e`
- end: `0x140003ec7`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003ecd`
- `0x140003edf`
- `0x140003f7c`
- `0x140003f8e`
- `0x140003fa0`
- `0x140003fb2`

## callees

- `0x1400023e0`
- `0x140003e4e`

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
0x140003e4e  mov     [rsp+arg_0], rcx
0x140003e53  mov     [rsp+arg_8], rdx
0x140003e58  mov     [rsp+arg_10], r8
0x140003e5d  mov     [rsp+arg_18], r9
0x140003e62  sub     rsp, 68h
0x140003e66  movdqa  [rsp+68h+var_48], xmm0
0x140003e6c  movdqa  [rsp+68h+var_38], xmm1
0x140003e72  movdqa  [rsp+68h+var_28], xmm2
0x140003e78  movdqa  [rsp+68h+var_18], xmm3
0x140003e7e  mov     rdx, rax
0x140003e81  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x140003e88  call    __delayLoadHelper2
0x140003e8d  movdqa  xmm0, [rsp+68h+var_48]
0x140003e93  movdqa  xmm1, [rsp+68h+var_38]
0x140003e99  movdqa  xmm2, [rsp+68h+var_28]
0x140003e9f  movdqa  xmm3, [rsp+68h+var_18]
0x140003ea5  mov     rcx, [rsp+68h+arg_0]
0x140003eaa  mov     rdx, [rsp+68h+arg_8]
0x140003eaf  mov     r8, [rsp+68h+arg_10]
0x140003eb7  mov     r9, [rsp+68h+arg_18]
0x140003ebf  add     rsp, 68h
0x140003ec3  jmp     short $+2
0x140003ec5  jmp     rax
```
