# __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll

- ea: `0x180002561`
- end: `0x1800025da`
- name: `__tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025e0`
- `0x1800025f2`
- `0x180002604`
- `0x180002616`
- `0x180002628`
- `0x18000263a`
- `0x18000264c`
- `0x1800026e9`
- `0x1800026fb`
- `0x18000270d`

## callees

- `0x180002561`
- `0x180011cc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002561  mov     [rsp+arg_0], rcx
0x180002566  mov     [rsp+arg_8], rdx
0x18000256b  mov     [rsp+arg_10], r8
0x180002570  mov     [rsp+arg_18], r9
0x180002575  sub     rsp, 68h
0x180002579  movdqa  [rsp+68h+var_48], xmm0
0x18000257f  movdqa  [rsp+68h+var_38], xmm1
0x180002585  movdqa  [rsp+68h+var_28], xmm2
0x18000258b  movdqa  [rsp+68h+var_18], xmm3
0x180002591  mov     rdx, rax
0x180002594  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
0x18000259b  call    __delayLoadHelper2
0x1800025a0  movdqa  xmm0, [rsp+68h+var_48]
0x1800025a6  movdqa  xmm1, [rsp+68h+var_38]
0x1800025ac  movdqa  xmm2, [rsp+68h+var_28]
0x1800025b2  movdqa  xmm3, [rsp+68h+var_18]
0x1800025b8  mov     rcx, [rsp+68h+arg_0]
0x1800025bd  mov     rdx, [rsp+68h+arg_8]
0x1800025c2  mov     r8, [rsp+68h+arg_10]
0x1800025ca  mov     r9, [rsp+68h+arg_18]
0x1800025d2  add     rsp, 68h
0x1800025d6  jmp     short $+2
0x1800025d8  jmp     rax
```
