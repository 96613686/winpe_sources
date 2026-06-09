# __tailMerge_api_ms_win_core_winrt_l1_1_0_dll

- ea: `0x180002c29`
- end: `0x180002ca2`
- name: `__tailMerge_api_ms_win_core_winrt_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002ca8`

## callees

- `0x180002c29`
- `0x18000a6d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002c29  mov     [rsp+arg_0], rcx
0x180002c2e  mov     [rsp+arg_8], rdx
0x180002c33  mov     [rsp+arg_10], r8
0x180002c38  mov     [rsp+arg_18], r9
0x180002c3d  sub     rsp, 68h
0x180002c41  movdqa  [rsp+68h+var_48], xmm0
0x180002c47  movdqa  [rsp+68h+var_38], xmm1
0x180002c4d  movdqa  [rsp+68h+var_28], xmm2
0x180002c53  movdqa  [rsp+68h+var_18], xmm3
0x180002c59  mov     rdx, rax
0x180002c5c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_l1_1_0_dll
0x180002c63  call    __delayLoadHelper2
0x180002c68  movdqa  xmm0, [rsp+68h+var_48]
0x180002c6e  movdqa  xmm1, [rsp+68h+var_38]
0x180002c74  movdqa  xmm2, [rsp+68h+var_28]
0x180002c7a  movdqa  xmm3, [rsp+68h+var_18]
0x180002c80  mov     rcx, [rsp+68h+arg_0]
0x180002c85  mov     rdx, [rsp+68h+arg_8]
0x180002c8a  mov     r8, [rsp+68h+arg_10]
0x180002c92  mov     r9, [rsp+68h+arg_18]
0x180002c9a  add     rsp, 68h
0x180002c9e  jmp     short $+2
0x180002ca0  jmp     rax
```
