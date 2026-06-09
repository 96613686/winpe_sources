# __tailMerge_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll

- ea: `0x18000966c`
- end: `0x1800096e5`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800096eb`

## callees

- `0x1800081c0`
- `0x18000966c`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000966c  mov     [rsp+arg_0], rcx
0x180009671  mov     [rsp+arg_8], rdx
0x180009676  mov     [rsp+arg_10], r8
0x18000967b  mov     [rsp+arg_18], r9
0x180009680  sub     rsp, 68h
0x180009684  movdqa  [rsp+68h+var_48], xmm0
0x18000968a  movdqa  [rsp+68h+var_38], xmm1
0x180009690  movdqa  [rsp+68h+var_28], xmm2
0x180009696  movdqa  [rsp+68h+var_18], xmm3
0x18000969c  mov     rdx, rax
0x18000969f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll
0x1800096a6  call    __delayLoadHelper2
0x1800096ab  movdqa  xmm0, [rsp+68h+var_48]
0x1800096b1  movdqa  xmm1, [rsp+68h+var_38]
0x1800096b7  movdqa  xmm2, [rsp+68h+var_28]
0x1800096bd  movdqa  xmm3, [rsp+68h+var_18]
0x1800096c3  mov     rcx, [rsp+68h+arg_0]
0x1800096c8  mov     rdx, [rsp+68h+arg_8]
0x1800096cd  mov     r8, [rsp+68h+arg_10]
0x1800096d5  mov     r9, [rsp+68h+arg_18]
0x1800096dd  add     rsp, 68h
0x1800096e1  jmp     short $+2
0x1800096e3  jmp     rax
```
