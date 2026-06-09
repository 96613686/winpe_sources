# __tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll

- ea: `0x18002b4a7`
- end: `0x18002b520`
- name: `__tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b526`

## callees

- `0x18002b4a7`
- `0x180045730`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18002b4a7  mov     [rsp+arg_0], rcx
0x18002b4ac  mov     [rsp+arg_8], rdx
0x18002b4b1  mov     [rsp+arg_10], r8
0x18002b4b6  mov     [rsp+arg_18], r9
0x18002b4bb  sub     rsp, 68h
0x18002b4bf  movdqa  [rsp+68h+var_48], xmm0
0x18002b4c5  movdqa  [rsp+68h+var_38], xmm1
0x18002b4cb  movdqa  [rsp+68h+var_28], xmm2
0x18002b4d1  movdqa  [rsp+68h+var_18], xmm3
0x18002b4d7  mov     rdx, rax
0x18002b4da  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll
0x18002b4e1  call    __delayLoadHelper2
0x18002b4e6  movdqa  xmm0, [rsp+68h+var_48]
0x18002b4ec  movdqa  xmm1, [rsp+68h+var_38]
0x18002b4f2  movdqa  xmm2, [rsp+68h+var_28]
0x18002b4f8  movdqa  xmm3, [rsp+68h+var_18]
0x18002b4fe  mov     rcx, [rsp+68h+arg_0]
0x18002b503  mov     rdx, [rsp+68h+arg_8]
0x18002b508  mov     r8, [rsp+68h+arg_10]
0x18002b510  mov     r9, [rsp+68h+arg_18]
0x18002b518  add     rsp, 68h
0x18002b51c  jmp     short $+2
0x18002b51e  jmp     rax
```
