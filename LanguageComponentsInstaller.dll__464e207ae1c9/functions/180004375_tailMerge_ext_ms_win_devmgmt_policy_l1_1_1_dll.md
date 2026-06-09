# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_1_dll

- ea: `0x180004375`
- end: `0x1800043ee`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800043f4`
- `0x180004406`

## callees

- `0x180004375`
- `0x180027c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004375  mov     [rsp+arg_0], rcx
0x18000437a  mov     [rsp+arg_8], rdx
0x18000437f  mov     [rsp+arg_10], r8
0x180004384  mov     [rsp+arg_18], r9
0x180004389  sub     rsp, 68h
0x18000438d  movdqa  [rsp+68h+var_48], xmm0
0x180004393  movdqa  [rsp+68h+var_38], xmm1
0x180004399  movdqa  [rsp+68h+var_28], xmm2
0x18000439f  movdqa  [rsp+68h+var_18], xmm3
0x1800043a5  mov     rdx, rax
0x1800043a8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_1_dll
0x1800043af  call    __delayLoadHelper2
0x1800043b4  movdqa  xmm0, [rsp+68h+var_48]
0x1800043ba  movdqa  xmm1, [rsp+68h+var_38]
0x1800043c0  movdqa  xmm2, [rsp+68h+var_28]
0x1800043c6  movdqa  xmm3, [rsp+68h+var_18]
0x1800043cc  mov     rcx, [rsp+68h+arg_0]
0x1800043d1  mov     rdx, [rsp+68h+arg_8]
0x1800043d6  mov     r8, [rsp+68h+arg_10]
0x1800043de  mov     r9, [rsp+68h+arg_18]
0x1800043e6  add     rsp, 68h
0x1800043ea  jmp     short $+2
0x1800043ec  jmp     rax
```
