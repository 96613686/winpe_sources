# __tailMerge_api_ms_win_devices_query_l1_1_0_dll

- ea: `0x18000ab58`
- end: `0x18000abd1`
- name: `__tailMerge_api_ms_win_devices_query_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000abd7`
- `0x18000abfb`

## callees

- `0x180007cd0`
- `0x18000ab58`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ab58  mov     [rsp+arg_0], rcx
0x18000ab5d  mov     [rsp+arg_8], rdx
0x18000ab62  mov     [rsp+arg_10], r8
0x18000ab67  mov     [rsp+arg_18], r9
0x18000ab6c  sub     rsp, 68h
0x18000ab70  movdqa  [rsp+68h+var_48], xmm0
0x18000ab76  movdqa  [rsp+68h+var_38], xmm1
0x18000ab7c  movdqa  [rsp+68h+var_28], xmm2
0x18000ab82  movdqa  [rsp+68h+var_18], xmm3
0x18000ab88  mov     rdx, rax
0x18000ab8b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_query_l1_1_0_dll
0x18000ab92  call    __delayLoadHelper2
0x18000ab97  movdqa  xmm0, [rsp+68h+var_48]
0x18000ab9d  movdqa  xmm1, [rsp+68h+var_38]
0x18000aba3  movdqa  xmm2, [rsp+68h+var_28]
0x18000aba9  movdqa  xmm3, [rsp+68h+var_18]
0x18000abaf  mov     rcx, [rsp+68h+arg_0]
0x18000abb4  mov     rdx, [rsp+68h+arg_8]
0x18000abb9  mov     r8, [rsp+68h+arg_10]
0x18000abc1  mov     r9, [rsp+68h+arg_18]
0x18000abc9  add     rsp, 68h
0x18000abcd  jmp     short $+2
0x18000abcf  jmp     rax
```
