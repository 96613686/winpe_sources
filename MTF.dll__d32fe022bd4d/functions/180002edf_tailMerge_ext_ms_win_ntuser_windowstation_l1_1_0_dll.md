# __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll

- ea: `0x180002edf`
- end: `0x180002f58`
- name: `__tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f5e`
- `0x180002f70`

## callees

- `0x180002edf`
- `0x18002bb20`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002edf  mov     [rsp+arg_0], rcx
0x180002ee4  mov     [rsp+arg_8], rdx
0x180002ee9  mov     [rsp+arg_10], r8
0x180002eee  mov     [rsp+arg_18], r9
0x180002ef3  sub     rsp, 68h
0x180002ef7  movdqa  [rsp+68h+var_48], xmm0
0x180002efd  movdqa  [rsp+68h+var_38], xmm1
0x180002f03  movdqa  [rsp+68h+var_28], xmm2
0x180002f09  movdqa  [rsp+68h+var_18], xmm3
0x180002f0f  mov     rdx, rax
0x180002f12  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowstation_l1_1_0_dll
0x180002f19  call    __delayLoadHelper2
0x180002f1e  movdqa  xmm0, [rsp+68h+var_48]
0x180002f24  movdqa  xmm1, [rsp+68h+var_38]
0x180002f2a  movdqa  xmm2, [rsp+68h+var_28]
0x180002f30  movdqa  xmm3, [rsp+68h+var_18]
0x180002f36  mov     rcx, [rsp+68h+arg_0]
0x180002f3b  mov     rdx, [rsp+68h+arg_8]
0x180002f40  mov     r8, [rsp+68h+arg_10]
0x180002f48  mov     r9, [rsp+68h+arg_18]
0x180002f50  add     rsp, 68h
0x180002f54  jmp     short $+2
0x180002f56  jmp     rax
```
