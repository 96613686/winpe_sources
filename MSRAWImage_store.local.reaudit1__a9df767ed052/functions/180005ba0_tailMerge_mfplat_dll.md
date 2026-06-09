# __tailMerge_mfplat_dll

- ea: `0x180005ba0`
- end: `0x180005c19`
- name: `__tailMerge_mfplat_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005c1f`
- `0x180005c31`
- `0x180006351`

## callees

- `0x180005ba0`
- `0x1800a3fe0`

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
0x180005ba0  mov     [rsp+arg_0], rcx
0x180005ba5  mov     [rsp+arg_8], rdx
0x180005baa  mov     [rsp+arg_10], r8
0x180005baf  mov     [rsp+arg_18], r9
0x180005bb4  sub     rsp, 68h
0x180005bb8  movdqa  [rsp+68h+var_48], xmm0
0x180005bbe  movdqa  [rsp+68h+var_38], xmm1
0x180005bc4  movdqa  [rsp+68h+var_28], xmm2
0x180005bca  movdqa  [rsp+68h+var_18], xmm3
0x180005bd0  mov     rdx, rax
0x180005bd3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mfplat_dll
0x180005bda  call    __delayLoadHelper2
0x180005bdf  movdqa  xmm0, [rsp+68h+var_48]
0x180005be5  movdqa  xmm1, [rsp+68h+var_38]
0x180005beb  movdqa  xmm2, [rsp+68h+var_28]
0x180005bf1  movdqa  xmm3, [rsp+68h+var_18]
0x180005bf7  mov     rcx, [rsp+68h+arg_0]
0x180005bfc  mov     rdx, [rsp+68h+arg_8]
0x180005c01  mov     r8, [rsp+68h+arg_10]
0x180005c09  mov     r9, [rsp+68h+arg_18]
0x180005c11  add     rsp, 68h
0x180005c15  jmp     short $+2
0x180005c17  jmp     rax
```
