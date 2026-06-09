# __tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll

- ea: `0x1800201ba`
- end: `0x180020233`
- name: `__tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020239`
- `0x18002024b`
- `0x18002025d`
- `0x18002026f`
- `0x180020281`
- `0x180020293`
- `0x1800202a5`
- `0x1800202b7`
- `0x1800202c9`
- `0x1800202db`
- `0x1800202ed`
- `0x1800202ff`
- `0x180020311`
- `0x180020323`
- `0x180020335`
- `0x180020347`
- `0x180020359`
- `0x18002036b`

## callees

- `0x18000c9b0`
- `0x1800201ba`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_domainjoin_netjoin_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_domainjoin_netjoin_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800201ba  mov     [rsp+arg_0], rcx
0x1800201bf  mov     [rsp+arg_8], rdx
0x1800201c4  mov     [rsp+arg_10], r8
0x1800201c9  mov     [rsp+arg_18], r9
0x1800201ce  sub     rsp, 68h
0x1800201d2  movdqa  [rsp+68h+var_48], xmm0
0x1800201d8  movdqa  [rsp+68h+var_38], xmm1
0x1800201de  movdqa  [rsp+68h+var_28], xmm2
0x1800201e4  movdqa  [rsp+68h+var_18], xmm3
0x1800201ea  mov     rdx, rax
0x1800201ed  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_domainjoin_netjoin_l1_1_0_dll
0x1800201f4  call    __delayLoadHelper2
0x1800201f9  movdqa  xmm0, [rsp+68h+var_48]
0x1800201ff  movdqa  xmm1, [rsp+68h+var_38]
0x180020205  movdqa  xmm2, [rsp+68h+var_28]
0x18002020b  movdqa  xmm3, [rsp+68h+var_18]
0x180020211  mov     rcx, [rsp+68h+arg_0]
0x180020216  mov     rdx, [rsp+68h+arg_8]
0x18002021b  mov     r8, [rsp+68h+arg_10]
0x180020223  mov     r9, [rsp+68h+arg_18]
0x18002022b  add     rsp, 68h
0x18002022f  jmp     short $+2
0x180020231  jmp     rax
```
