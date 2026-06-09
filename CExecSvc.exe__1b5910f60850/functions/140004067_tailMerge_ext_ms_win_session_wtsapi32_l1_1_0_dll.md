# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x140004067`
- end: `0x1400040e0`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400040e6`
- `0x1400040f8`
- `0x140004160`

## callees

- `0x140004067`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004067  mov     [rsp+arg_0], rcx
0x14000406c  mov     [rsp+arg_8], rdx
0x140004071  mov     [rsp+arg_10], r8
0x140004076  mov     [rsp+arg_18], r9
0x14000407b  sub     rsp, 68h
0x14000407f  movdqa  [rsp+68h+var_48], xmm0
0x140004085  movdqa  [rsp+68h+var_38], xmm1
0x14000408b  movdqa  [rsp+68h+var_28], xmm2
0x140004091  movdqa  [rsp+68h+var_18], xmm3
0x140004097  mov     rdx, rax
0x14000409a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x1400040a1  call    __delayLoadHelper2
0x1400040a6  movdqa  xmm0, [rsp+68h+var_48]
0x1400040ac  movdqa  xmm1, [rsp+68h+var_38]
0x1400040b2  movdqa  xmm2, [rsp+68h+var_28]
0x1400040b8  movdqa  xmm3, [rsp+68h+var_18]
0x1400040be  mov     rcx, [rsp+68h+arg_0]
0x1400040c3  mov     rdx, [rsp+68h+arg_8]
0x1400040c8  mov     r8, [rsp+68h+arg_10]
0x1400040d0  mov     r9, [rsp+68h+arg_18]
0x1400040d8  add     rsp, 68h
0x1400040dc  jmp     short $+2
0x1400040de  jmp     rax
```
