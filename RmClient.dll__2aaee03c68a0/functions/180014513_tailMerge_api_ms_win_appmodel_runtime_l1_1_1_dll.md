# __tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll

- ea: `0x180014513`
- end: `0x18001458c`
- name: `__tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014592`

## callees

- `0x18000f260`
- `0x180014513`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180014513  mov     [rsp+arg_0], rcx
0x180014518  mov     [rsp+arg_8], rdx
0x18001451d  mov     [rsp+arg_10], r8
0x180014522  mov     [rsp+arg_18], r9
0x180014527  sub     rsp, 68h
0x18001452b  movdqa  [rsp+68h+var_48], xmm0
0x180014531  movdqa  [rsp+68h+var_38], xmm1
0x180014537  movdqa  [rsp+68h+var_28], xmm2
0x18001453d  movdqa  [rsp+68h+var_18], xmm3
0x180014543  mov     rdx, rax
0x180014546  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_1_dll
0x18001454d  call    __delayLoadHelper2
0x180014552  movdqa  xmm0, [rsp+68h+var_48]
0x180014558  movdqa  xmm1, [rsp+68h+var_38]
0x18001455e  movdqa  xmm2, [rsp+68h+var_28]
0x180014564  movdqa  xmm3, [rsp+68h+var_18]
0x18001456a  mov     rcx, [rsp+68h+arg_0]
0x18001456f  mov     rdx, [rsp+68h+arg_8]
0x180014574  mov     r8, [rsp+68h+arg_10]
0x18001457c  mov     r9, [rsp+68h+arg_18]
0x180014584  add     rsp, 68h
0x180014588  jmp     short $+2
0x18001458a  jmp     rax
```
