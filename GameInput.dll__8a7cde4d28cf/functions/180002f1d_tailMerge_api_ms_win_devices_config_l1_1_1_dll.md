# __tailMerge_api_ms_win_devices_config_l1_1_1_dll

- ea: `0x180002f1d`
- end: `0x180002f96`
- name: `__tailMerge_api_ms_win_devices_config_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002f9c`
- `0x180002fae`
- `0x180002fc0`
- `0x180002fd2`
- `0x180002fe4`
- `0x180002ff6`
- `0x180003008`

## callees

- `0x180002f1d`
- `0x180047d30`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_config_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_config_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002f1d  mov     [rsp+arg_0], rcx
0x180002f22  mov     [rsp+arg_8], rdx
0x180002f27  mov     [rsp+arg_10], r8
0x180002f2c  mov     [rsp+arg_18], r9
0x180002f31  sub     rsp, 68h
0x180002f35  movdqa  [rsp+68h+var_48], xmm0
0x180002f3b  movdqa  [rsp+68h+var_38], xmm1
0x180002f41  movdqa  [rsp+68h+var_28], xmm2
0x180002f47  movdqa  [rsp+68h+var_18], xmm3
0x180002f4d  mov     rdx, rax
0x180002f50  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_config_l1_1_1_dll
0x180002f57  call    __delayLoadHelper2
0x180002f5c  movdqa  xmm0, [rsp+68h+var_48]
0x180002f62  movdqa  xmm1, [rsp+68h+var_38]
0x180002f68  movdqa  xmm2, [rsp+68h+var_28]
0x180002f6e  movdqa  xmm3, [rsp+68h+var_18]
0x180002f74  mov     rcx, [rsp+68h+arg_0]
0x180002f79  mov     rdx, [rsp+68h+arg_8]
0x180002f7e  mov     r8, [rsp+68h+arg_10]
0x180002f86  mov     r9, [rsp+68h+arg_18]
0x180002f8e  add     rsp, 68h
0x180002f92  jmp     short $+2
0x180002f94  jmp     rax
```
