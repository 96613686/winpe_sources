# __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll

- ea: `0x180002ccc`
- end: `0x180002d45`
- name: `__tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d4b`

## callees

- `0x180002ccc`
- `0x18001ca20`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002ccc  mov     [rsp+arg_0], rcx
0x180002cd1  mov     [rsp+arg_8], rdx
0x180002cd6  mov     [rsp+arg_10], r8
0x180002cdb  mov     [rsp+arg_18], r9
0x180002ce0  sub     rsp, 68h
0x180002ce4  movdqa  [rsp+68h+var_48], xmm0
0x180002cea  movdqa  [rsp+68h+var_38], xmm1
0x180002cf0  movdqa  [rsp+68h+var_28], xmm2
0x180002cf6  movdqa  [rsp+68h+var_18], xmm3
0x180002cfc  mov     rdx, rax
0x180002cff  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_usertoken_l1_1_0_dll
0x180002d06  call    __delayLoadHelper2
0x180002d0b  movdqa  xmm0, [rsp+68h+var_48]
0x180002d11  movdqa  xmm1, [rsp+68h+var_38]
0x180002d17  movdqa  xmm2, [rsp+68h+var_28]
0x180002d1d  movdqa  xmm3, [rsp+68h+var_18]
0x180002d23  mov     rcx, [rsp+68h+arg_0]
0x180002d28  mov     rdx, [rsp+68h+arg_8]
0x180002d2d  mov     r8, [rsp+68h+arg_10]
0x180002d35  mov     r9, [rsp+68h+arg_18]
0x180002d3d  add     rsp, 68h
0x180002d41  jmp     short $+2
0x180002d43  jmp     rax
```
