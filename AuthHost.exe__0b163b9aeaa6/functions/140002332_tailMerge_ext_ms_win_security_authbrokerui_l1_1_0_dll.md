# __tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll

- ea: `0x140002332`
- end: `0x1400023ab`
- name: `__tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400023b1`
- `0x1400023c3`
- `0x1400023d5`

## callees

- `0x140002332`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_authbrokerui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002332  mov     [rsp+arg_0], rcx
0x140002337  mov     [rsp+arg_8], rdx
0x14000233c  mov     [rsp+arg_10], r8
0x140002341  mov     [rsp+arg_18], r9
0x140002346  sub     rsp, 68h
0x14000234a  movdqa  [rsp+68h+var_48], xmm0
0x140002350  movdqa  [rsp+68h+var_38], xmm1
0x140002356  movdqa  [rsp+68h+var_28], xmm2
0x14000235c  movdqa  [rsp+68h+var_18], xmm3
0x140002362  mov     rdx, rax
0x140002365  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_security_authbrokerui_l1_1_0_dll
0x14000236c  call    __delayLoadHelper2
0x140002371  movdqa  xmm0, [rsp+68h+var_48]
0x140002377  movdqa  xmm1, [rsp+68h+var_38]
0x14000237d  movdqa  xmm2, [rsp+68h+var_28]
0x140002383  movdqa  xmm3, [rsp+68h+var_18]
0x140002389  mov     rcx, [rsp+68h+arg_0]
0x14000238e  mov     rdx, [rsp+68h+arg_8]
0x140002393  mov     r8, [rsp+68h+arg_10]
0x14000239b  mov     r9, [rsp+68h+arg_18]
0x1400023a3  add     rsp, 68h
0x1400023a7  jmp     short $+2
0x1400023a9  jmp     rax
```
