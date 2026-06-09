# __tailMerge_iertutil_dll

- ea: `0x1800036bc`
- end: `0x180003735`
- name: `__tailMerge_iertutil_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000373b`

## callees

- `0x1800036bc`
- `0x180010a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_iertutil_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_iertutil_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800036bc  mov     [rsp+arg_0], rcx
0x1800036c1  mov     [rsp+arg_8], rdx
0x1800036c6  mov     [rsp+arg_10], r8
0x1800036cb  mov     [rsp+arg_18], r9
0x1800036d0  sub     rsp, 68h
0x1800036d4  movdqa  [rsp+68h+var_48], xmm0
0x1800036da  movdqa  [rsp+68h+var_38], xmm1
0x1800036e0  movdqa  [rsp+68h+var_28], xmm2
0x1800036e6  movdqa  [rsp+68h+var_18], xmm3
0x1800036ec  mov     rdx, rax
0x1800036ef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iertutil_dll
0x1800036f6  call    __delayLoadHelper2
0x1800036fb  movdqa  xmm0, [rsp+68h+var_48]
0x180003701  movdqa  xmm1, [rsp+68h+var_38]
0x180003707  movdqa  xmm2, [rsp+68h+var_28]
0x18000370d  movdqa  xmm3, [rsp+68h+var_18]
0x180003713  mov     rcx, [rsp+68h+arg_0]
0x180003718  mov     rdx, [rsp+68h+arg_8]
0x18000371d  mov     r8, [rsp+68h+arg_10]
0x180003725  mov     r9, [rsp+68h+arg_18]
0x18000372d  add     rsp, 68h
0x180003731  jmp     short $+2
0x180003733  jmp     rax
```
