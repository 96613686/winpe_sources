# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000a3f8`
- end: `0x18000a471`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a477`
- `0x18000a6b5`
- `0x18000a6c7`
- `0x18000a776`
- `0x18000a9cb`

## callees

- `0x180006050`
- `0x18000a3f8`

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
0x18000a3f8  mov     [rsp+arg_0], rcx
0x18000a3fd  mov     [rsp+arg_8], rdx
0x18000a402  mov     [rsp+arg_10], r8
0x18000a407  mov     [rsp+arg_18], r9
0x18000a40c  sub     rsp, 68h
0x18000a410  movdqa  [rsp+68h+var_48], xmm0
0x18000a416  movdqa  [rsp+68h+var_38], xmm1
0x18000a41c  movdqa  [rsp+68h+var_28], xmm2
0x18000a422  movdqa  [rsp+68h+var_18], xmm3
0x18000a428  mov     rdx, rax
0x18000a42b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000a432  call    __delayLoadHelper2
0x18000a437  movdqa  xmm0, [rsp+68h+var_48]
0x18000a43d  movdqa  xmm1, [rsp+68h+var_38]
0x18000a443  movdqa  xmm2, [rsp+68h+var_28]
0x18000a449  movdqa  xmm3, [rsp+68h+var_18]
0x18000a44f  mov     rcx, [rsp+68h+arg_0]
0x18000a454  mov     rdx, [rsp+68h+arg_8]
0x18000a459  mov     r8, [rsp+68h+arg_10]
0x18000a461  mov     r9, [rsp+68h+arg_18]
0x18000a469  add     rsp, 68h
0x18000a46d  jmp     short $+2
0x18000a46f  jmp     rax
```
