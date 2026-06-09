# __tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll

- ea: `0x1400023be`
- end: `0x140002437`
- name: `__tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000243d`

## callees

- `0x1400023be`
- `0x140011350`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win32_subsystem_query_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400023be  mov     [rsp+arg_0], rcx
0x1400023c3  mov     [rsp+arg_8], rdx
0x1400023c8  mov     [rsp+arg_10], r8
0x1400023cd  mov     [rsp+arg_18], r9
0x1400023d2  sub     rsp, 68h
0x1400023d6  movdqa  [rsp+68h+var_48], xmm0
0x1400023dc  movdqa  [rsp+68h+var_38], xmm1
0x1400023e2  movdqa  [rsp+68h+var_28], xmm2
0x1400023e8  movdqa  [rsp+68h+var_18], xmm3
0x1400023ee  mov     rdx, rax
0x1400023f1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win32_subsystem_query_l1_1_0_dll
0x1400023f8  call    __delayLoadHelper2
0x1400023fd  movdqa  xmm0, [rsp+68h+var_48]
0x140002403  movdqa  xmm1, [rsp+68h+var_38]
0x140002409  movdqa  xmm2, [rsp+68h+var_28]
0x14000240f  movdqa  xmm3, [rsp+68h+var_18]
0x140002415  mov     rcx, [rsp+68h+arg_0]
0x14000241a  mov     rdx, [rsp+68h+arg_8]
0x14000241f  mov     r8, [rsp+68h+arg_10]
0x140002427  mov     r9, [rsp+68h+arg_18]
0x14000242f  add     rsp, 68h
0x140002433  jmp     short $+2
0x140002435  jmp     rax
```
