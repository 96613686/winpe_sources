# __tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll

- ea: `0x1800057ec`
- end: `0x180005865`
- name: `__tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000586b`

## callees

- `0x180002420`
- `0x1800057ec`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_gdi_object_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_gdi_object_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800057ec  mov     [rsp+arg_0], rcx
0x1800057f1  mov     [rsp+arg_8], rdx
0x1800057f6  mov     [rsp+arg_10], r8
0x1800057fb  mov     [rsp+arg_18], r9
0x180005800  sub     rsp, 68h
0x180005804  movdqa  [rsp+68h+var_48], xmm0
0x18000580a  movdqa  [rsp+68h+var_38], xmm1
0x180005810  movdqa  [rsp+68h+var_28], xmm2
0x180005816  movdqa  [rsp+68h+var_18], xmm3
0x18000581c  mov     rdx, rax
0x18000581f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_gdi_object_l1_1_0_dll
0x180005826  call    __delayLoadHelper2
0x18000582b  movdqa  xmm0, [rsp+68h+var_48]
0x180005831  movdqa  xmm1, [rsp+68h+var_38]
0x180005837  movdqa  xmm2, [rsp+68h+var_28]
0x18000583d  movdqa  xmm3, [rsp+68h+var_18]
0x180005843  mov     rcx, [rsp+68h+arg_0]
0x180005848  mov     rdx, [rsp+68h+arg_8]
0x18000584d  mov     r8, [rsp+68h+arg_10]
0x180005855  mov     r9, [rsp+68h+arg_18]
0x18000585d  add     rsp, 68h
0x180005861  jmp     short $+2
0x180005863  jmp     rax
```
