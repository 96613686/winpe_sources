# __tailMerge_mlang_dll

- ea: `0x180002e9e`
- end: `0x180002f17`
- name: `__tailMerge_mlang_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f1d`

## callees

- `0x180002e9e`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_mlang_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mlang_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002e9e  mov     [rsp+arg_0], rcx
0x180002ea3  mov     [rsp+arg_8], rdx
0x180002ea8  mov     [rsp+arg_10], r8
0x180002ead  mov     [rsp+arg_18], r9
0x180002eb2  sub     rsp, 68h
0x180002eb6  movdqa  [rsp+68h+var_48], xmm0
0x180002ebc  movdqa  [rsp+68h+var_38], xmm1
0x180002ec2  movdqa  [rsp+68h+var_28], xmm2
0x180002ec8  movdqa  [rsp+68h+var_18], xmm3
0x180002ece  mov     rdx, rax
0x180002ed1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mlang_dll
0x180002ed8  call    __delayLoadHelper2
0x180002edd  movdqa  xmm0, [rsp+68h+var_48]
0x180002ee3  movdqa  xmm1, [rsp+68h+var_38]
0x180002ee9  movdqa  xmm2, [rsp+68h+var_28]
0x180002eef  movdqa  xmm3, [rsp+68h+var_18]
0x180002ef5  mov     rcx, [rsp+68h+arg_0]
0x180002efa  mov     rdx, [rsp+68h+arg_8]
0x180002eff  mov     r8, [rsp+68h+arg_10]
0x180002f07  mov     r9, [rsp+68h+arg_18]
0x180002f0f  add     rsp, 68h
0x180002f13  jmp     short $+2
0x180002f15  jmp     rax
```
