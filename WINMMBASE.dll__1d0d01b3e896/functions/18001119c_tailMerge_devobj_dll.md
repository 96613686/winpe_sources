# __tailMerge_devobj_dll

- ea: `0x18001119c`
- end: `0x180011215`
- name: `__tailMerge_devobj_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001121b`
- `0x180011300`
- `0x180011312`

## callees

- `0x18000f240`
- `0x18001119c`

## pseudocode

```c
__int64 __fastcall _tailMerge_devobj_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_devobj_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001119c  mov     [rsp+arg_0], rcx
0x1800111a1  mov     [rsp+arg_8], rdx
0x1800111a6  mov     [rsp+arg_10], r8
0x1800111ab  mov     [rsp+arg_18], r9
0x1800111b0  sub     rsp, 68h
0x1800111b4  movdqa  [rsp+68h+var_48], xmm0
0x1800111ba  movdqa  [rsp+68h+var_38], xmm1
0x1800111c0  movdqa  [rsp+68h+var_28], xmm2
0x1800111c6  movdqa  [rsp+68h+var_18], xmm3
0x1800111cc  mov     rdx, rax
0x1800111cf  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_devobj_dll
0x1800111d6  call    __delayLoadHelper2
0x1800111db  movdqa  xmm0, [rsp+68h+var_48]
0x1800111e1  movdqa  xmm1, [rsp+68h+var_38]
0x1800111e7  movdqa  xmm2, [rsp+68h+var_28]
0x1800111ed  movdqa  xmm3, [rsp+68h+var_18]
0x1800111f3  mov     rcx, [rsp+68h+arg_0]
0x1800111f8  mov     rdx, [rsp+68h+arg_8]
0x1800111fd  mov     r8, [rsp+68h+arg_10]
0x180011205  mov     r9, [rsp+68h+arg_18]
0x18001120d  add     rsp, 68h
0x180011211  jmp     short $+2
0x180011213  jmp     rax
```
