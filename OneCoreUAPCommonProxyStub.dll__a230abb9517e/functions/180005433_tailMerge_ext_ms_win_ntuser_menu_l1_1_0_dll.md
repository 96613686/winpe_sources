# __tailMerge_ext_ms_win_ntuser_menu_l1_1_0_dll

- ea: `0x180005433`
- end: `0x1800054ac`
- name: `__tailMerge_ext_ms_win_ntuser_menu_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800054b2`
- `0x1800054c4`
- `0x18000552c`

## callees

- `0x180002420`
- `0x180005433`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_menu_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_menu_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005433  mov     [rsp+arg_0], rcx
0x180005438  mov     [rsp+arg_8], rdx
0x18000543d  mov     [rsp+arg_10], r8
0x180005442  mov     [rsp+arg_18], r9
0x180005447  sub     rsp, 68h
0x18000544b  movdqa  [rsp+68h+var_48], xmm0
0x180005451  movdqa  [rsp+68h+var_38], xmm1
0x180005457  movdqa  [rsp+68h+var_28], xmm2
0x18000545d  movdqa  [rsp+68h+var_18], xmm3
0x180005463  mov     rdx, rax
0x180005466  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_menu_l1_1_0_dll
0x18000546d  call    __delayLoadHelper2
0x180005472  movdqa  xmm0, [rsp+68h+var_48]
0x180005478  movdqa  xmm1, [rsp+68h+var_38]
0x18000547e  movdqa  xmm2, [rsp+68h+var_28]
0x180005484  movdqa  xmm3, [rsp+68h+var_18]
0x18000548a  mov     rcx, [rsp+68h+arg_0]
0x18000548f  mov     rdx, [rsp+68h+arg_8]
0x180005494  mov     r8, [rsp+68h+arg_10]
0x18000549c  mov     r9, [rsp+68h+arg_18]
0x1800054a4  add     rsp, 68h
0x1800054a8  jmp     short $+2
0x1800054aa  jmp     rax
```
