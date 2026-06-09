# __tailMerge_cryptsp_dll

- ea: `0x1800158a6`
- end: `0x18001591f`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015925`
- `0x180015937`
- `0x180015949`
- `0x18001595b`
- `0x18001596d`
- `0x18001597f`
- `0x180015991`
- `0x1800159a3`

## callees

- `0x180012ae0`
- `0x1800158a6`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800158a6  mov     [rsp+arg_0], rcx
0x1800158ab  mov     [rsp+arg_8], rdx
0x1800158b0  mov     [rsp+arg_10], r8
0x1800158b5  mov     [rsp+arg_18], r9
0x1800158ba  sub     rsp, 68h
0x1800158be  movdqa  [rsp+68h+var_48], xmm0
0x1800158c4  movdqa  [rsp+68h+var_38], xmm1
0x1800158ca  movdqa  [rsp+68h+var_28], xmm2
0x1800158d0  movdqa  [rsp+68h+var_18], xmm3
0x1800158d6  mov     rdx, rax
0x1800158d9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x1800158e0  call    __delayLoadHelper2
0x1800158e5  movdqa  xmm0, [rsp+68h+var_48]
0x1800158eb  movdqa  xmm1, [rsp+68h+var_38]
0x1800158f1  movdqa  xmm2, [rsp+68h+var_28]
0x1800158f7  movdqa  xmm3, [rsp+68h+var_18]
0x1800158fd  mov     rcx, [rsp+68h+arg_0]
0x180015902  mov     rdx, [rsp+68h+arg_8]
0x180015907  mov     r8, [rsp+68h+arg_10]
0x18001590f  mov     r9, [rsp+68h+arg_18]
0x180015917  add     rsp, 68h
0x18001591b  jmp     short $+2
0x18001591d  jmp     rax
```
