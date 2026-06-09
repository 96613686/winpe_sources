# __tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll

- ea: `0x1800026e6`
- end: `0x18000275f`
- name: `__tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002765`
- `0x180002777`
- `0x180002789`
- `0x18000279b`

## callees

- `0x1800026e6`
- `0x180034f10`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_wevtapi_eventlog_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_wevtapi_eventlog_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026e6  mov     [rsp+arg_0], rcx
0x1800026eb  mov     [rsp+arg_8], rdx
0x1800026f0  mov     [rsp+arg_10], r8
0x1800026f5  mov     [rsp+arg_18], r9
0x1800026fa  sub     rsp, 68h
0x1800026fe  movdqa  [rsp+68h+var_48], xmm0
0x180002704  movdqa  [rsp+68h+var_38], xmm1
0x18000270a  movdqa  [rsp+68h+var_28], xmm2
0x180002710  movdqa  [rsp+68h+var_18], xmm3
0x180002716  mov     rdx, rax
0x180002719  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_wevtapi_eventlog_l1_1_0_dll
0x180002720  call    __delayLoadHelper2
0x180002725  movdqa  xmm0, [rsp+68h+var_48]
0x18000272b  movdqa  xmm1, [rsp+68h+var_38]
0x180002731  movdqa  xmm2, [rsp+68h+var_28]
0x180002737  movdqa  xmm3, [rsp+68h+var_18]
0x18000273d  mov     rcx, [rsp+68h+arg_0]
0x180002742  mov     rdx, [rsp+68h+arg_8]
0x180002747  mov     r8, [rsp+68h+arg_10]
0x18000274f  mov     r9, [rsp+68h+arg_18]
0x180002757  add     rsp, 68h
0x18000275b  jmp     short $+2
0x18000275d  jmp     rax
```
