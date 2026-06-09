# __tailMerge_api_ms_win_devices_config_l1_1_1_dll

- ea: `0x18000a483`
- end: `0x18000a4fc`
- name: `__tailMerge_api_ms_win_devices_config_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a57b`
- `0x18000a788`
- `0x18000a8b0`
- `0x18000a8c2`
- `0x18000a8d4`
- `0x18000a8e6`
- `0x18000a8f8`

## callees

- `0x180006050`
- `0x18000a483`

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
0x18000a483  mov     [rsp+arg_0], rcx
0x18000a488  mov     [rsp+arg_8], rdx
0x18000a48d  mov     [rsp+arg_10], r8
0x18000a492  mov     [rsp+arg_18], r9
0x18000a497  sub     rsp, 68h
0x18000a49b  movdqa  [rsp+68h+var_48], xmm0
0x18000a4a1  movdqa  [rsp+68h+var_38], xmm1
0x18000a4a7  movdqa  [rsp+68h+var_28], xmm2
0x18000a4ad  movdqa  [rsp+68h+var_18], xmm3
0x18000a4b3  mov     rdx, rax
0x18000a4b6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_config_l1_1_1_dll
0x18000a4bd  call    __delayLoadHelper2
0x18000a4c2  movdqa  xmm0, [rsp+68h+var_48]
0x18000a4c8  movdqa  xmm1, [rsp+68h+var_38]
0x18000a4ce  movdqa  xmm2, [rsp+68h+var_28]
0x18000a4d4  movdqa  xmm3, [rsp+68h+var_18]
0x18000a4da  mov     rcx, [rsp+68h+arg_0]
0x18000a4df  mov     rdx, [rsp+68h+arg_8]
0x18000a4e4  mov     r8, [rsp+68h+arg_10]
0x18000a4ec  mov     r9, [rsp+68h+arg_18]
0x18000a4f4  add     rsp, 68h
0x18000a4f8  jmp     short $+2
0x18000a4fa  jmp     rax
```
