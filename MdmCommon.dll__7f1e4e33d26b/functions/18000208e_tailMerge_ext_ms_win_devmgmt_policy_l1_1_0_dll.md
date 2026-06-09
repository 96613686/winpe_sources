# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x18000208e`
- end: `0x180002107`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000210d`
- `0x18000211f`

## callees

- `0x18000208e`
- `0x18001d370`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000208e  mov     [rsp+arg_0], rcx
0x180002093  mov     [rsp+arg_8], rdx
0x180002098  mov     [rsp+arg_10], r8
0x18000209d  mov     [rsp+arg_18], r9
0x1800020a2  sub     rsp, 68h
0x1800020a6  movdqa  [rsp+68h+var_48], xmm0
0x1800020ac  movdqa  [rsp+68h+var_38], xmm1
0x1800020b2  movdqa  [rsp+68h+var_28], xmm2
0x1800020b8  movdqa  [rsp+68h+var_18], xmm3
0x1800020be  mov     rdx, rax
0x1800020c1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x1800020c8  call    __delayLoadHelper2
0x1800020cd  movdqa  xmm0, [rsp+68h+var_48]
0x1800020d3  movdqa  xmm1, [rsp+68h+var_38]
0x1800020d9  movdqa  xmm2, [rsp+68h+var_28]
0x1800020df  movdqa  xmm3, [rsp+68h+var_18]
0x1800020e5  mov     rcx, [rsp+68h+arg_0]
0x1800020ea  mov     rdx, [rsp+68h+arg_8]
0x1800020ef  mov     r8, [rsp+68h+arg_10]
0x1800020f7  mov     r9, [rsp+68h+arg_18]
0x1800020ff  add     rsp, 68h
0x180002103  jmp     short $+2
0x180002105  jmp     rax
```
