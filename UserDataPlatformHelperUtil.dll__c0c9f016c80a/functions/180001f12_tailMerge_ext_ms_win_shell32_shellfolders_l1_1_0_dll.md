# __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll

- ea: `0x180001f12`
- end: `0x180001f8b`
- name: `__tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f91`

## callees

- `0x180001f12`
- `0x18000a0f0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f12  mov     [rsp+arg_0], rcx
0x180001f17  mov     [rsp+arg_8], rdx
0x180001f1c  mov     [rsp+arg_10], r8
0x180001f21  mov     [rsp+arg_18], r9
0x180001f26  sub     rsp, 68h
0x180001f2a  movdqa  [rsp+68h+var_48], xmm0
0x180001f30  movdqa  [rsp+68h+var_38], xmm1
0x180001f36  movdqa  [rsp+68h+var_28], xmm2
0x180001f3c  movdqa  [rsp+68h+var_18], xmm3
0x180001f42  mov     rdx, rax
0x180001f45  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll
0x180001f4c  call    __delayLoadHelper2
0x180001f51  movdqa  xmm0, [rsp+68h+var_48]
0x180001f57  movdqa  xmm1, [rsp+68h+var_38]
0x180001f5d  movdqa  xmm2, [rsp+68h+var_28]
0x180001f63  movdqa  xmm3, [rsp+68h+var_18]
0x180001f69  mov     rcx, [rsp+68h+arg_0]
0x180001f6e  mov     rdx, [rsp+68h+arg_8]
0x180001f73  mov     r8, [rsp+68h+arg_10]
0x180001f7b  mov     r9, [rsp+68h+arg_18]
0x180001f83  add     rsp, 68h
0x180001f87  jmp     short $+2
0x180001f89  jmp     rax
```
