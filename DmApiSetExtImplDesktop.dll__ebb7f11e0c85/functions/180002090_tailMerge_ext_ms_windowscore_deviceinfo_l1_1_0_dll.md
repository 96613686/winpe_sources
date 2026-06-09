# __tailMerge_ext_ms_windowscore_deviceinfo_l1_1_0_dll

- ea: `0x180002090`
- end: `0x180002109`
- name: `__tailMerge_ext_ms_windowscore_deviceinfo_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000210f`
- `0x180002121`

## callees

- `0x180002090`
- `0x180009a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_windowscore_deviceinfo_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_windowscore_deviceinfo_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002090  mov     [rsp+arg_0], rcx
0x180002095  mov     [rsp+arg_8], rdx
0x18000209a  mov     [rsp+arg_10], r8
0x18000209f  mov     [rsp+arg_18], r9
0x1800020a4  sub     rsp, 68h
0x1800020a8  movdqa  [rsp+68h+var_48], xmm0
0x1800020ae  movdqa  [rsp+68h+var_38], xmm1
0x1800020b4  movdqa  [rsp+68h+var_28], xmm2
0x1800020ba  movdqa  [rsp+68h+var_18], xmm3
0x1800020c0  mov     rdx, rax
0x1800020c3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_windowscore_deviceinfo_l1_1_0_dll
0x1800020ca  call    __delayLoadHelper2
0x1800020cf  movdqa  xmm0, [rsp+68h+var_48]
0x1800020d5  movdqa  xmm1, [rsp+68h+var_38]
0x1800020db  movdqa  xmm2, [rsp+68h+var_28]
0x1800020e1  movdqa  xmm3, [rsp+68h+var_18]
0x1800020e7  mov     rcx, [rsp+68h+arg_0]
0x1800020ec  mov     rdx, [rsp+68h+arg_8]
0x1800020f1  mov     r8, [rsp+68h+arg_10]
0x1800020f9  mov     r9, [rsp+68h+arg_18]
0x180002101  add     rsp, 68h
0x180002105  jmp     short $+2
0x180002107  jmp     rax
```
