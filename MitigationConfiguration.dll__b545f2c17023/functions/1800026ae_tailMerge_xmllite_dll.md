# __tailMerge_xmllite_dll

- ea: `0x1800026ae`
- end: `0x180002727`
- name: `__tailMerge_xmllite_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000272d`
- `0x18000273f`

## callees

- `0x1800026ae`
- `0x180013920`

## pseudocode

```c
__int64 __fastcall _tailMerge_xmllite_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_xmllite_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026ae  mov     [rsp+arg_0], rcx
0x1800026b3  mov     [rsp+arg_8], rdx
0x1800026b8  mov     [rsp+arg_10], r8
0x1800026bd  mov     [rsp+arg_18], r9
0x1800026c2  sub     rsp, 68h
0x1800026c6  movdqa  [rsp+68h+var_48], xmm0
0x1800026cc  movdqa  [rsp+68h+var_38], xmm1
0x1800026d2  movdqa  [rsp+68h+var_28], xmm2
0x1800026d8  movdqa  [rsp+68h+var_18], xmm3
0x1800026de  mov     rdx, rax
0x1800026e1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_xmllite_dll
0x1800026e8  call    __delayLoadHelper2
0x1800026ed  movdqa  xmm0, [rsp+68h+var_48]
0x1800026f3  movdqa  xmm1, [rsp+68h+var_38]
0x1800026f9  movdqa  xmm2, [rsp+68h+var_28]
0x1800026ff  movdqa  xmm3, [rsp+68h+var_18]
0x180002705  mov     rcx, [rsp+68h+arg_0]
0x18000270a  mov     rdx, [rsp+68h+arg_8]
0x18000270f  mov     r8, [rsp+68h+arg_10]
0x180002717  mov     r9, [rsp+68h+arg_18]
0x18000271f  add     rsp, 68h
0x180002723  jmp     short $+2
0x180002725  jmp     rax
```
