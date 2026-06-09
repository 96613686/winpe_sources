# __tailMerge_api_ms_win_appmodel_runtime_l1_1_0_dll

- ea: `0x180013aa1`
- end: `0x180013b1a`
- name: `__tailMerge_api_ms_win_appmodel_runtime_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013b20`

## callees

- `0x180010e10`
- `0x180013aa1`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013aa1  mov     [rsp+arg_0], rcx
0x180013aa6  mov     [rsp+arg_8], rdx
0x180013aab  mov     [rsp+arg_10], r8
0x180013ab0  mov     [rsp+arg_18], r9
0x180013ab5  sub     rsp, 68h
0x180013ab9  movdqa  [rsp+68h+var_48], xmm0
0x180013abf  movdqa  [rsp+68h+var_38], xmm1
0x180013ac5  movdqa  [rsp+68h+var_28], xmm2
0x180013acb  movdqa  [rsp+68h+var_18], xmm3
0x180013ad1  mov     rdx, rax
0x180013ad4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_l1_1_0_dll
0x180013adb  call    __delayLoadHelper2
0x180013ae0  movdqa  xmm0, [rsp+68h+var_48]
0x180013ae6  movdqa  xmm1, [rsp+68h+var_38]
0x180013aec  movdqa  xmm2, [rsp+68h+var_28]
0x180013af2  movdqa  xmm3, [rsp+68h+var_18]
0x180013af8  mov     rcx, [rsp+68h+arg_0]
0x180013afd  mov     rdx, [rsp+68h+arg_8]
0x180013b02  mov     r8, [rsp+68h+arg_10]
0x180013b0a  mov     r9, [rsp+68h+arg_18]
0x180013b12  add     rsp, 68h
0x180013b16  jmp     short $+2
0x180013b18  jmp     rax
```
