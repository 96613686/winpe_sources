# __tailMerge_ext_ms_win_composition_ghost_l1_1_0_dll

- ea: `0x14000661a`
- end: `0x140006693`
- name: `__tailMerge_ext_ms_win_composition_ghost_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006699`
- `0x1400066ab`
- `0x1400066bd`
- `0x1400066cf`

## callees

- `0x140003b60`
- `0x14000661a`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_composition_ghost_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_composition_ghost_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000661a  mov     [rsp+arg_0], rcx
0x14000661f  mov     [rsp+arg_8], rdx
0x140006624  mov     [rsp+arg_10], r8
0x140006629  mov     [rsp+arg_18], r9
0x14000662e  sub     rsp, 68h
0x140006632  movdqa  [rsp+68h+var_48], xmm0
0x140006638  movdqa  [rsp+68h+var_38], xmm1
0x14000663e  movdqa  [rsp+68h+var_28], xmm2
0x140006644  movdqa  [rsp+68h+var_18], xmm3
0x14000664a  mov     rdx, rax
0x14000664d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_composition_ghost_l1_1_0_dll
0x140006654  call    __delayLoadHelper2
0x140006659  movdqa  xmm0, [rsp+68h+var_48]
0x14000665f  movdqa  xmm1, [rsp+68h+var_38]
0x140006665  movdqa  xmm2, [rsp+68h+var_28]
0x14000666b  movdqa  xmm3, [rsp+68h+var_18]
0x140006671  mov     rcx, [rsp+68h+arg_0]
0x140006676  mov     rdx, [rsp+68h+arg_8]
0x14000667b  mov     r8, [rsp+68h+arg_10]
0x140006683  mov     r9, [rsp+68h+arg_18]
0x14000668b  add     rsp, 68h
0x14000668f  jmp     short $+2
0x140006691  jmp     rax
```
