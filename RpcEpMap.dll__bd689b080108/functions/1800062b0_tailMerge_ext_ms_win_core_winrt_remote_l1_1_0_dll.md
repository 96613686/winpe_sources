# __tailMerge_ext_ms_win_core_winrt_remote_l1_1_0_dll

- ea: `0x1800062b0`
- end: `0x180006329`
- name: `__tailMerge_ext_ms_win_core_winrt_remote_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000632f`
- `0x180006341`

## callees

- `0x1800062b0`
- `0x18000a860`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_winrt_remote_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_winrt_remote_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800062b0  mov     [rsp+arg_0], rcx
0x1800062b5  mov     [rsp+arg_8], rdx
0x1800062ba  mov     [rsp+arg_10], r8
0x1800062bf  mov     [rsp+arg_18], r9
0x1800062c4  sub     rsp, 68h
0x1800062c8  movdqa  [rsp+68h+var_48], xmm0
0x1800062ce  movdqa  [rsp+68h+var_38], xmm1
0x1800062d4  movdqa  [rsp+68h+var_28], xmm2
0x1800062da  movdqa  [rsp+68h+var_18], xmm3
0x1800062e0  mov     rdx, rax
0x1800062e3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_winrt_remote_l1_1_0_dll
0x1800062ea  call    __delayLoadHelper2
0x1800062ef  movdqa  xmm0, [rsp+68h+var_48]
0x1800062f5  movdqa  xmm1, [rsp+68h+var_38]
0x1800062fb  movdqa  xmm2, [rsp+68h+var_28]
0x180006301  movdqa  xmm3, [rsp+68h+var_18]
0x180006307  mov     rcx, [rsp+68h+arg_0]
0x18000630c  mov     rdx, [rsp+68h+arg_8]
0x180006311  mov     r8, [rsp+68h+arg_10]
0x180006319  mov     r9, [rsp+68h+arg_18]
0x180006321  add     rsp, 68h
0x180006325  jmp     short $+2
0x180006327  jmp     rax
```
