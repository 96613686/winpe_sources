# __tailMerge_ext_ms_win_ntuser_windowstation_ansi_l1_1_0_dll

- ea: `0x1800094ca`
- end: `0x180009543`
- name: `__tailMerge_ext_ms_win_ntuser_windowstation_ansi_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009549`

## callees

- `0x1800081c0`
- `0x1800094ca`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowstation_ansi_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_ansi_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800094ca  mov     [rsp+arg_0], rcx
0x1800094cf  mov     [rsp+arg_8], rdx
0x1800094d4  mov     [rsp+arg_10], r8
0x1800094d9  mov     [rsp+arg_18], r9
0x1800094de  sub     rsp, 68h
0x1800094e2  movdqa  [rsp+68h+var_48], xmm0
0x1800094e8  movdqa  [rsp+68h+var_38], xmm1
0x1800094ee  movdqa  [rsp+68h+var_28], xmm2
0x1800094f4  movdqa  [rsp+68h+var_18], xmm3
0x1800094fa  mov     rdx, rax
0x1800094fd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_ansi_l1_1_0_dll
0x180009504  call    __delayLoadHelper2
0x180009509  movdqa  xmm0, [rsp+68h+var_48]
0x18000950f  movdqa  xmm1, [rsp+68h+var_38]
0x180009515  movdqa  xmm2, [rsp+68h+var_28]
0x18000951b  movdqa  xmm3, [rsp+68h+var_18]
0x180009521  mov     rcx, [rsp+68h+arg_0]
0x180009526  mov     rdx, [rsp+68h+arg_8]
0x18000952b  mov     r8, [rsp+68h+arg_10]
0x180009533  mov     r9, [rsp+68h+arg_18]
0x18000953b  add     rsp, 68h
0x18000953f  jmp     short $+2
0x180009541  jmp     rax
```
