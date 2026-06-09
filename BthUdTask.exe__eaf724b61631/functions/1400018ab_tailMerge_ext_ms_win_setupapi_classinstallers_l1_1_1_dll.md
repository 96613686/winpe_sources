# __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll

- ea: `0x1400018ab`
- end: `0x140001924`
- name: `__tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000192a`
- `0x14000193c`

## callees

- `0x1400018ab`
- `0x140001eb0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_1_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_setupapi_classinstallers_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400018ab  mov     [rsp+arg_0], rcx
0x1400018b0  mov     [rsp+arg_8], rdx
0x1400018b5  mov     [rsp+arg_10], r8
0x1400018ba  mov     [rsp+arg_18], r9
0x1400018bf  sub     rsp, 68h
0x1400018c3  movdqa  [rsp+68h+var_48], xmm0
0x1400018c9  movdqa  [rsp+68h+var_38], xmm1
0x1400018cf  movdqa  [rsp+68h+var_28], xmm2
0x1400018d5  movdqa  [rsp+68h+var_18], xmm3
0x1400018db  mov     rdx, rax
0x1400018de  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_setupapi_classinstallers_l1_1_1_dll
0x1400018e5  call    __delayLoadHelper2
0x1400018ea  movdqa  xmm0, [rsp+68h+var_48]
0x1400018f0  movdqa  xmm1, [rsp+68h+var_38]
0x1400018f6  movdqa  xmm2, [rsp+68h+var_28]
0x1400018fc  movdqa  xmm3, [rsp+68h+var_18]
0x140001902  mov     rcx, [rsp+68h+arg_0]
0x140001907  mov     rdx, [rsp+68h+arg_8]
0x14000190c  mov     r8, [rsp+68h+arg_10]
0x140001914  mov     r9, [rsp+68h+arg_18]
0x14000191c  add     rsp, 68h
0x140001920  jmp     short $+2
0x140001922  jmp     rax
```
