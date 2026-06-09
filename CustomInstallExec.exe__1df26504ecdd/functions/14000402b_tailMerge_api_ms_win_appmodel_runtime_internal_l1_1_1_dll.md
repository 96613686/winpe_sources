# __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll

- ea: `0x14000402b`
- end: `0x1400040a4`
- name: `__tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400040aa`

## callees

- `0x14000402b`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000402b  mov     [rsp+arg_0], rcx
0x140004030  mov     [rsp+arg_8], rdx
0x140004035  mov     [rsp+arg_10], r8
0x14000403a  mov     [rsp+arg_18], r9
0x14000403f  sub     rsp, 68h
0x140004043  movdqa  [rsp+68h+var_48], xmm0
0x140004049  movdqa  [rsp+68h+var_38], xmm1
0x14000404f  movdqa  [rsp+68h+var_28], xmm2
0x140004055  movdqa  [rsp+68h+var_18], xmm3
0x14000405b  mov     rdx, rax
0x14000405e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_1_dll
0x140004065  call    __delayLoadHelper2
0x14000406a  movdqa  xmm0, [rsp+68h+var_48]
0x140004070  movdqa  xmm1, [rsp+68h+var_38]
0x140004076  movdqa  xmm2, [rsp+68h+var_28]
0x14000407c  movdqa  xmm3, [rsp+68h+var_18]
0x140004082  mov     rcx, [rsp+68h+arg_0]
0x140004087  mov     rdx, [rsp+68h+arg_8]
0x14000408c  mov     r8, [rsp+68h+arg_10]
0x140004094  mov     r9, [rsp+68h+arg_18]
0x14000409c  add     rsp, 68h
0x1400040a0  jmp     short $+2
0x1400040a2  jmp     rax
```
