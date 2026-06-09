# __tailMerge_msi_dll

- ea: `0x1800027b4`
- end: `0x18000282d`
- name: `__tailMerge_msi_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180002833`
- `0x180002845`
- `0x180002857`
- `0x180002869`
- `0x18000287b`
- `0x18000288d`
- `0x18000289f`

## callees

- `0x1800027b4`
- `0x180009440`

## pseudocode

```c
__int64 __fastcall _tailMerge_msi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_msi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027b4  mov     [rsp+arg_0], rcx
0x1800027b9  mov     [rsp+arg_8], rdx
0x1800027be  mov     [rsp+arg_10], r8
0x1800027c3  mov     [rsp+arg_18], r9
0x1800027c8  sub     rsp, 68h
0x1800027cc  movdqa  [rsp+68h+var_48], xmm0
0x1800027d2  movdqa  [rsp+68h+var_38], xmm1
0x1800027d8  movdqa  [rsp+68h+var_28], xmm2
0x1800027de  movdqa  [rsp+68h+var_18], xmm3
0x1800027e4  mov     rdx, rax
0x1800027e7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_msi_dll
0x1800027ee  call    __delayLoadHelper2
0x1800027f3  movdqa  xmm0, [rsp+68h+var_48]
0x1800027f9  movdqa  xmm1, [rsp+68h+var_38]
0x1800027ff  movdqa  xmm2, [rsp+68h+var_28]
0x180002805  movdqa  xmm3, [rsp+68h+var_18]
0x18000280b  mov     rcx, [rsp+68h+arg_0]
0x180002810  mov     rdx, [rsp+68h+arg_8]
0x180002815  mov     r8, [rsp+68h+arg_10]
0x18000281d  mov     r9, [rsp+68h+arg_18]
0x180002825  add     rsp, 68h
0x180002829  jmp     short $+2
0x18000282b  jmp     rax
```
