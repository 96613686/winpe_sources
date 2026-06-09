# __tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll

- ea: `0x180002a27`
- end: `0x180002aa0`
- name: `__tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002aa6`

## callees

- `0x180002a27`
- `0x18000e1a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shell_shellfolders_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a27  mov     [rsp+arg_0], rcx
0x180002a2c  mov     [rsp+arg_8], rdx
0x180002a31  mov     [rsp+arg_10], r8
0x180002a36  mov     [rsp+arg_18], r9
0x180002a3b  sub     rsp, 68h
0x180002a3f  movdqa  [rsp+68h+var_48], xmm0
0x180002a45  movdqa  [rsp+68h+var_38], xmm1
0x180002a4b  movdqa  [rsp+68h+var_28], xmm2
0x180002a51  movdqa  [rsp+68h+var_18], xmm3
0x180002a57  mov     rdx, rax
0x180002a5a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shell_shellfolders_l1_1_0_dll
0x180002a61  call    __delayLoadHelper2
0x180002a66  movdqa  xmm0, [rsp+68h+var_48]
0x180002a6c  movdqa  xmm1, [rsp+68h+var_38]
0x180002a72  movdqa  xmm2, [rsp+68h+var_28]
0x180002a78  movdqa  xmm3, [rsp+68h+var_18]
0x180002a7e  mov     rcx, [rsp+68h+arg_0]
0x180002a83  mov     rdx, [rsp+68h+arg_8]
0x180002a88  mov     r8, [rsp+68h+arg_10]
0x180002a90  mov     r9, [rsp+68h+arg_18]
0x180002a98  add     rsp, 68h
0x180002a9c  jmp     short $+2
0x180002a9e  jmp     rax
```
