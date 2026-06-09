# __tailMerge_api_ms_win_devices_config_l1_1_1_dll

- ea: `0x180011111`
- end: `0x18001118a`
- name: `__tailMerge_api_ms_win_devices_config_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180011190`

## callees

- `0x18000f240`
- `0x180011111`

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
0x180011111  mov     [rsp+arg_0], rcx
0x180011116  mov     [rsp+arg_8], rdx
0x18001111b  mov     [rsp+arg_10], r8
0x180011120  mov     [rsp+arg_18], r9
0x180011125  sub     rsp, 68h
0x180011129  movdqa  [rsp+68h+var_48], xmm0
0x18001112f  movdqa  [rsp+68h+var_38], xmm1
0x180011135  movdqa  [rsp+68h+var_28], xmm2
0x18001113b  movdqa  [rsp+68h+var_18], xmm3
0x180011141  mov     rdx, rax
0x180011144  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_config_l1_1_1_dll
0x18001114b  call    __delayLoadHelper2
0x180011150  movdqa  xmm0, [rsp+68h+var_48]
0x180011156  movdqa  xmm1, [rsp+68h+var_38]
0x18001115c  movdqa  xmm2, [rsp+68h+var_28]
0x180011162  movdqa  xmm3, [rsp+68h+var_18]
0x180011168  mov     rcx, [rsp+68h+arg_0]
0x18001116d  mov     rdx, [rsp+68h+arg_8]
0x180011172  mov     r8, [rsp+68h+arg_10]
0x18001117a  mov     r9, [rsp+68h+arg_18]
0x180011182  add     rsp, 68h
0x180011186  jmp     short $+2
0x180011188  jmp     rax
```
