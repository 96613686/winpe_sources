# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x14000969a`
- end: `0x140009713`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009719`
- `0x1400097b6`
- `0x1400098de`
- `0x14000997b`
- `0x14000998d`
- `0x14000999f`
- `0x1400099c3`
- `0x1400099d5`
- `0x140009a72`
- `0x140009a84`
- `0x140009aa8`
- `0x140009aba`
- `0x140009acc`
- `0x140009ade`
- `0x140009b02`
- `0x140009b5c`
- `0x140009b6e`

## callees

- `0x140006ad0`
- `0x14000969a`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000969a  mov     [rsp+arg_0], rcx
0x14000969f  mov     [rsp+arg_8], rdx
0x1400096a4  mov     [rsp+arg_10], r8
0x1400096a9  mov     [rsp+arg_18], r9
0x1400096ae  sub     rsp, 68h
0x1400096b2  movdqa  [rsp+68h+var_48], xmm0
0x1400096b8  movdqa  [rsp+68h+var_38], xmm1
0x1400096be  movdqa  [rsp+68h+var_28], xmm2
0x1400096c4  movdqa  [rsp+68h+var_18], xmm3
0x1400096ca  mov     rdx, rax
0x1400096cd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x1400096d4  call    __delayLoadHelper2
0x1400096d9  movdqa  xmm0, [rsp+68h+var_48]
0x1400096df  movdqa  xmm1, [rsp+68h+var_38]
0x1400096e5  movdqa  xmm2, [rsp+68h+var_28]
0x1400096eb  movdqa  xmm3, [rsp+68h+var_18]
0x1400096f1  mov     rcx, [rsp+68h+arg_0]
0x1400096f6  mov     rdx, [rsp+68h+arg_8]
0x1400096fb  mov     r8, [rsp+68h+arg_10]
0x140009703  mov     r9, [rsp+68h+arg_18]
0x14000970b  add     rsp, 68h
0x14000970f  jmp     short $+2
0x140009711  jmp     rax
```
