# __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_0_dll

- ea: `0x180002609`
- end: `0x180002682`
- name: `__tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002688`
- `0x18000269a`

## callees

- `0x180002609`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002609  mov     [rsp+arg_0], rcx
0x18000260e  mov     [rsp+arg_8], rdx
0x180002613  mov     [rsp+arg_10], r8
0x180002618  mov     [rsp+arg_18], r9
0x18000261d  sub     rsp, 68h
0x180002621  movdqa  [rsp+68h+var_48], xmm0
0x180002627  movdqa  [rsp+68h+var_38], xmm1
0x18000262d  movdqa  [rsp+68h+var_28], xmm2
0x180002633  movdqa  [rsp+68h+var_18], xmm3
0x180002639  mov     rdx, rax
0x18000263c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_0_dll
0x180002643  call    __delayLoadHelper2
0x180002648  movdqa  xmm0, [rsp+68h+var_48]
0x18000264e  movdqa  xmm1, [rsp+68h+var_38]
0x180002654  movdqa  xmm2, [rsp+68h+var_28]
0x18000265a  movdqa  xmm3, [rsp+68h+var_18]
0x180002660  mov     rcx, [rsp+68h+arg_0]
0x180002665  mov     rdx, [rsp+68h+arg_8]
0x18000266a  mov     r8, [rsp+68h+arg_10]
0x180002672  mov     r9, [rsp+68h+arg_18]
0x18000267a  add     rsp, 68h
0x18000267e  jmp     short $+2
0x180002680  jmp     rax
```
