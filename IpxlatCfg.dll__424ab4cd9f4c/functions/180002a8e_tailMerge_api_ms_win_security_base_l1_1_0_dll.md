# __tailMerge_api_ms_win_security_base_l1_1_0_dll

- ea: `0x180002a8e`
- end: `0x180002b07`
- name: `__tailMerge_api_ms_win_security_base_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b0d`

## callees

- `0x180002a8e`
- `0x180017cd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_base_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a8e  mov     [rsp+arg_0], rcx
0x180002a93  mov     [rsp+arg_8], rdx
0x180002a98  mov     [rsp+arg_10], r8
0x180002a9d  mov     [rsp+arg_18], r9
0x180002aa2  sub     rsp, 68h
0x180002aa6  movdqa  [rsp+68h+var_48], xmm0
0x180002aac  movdqa  [rsp+68h+var_38], xmm1
0x180002ab2  movdqa  [rsp+68h+var_28], xmm2
0x180002ab8  movdqa  [rsp+68h+var_18], xmm3
0x180002abe  mov     rdx, rax
0x180002ac1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_base_l1_1_0_dll
0x180002ac8  call    __delayLoadHelper2
0x180002acd  movdqa  xmm0, [rsp+68h+var_48]
0x180002ad3  movdqa  xmm1, [rsp+68h+var_38]
0x180002ad9  movdqa  xmm2, [rsp+68h+var_28]
0x180002adf  movdqa  xmm3, [rsp+68h+var_18]
0x180002ae5  mov     rcx, [rsp+68h+arg_0]
0x180002aea  mov     rdx, [rsp+68h+arg_8]
0x180002aef  mov     r8, [rsp+68h+arg_10]
0x180002af7  mov     r9, [rsp+68h+arg_18]
0x180002aff  add     rsp, 68h
0x180002b03  jmp     short $+2
0x180002b05  jmp     rax
```
