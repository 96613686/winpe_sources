# __tailMerge_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll

- ea: `0x180002926`
- end: `0x18000299f`
- name: `__tailMerge_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800029a5`

## callees

- `0x180002926`
- `0x18000fed0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002926  mov     [rsp+arg_0], rcx
0x18000292b  mov     [rsp+arg_8], rdx
0x180002930  mov     [rsp+arg_10], r8
0x180002935  mov     [rsp+arg_18], r9
0x18000293a  sub     rsp, 68h
0x18000293e  movdqa  [rsp+68h+var_48], xmm0
0x180002944  movdqa  [rsp+68h+var_38], xmm1
0x18000294a  movdqa  [rsp+68h+var_28], xmm2
0x180002950  movdqa  [rsp+68h+var_18], xmm3
0x180002956  mov     rdx, rax
0x180002959  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll
0x180002960  call    __delayLoadHelper2
0x180002965  movdqa  xmm0, [rsp+68h+var_48]
0x18000296b  movdqa  xmm1, [rsp+68h+var_38]
0x180002971  movdqa  xmm2, [rsp+68h+var_28]
0x180002977  movdqa  xmm3, [rsp+68h+var_18]
0x18000297d  mov     rcx, [rsp+68h+arg_0]
0x180002982  mov     rdx, [rsp+68h+arg_8]
0x180002987  mov     r8, [rsp+68h+arg_10]
0x18000298f  mov     r9, [rsp+68h+arg_18]
0x180002997  add     rsp, 68h
0x18000299b  jmp     short $+2
0x18000299d  jmp     rax
```
