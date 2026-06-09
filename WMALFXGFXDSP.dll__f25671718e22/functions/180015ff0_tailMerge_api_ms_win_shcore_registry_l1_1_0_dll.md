# __tailMerge_api_ms_win_shcore_registry_l1_1_0_dll

- ea: `0x180015ff0`
- end: `0x180016069`
- name: `__tailMerge_api_ms_win_shcore_registry_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001606f`

## callees

- `0x1800131d0`
- `0x180015ff0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shcore_registry_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_registry_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015ff0  mov     [rsp+arg_0], rcx
0x180015ff5  mov     [rsp+arg_8], rdx
0x180015ffa  mov     [rsp+arg_10], r8
0x180015fff  mov     [rsp+arg_18], r9
0x180016004  sub     rsp, 68h
0x180016008  movdqa  [rsp+68h+var_48], xmm0
0x18001600e  movdqa  [rsp+68h+var_38], xmm1
0x180016014  movdqa  [rsp+68h+var_28], xmm2
0x18001601a  movdqa  [rsp+68h+var_18], xmm3
0x180016020  mov     rdx, rax
0x180016023  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_registry_l1_1_0_dll
0x18001602a  call    __delayLoadHelper2
0x18001602f  movdqa  xmm0, [rsp+68h+var_48]
0x180016035  movdqa  xmm1, [rsp+68h+var_38]
0x18001603b  movdqa  xmm2, [rsp+68h+var_28]
0x180016041  movdqa  xmm3, [rsp+68h+var_18]
0x180016047  mov     rcx, [rsp+68h+arg_0]
0x18001604c  mov     rdx, [rsp+68h+arg_8]
0x180016051  mov     r8, [rsp+68h+arg_10]
0x180016059  mov     r9, [rsp+68h+arg_18]
0x180016061  add     rsp, 68h
0x180016065  jmp     short $+2
0x180016067  jmp     rax
```
