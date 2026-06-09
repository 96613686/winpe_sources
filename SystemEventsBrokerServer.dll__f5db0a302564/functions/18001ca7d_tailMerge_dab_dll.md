# __tailMerge_dab_dll

- ea: `0x18001ca7d`
- end: `0x18001caf6`
- name: `__tailMerge_dab_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001cafc`
- `0x18001cb0e`
- `0x18001cb20`
- `0x18001cb32`
- `0x18001cb44`

## callees

- `0x18001ca7d`
- `0x180021e90`

## pseudocode

```c
__int64 __fastcall _tailMerge_dab_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dab_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001ca7d  mov     [rsp+arg_0], rcx
0x18001ca82  mov     [rsp+arg_8], rdx
0x18001ca87  mov     [rsp+arg_10], r8
0x18001ca8c  mov     [rsp+arg_18], r9
0x18001ca91  sub     rsp, 68h
0x18001ca95  movdqa  [rsp+68h+var_48], xmm0
0x18001ca9b  movdqa  [rsp+68h+var_38], xmm1
0x18001caa1  movdqa  [rsp+68h+var_28], xmm2
0x18001caa7  movdqa  [rsp+68h+var_18], xmm3
0x18001caad  mov     rdx, rax
0x18001cab0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dab_dll
0x18001cab7  call    __delayLoadHelper2
0x18001cabc  movdqa  xmm0, [rsp+68h+var_48]
0x18001cac2  movdqa  xmm1, [rsp+68h+var_38]
0x18001cac8  movdqa  xmm2, [rsp+68h+var_28]
0x18001cace  movdqa  xmm3, [rsp+68h+var_18]
0x18001cad4  mov     rcx, [rsp+68h+arg_0]
0x18001cad9  mov     rdx, [rsp+68h+arg_8]
0x18001cade  mov     r8, [rsp+68h+arg_10]
0x18001cae6  mov     r9, [rsp+68h+arg_18]
0x18001caee  add     rsp, 68h
0x18001caf2  jmp     short $+2
0x18001caf4  jmp     rax
```
