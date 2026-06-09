# __tailMerge_ext_ms_win_kernel32_package_l1_1_0_dll

- ea: `0x1800023f6`
- end: `0x18000246f`
- name: `__tailMerge_ext_ms_win_kernel32_package_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002480`

## callees

- `0x1800023f6`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_kernel32_package_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_kernel32_package_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800023f6  mov     [rsp+arg_0], rcx
0x1800023fb  mov     [rsp+arg_8], rdx
0x180002400  mov     [rsp+arg_10], r8
0x180002405  mov     [rsp+arg_18], r9
0x18000240a  sub     rsp, 68h
0x18000240e  movdqa  [rsp+68h+var_48], xmm0
0x180002414  movdqa  [rsp+68h+var_38], xmm1
0x18000241a  movdqa  [rsp+68h+var_28], xmm2
0x180002420  movdqa  [rsp+68h+var_18], xmm3
0x180002426  mov     rdx, rax
0x180002429  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_kernel32_package_l1_1_0_dll
0x180002430  call    __delayLoadHelper2
0x180002435  movdqa  xmm0, [rsp+68h+var_48]
0x18000243b  movdqa  xmm1, [rsp+68h+var_38]
0x180002441  movdqa  xmm2, [rsp+68h+var_28]
0x180002447  movdqa  xmm3, [rsp+68h+var_18]
0x18000244d  mov     rcx, [rsp+68h+arg_0]
0x180002452  mov     rdx, [rsp+68h+arg_8]
0x180002457  mov     r8, [rsp+68h+arg_10]
0x18000245f  mov     r9, [rsp+68h+arg_18]
0x180002467  add     rsp, 68h
0x18000246b  jmp     short $+2
0x18000246d  jmp     rax
```
