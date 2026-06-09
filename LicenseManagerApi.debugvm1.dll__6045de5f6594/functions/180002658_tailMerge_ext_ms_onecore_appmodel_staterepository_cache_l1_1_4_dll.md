# __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll

- ea: `0x180002658`
- end: `0x1800026d1`
- name: `__tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800026d7`

## callees

- `0x180002658`
- `0x180011cc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002658  mov     [rsp+arg_0], rcx
0x18000265d  mov     [rsp+arg_8], rdx
0x180002662  mov     [rsp+arg_10], r8
0x180002667  mov     [rsp+arg_18], r9
0x18000266c  sub     rsp, 68h
0x180002670  movdqa  [rsp+68h+var_48], xmm0
0x180002676  movdqa  [rsp+68h+var_38], xmm1
0x18000267c  movdqa  [rsp+68h+var_28], xmm2
0x180002682  movdqa  [rsp+68h+var_18], xmm3
0x180002688  mov     rdx, rax
0x18000268b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll
0x180002692  call    __delayLoadHelper2
0x180002697  movdqa  xmm0, [rsp+68h+var_48]
0x18000269d  movdqa  xmm1, [rsp+68h+var_38]
0x1800026a3  movdqa  xmm2, [rsp+68h+var_28]
0x1800026a9  movdqa  xmm3, [rsp+68h+var_18]
0x1800026af  mov     rcx, [rsp+68h+arg_0]
0x1800026b4  mov     rdx, [rsp+68h+arg_8]
0x1800026b9  mov     r8, [rsp+68h+arg_10]
0x1800026c1  mov     r9, [rsp+68h+arg_18]
0x1800026c9  add     rsp, 68h
0x1800026cd  jmp     short $+2
0x1800026cf  jmp     rax
```
