# __tailMerge_mfplat_dll

- ea: `0x18004dd1a`
- end: `0x18004dd93`
- name: `__tailMerge_mfplat_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004dd99`
- `0x18004ddab`
- `0x180055603`
- `0x180055615`
- `0x180055627`
- `0x180055639`

## callees

- `0x180044730`
- `0x18004dd1a`

## pseudocode

```c
__int64 __fastcall _tailMerge_mfplat_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mfplat_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18004dd1a  mov     [rsp+arg_0], rcx
0x18004dd1f  mov     [rsp+arg_8], rdx
0x18004dd24  mov     [rsp+arg_10], r8
0x18004dd29  mov     [rsp+arg_18], r9
0x18004dd2e  sub     rsp, 68h
0x18004dd32  movdqa  [rsp+68h+var_48], xmm0
0x18004dd38  movdqa  [rsp+68h+var_38], xmm1
0x18004dd3e  movdqa  [rsp+68h+var_28], xmm2
0x18004dd44  movdqa  [rsp+68h+var_18], xmm3
0x18004dd4a  mov     rdx, rax
0x18004dd4d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mfplat_dll
0x18004dd54  call    __delayLoadHelper2
0x18004dd59  movdqa  xmm0, [rsp+68h+var_48]
0x18004dd5f  movdqa  xmm1, [rsp+68h+var_38]
0x18004dd65  movdqa  xmm2, [rsp+68h+var_28]
0x18004dd6b  movdqa  xmm3, [rsp+68h+var_18]
0x18004dd71  mov     rcx, [rsp+68h+arg_0]
0x18004dd76  mov     rdx, [rsp+68h+arg_8]
0x18004dd7b  mov     r8, [rsp+68h+arg_10]
0x18004dd83  mov     r9, [rsp+68h+arg_18]
0x18004dd8b  add     rsp, 68h
0x18004dd8f  jmp     short $+2
0x18004dd91  jmp     rax
```
