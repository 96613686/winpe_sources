# __tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll

- ea: `0x140009cd8`
- end: `0x140009d51`
- name: `__tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009d57`

## callees

- `0x140006ad0`
- `0x140009cd8`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140009cd8  mov     [rsp+arg_0], rcx
0x140009cdd  mov     [rsp+arg_8], rdx
0x140009ce2  mov     [rsp+arg_10], r8
0x140009ce7  mov     [rsp+arg_18], r9
0x140009cec  sub     rsp, 68h
0x140009cf0  movdqa  [rsp+68h+var_48], xmm0
0x140009cf6  movdqa  [rsp+68h+var_38], xmm1
0x140009cfc  movdqa  [rsp+68h+var_28], xmm2
0x140009d02  movdqa  [rsp+68h+var_18], xmm3
0x140009d08  mov     rdx, rax
0x140009d0b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_1_dll
0x140009d12  call    __delayLoadHelper2
0x140009d17  movdqa  xmm0, [rsp+68h+var_48]
0x140009d1d  movdqa  xmm1, [rsp+68h+var_38]
0x140009d23  movdqa  xmm2, [rsp+68h+var_28]
0x140009d29  movdqa  xmm3, [rsp+68h+var_18]
0x140009d2f  mov     rcx, [rsp+68h+arg_0]
0x140009d34  mov     rdx, [rsp+68h+arg_8]
0x140009d39  mov     r8, [rsp+68h+arg_10]
0x140009d41  mov     r9, [rsp+68h+arg_18]
0x140009d49  add     rsp, 68h
0x140009d4d  jmp     short $+2
0x140009d4f  jmp     rax
```
