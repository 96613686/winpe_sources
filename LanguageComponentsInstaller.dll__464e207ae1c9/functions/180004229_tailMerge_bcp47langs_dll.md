# __tailMerge_bcp47langs_dll

- ea: `0x180004229`
- end: `0x1800042a2`
- name: `__tailMerge_bcp47langs_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800042a8`
- `0x1800042ba`
- `0x1800042cc`
- `0x1800042de`

## callees

- `0x180004229`
- `0x180027c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcp47langs_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcp47langs_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004229  mov     [rsp+arg_0], rcx
0x18000422e  mov     [rsp+arg_8], rdx
0x180004233  mov     [rsp+arg_10], r8
0x180004238  mov     [rsp+arg_18], r9
0x18000423d  sub     rsp, 68h
0x180004241  movdqa  [rsp+68h+var_48], xmm0
0x180004247  movdqa  [rsp+68h+var_38], xmm1
0x18000424d  movdqa  [rsp+68h+var_28], xmm2
0x180004253  movdqa  [rsp+68h+var_18], xmm3
0x180004259  mov     rdx, rax
0x18000425c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcp47langs_dll
0x180004263  call    __delayLoadHelper2
0x180004268  movdqa  xmm0, [rsp+68h+var_48]
0x18000426e  movdqa  xmm1, [rsp+68h+var_38]
0x180004274  movdqa  xmm2, [rsp+68h+var_28]
0x18000427a  movdqa  xmm3, [rsp+68h+var_18]
0x180004280  mov     rcx, [rsp+68h+arg_0]
0x180004285  mov     rdx, [rsp+68h+arg_8]
0x18000428a  mov     r8, [rsp+68h+arg_10]
0x180004292  mov     r9, [rsp+68h+arg_18]
0x18000429a  add     rsp, 68h
0x18000429e  jmp     short $+2
0x1800042a0  jmp     rax
```
