# __tailMerge_oleaut32_dll

- ea: `0x18000f180`
- end: `0x18000f1f9`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f1ff`
- `0x18000f211`
- `0x18000f223`
- `0x18000f3c9`
- `0x180010220`
- `0x180010232`
- `0x180010244`
- `0x180010256`
- `0x180010268`
- `0x18001027a`
- `0x180010290`
- `0x1800102a2`
- `0x1800102b4`

## callees

- `0x18000a5e0`
- `0x18000f180`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f180  mov     [rsp+arg_0], rcx
0x18000f185  mov     [rsp+arg_8], rdx
0x18000f18a  mov     [rsp+arg_10], r8
0x18000f18f  mov     [rsp+arg_18], r9
0x18000f194  sub     rsp, 68h
0x18000f198  movdqa  [rsp+68h+var_48], xmm0
0x18000f19e  movdqa  [rsp+68h+var_38], xmm1
0x18000f1a4  movdqa  [rsp+68h+var_28], xmm2
0x18000f1aa  movdqa  [rsp+68h+var_18], xmm3
0x18000f1b0  mov     rdx, rax
0x18000f1b3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000f1ba  call    __delayLoadHelper2
0x18000f1bf  movdqa  xmm0, [rsp+68h+var_48]
0x18000f1c5  movdqa  xmm1, [rsp+68h+var_38]
0x18000f1cb  movdqa  xmm2, [rsp+68h+var_28]
0x18000f1d1  movdqa  xmm3, [rsp+68h+var_18]
0x18000f1d7  mov     rcx, [rsp+68h+arg_0]
0x18000f1dc  mov     rdx, [rsp+68h+arg_8]
0x18000f1e1  mov     r8, [rsp+68h+arg_10]
0x18000f1e9  mov     r9, [rsp+68h+arg_18]
0x18000f1f1  add     rsp, 68h
0x18000f1f5  jmp     short $+2
0x18000f1f7  jmp     rax
```
