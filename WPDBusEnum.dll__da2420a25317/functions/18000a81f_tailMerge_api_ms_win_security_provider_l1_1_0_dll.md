# __tailMerge_api_ms_win_security_provider_l1_1_0_dll

- ea: `0x18000a81f`
- end: `0x18000a898`
- name: `__tailMerge_api_ms_win_security_provider_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a89e`
- `0x18000ae32`
- `0x18000ae44`

## callees

- `0x180006050`
- `0x18000a81f`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_security_provider_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a81f  mov     [rsp+arg_0], rcx
0x18000a824  mov     [rsp+arg_8], rdx
0x18000a829  mov     [rsp+arg_10], r8
0x18000a82e  mov     [rsp+arg_18], r9
0x18000a833  sub     rsp, 68h
0x18000a837  movdqa  [rsp+68h+var_48], xmm0
0x18000a83d  movdqa  [rsp+68h+var_38], xmm1
0x18000a843  movdqa  [rsp+68h+var_28], xmm2
0x18000a849  movdqa  [rsp+68h+var_18], xmm3
0x18000a84f  mov     rdx, rax
0x18000a852  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_security_provider_l1_1_0_dll
0x18000a859  call    __delayLoadHelper2
0x18000a85e  movdqa  xmm0, [rsp+68h+var_48]
0x18000a864  movdqa  xmm1, [rsp+68h+var_38]
0x18000a86a  movdqa  xmm2, [rsp+68h+var_28]
0x18000a870  movdqa  xmm3, [rsp+68h+var_18]
0x18000a876  mov     rcx, [rsp+68h+arg_0]
0x18000a87b  mov     rdx, [rsp+68h+arg_8]
0x18000a880  mov     r8, [rsp+68h+arg_10]
0x18000a888  mov     r9, [rsp+68h+arg_18]
0x18000a890  add     rsp, 68h
0x18000a894  jmp     short $+2
0x18000a896  jmp     rax
```
