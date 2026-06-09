# __tailMerge_ext_ms_win_com_psmregister_l1_1_0_dll

- ea: `0x180014488`
- end: `0x180014501`
- name: `__tailMerge_ext_ms_win_com_psmregister_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014507`

## callees

- `0x18000f260`
- `0x180014488`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_com_psmregister_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_com_psmregister_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180014488  mov     [rsp+arg_0], rcx
0x18001448d  mov     [rsp+arg_8], rdx
0x180014492  mov     [rsp+arg_10], r8
0x180014497  mov     [rsp+arg_18], r9
0x18001449c  sub     rsp, 68h
0x1800144a0  movdqa  [rsp+68h+var_48], xmm0
0x1800144a6  movdqa  [rsp+68h+var_38], xmm1
0x1800144ac  movdqa  [rsp+68h+var_28], xmm2
0x1800144b2  movdqa  [rsp+68h+var_18], xmm3
0x1800144b8  mov     rdx, rax
0x1800144bb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_com_psmregister_l1_1_0_dll
0x1800144c2  call    __delayLoadHelper2
0x1800144c7  movdqa  xmm0, [rsp+68h+var_48]
0x1800144cd  movdqa  xmm1, [rsp+68h+var_38]
0x1800144d3  movdqa  xmm2, [rsp+68h+var_28]
0x1800144d9  movdqa  xmm3, [rsp+68h+var_18]
0x1800144df  mov     rcx, [rsp+68h+arg_0]
0x1800144e4  mov     rdx, [rsp+68h+arg_8]
0x1800144e9  mov     r8, [rsp+68h+arg_10]
0x1800144f1  mov     r9, [rsp+68h+arg_18]
0x1800144f9  add     rsp, 68h
0x1800144fd  jmp     short $+2
0x1800144ff  jmp     rax
```
