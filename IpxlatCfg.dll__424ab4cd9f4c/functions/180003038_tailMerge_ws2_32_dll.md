# __tailMerge_ws2_32_dll

- ea: `0x180003038`
- end: `0x1800030b1`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800030b7`

## callees

- `0x180003038`
- `0x180017cd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003038  mov     [rsp+arg_0], rcx
0x18000303d  mov     [rsp+arg_8], rdx
0x180003042  mov     [rsp+arg_10], r8
0x180003047  mov     [rsp+arg_18], r9
0x18000304c  sub     rsp, 68h
0x180003050  movdqa  [rsp+68h+var_48], xmm0
0x180003056  movdqa  [rsp+68h+var_38], xmm1
0x18000305c  movdqa  [rsp+68h+var_28], xmm2
0x180003062  movdqa  [rsp+68h+var_18], xmm3
0x180003068  mov     rdx, rax
0x18000306b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180003072  call    __delayLoadHelper2
0x180003077  movdqa  xmm0, [rsp+68h+var_48]
0x18000307d  movdqa  xmm1, [rsp+68h+var_38]
0x180003083  movdqa  xmm2, [rsp+68h+var_28]
0x180003089  movdqa  xmm3, [rsp+68h+var_18]
0x18000308f  mov     rcx, [rsp+68h+arg_0]
0x180003094  mov     rdx, [rsp+68h+arg_8]
0x180003099  mov     r8, [rsp+68h+arg_10]
0x1800030a1  mov     r9, [rsp+68h+arg_18]
0x1800030a9  add     rsp, 68h
0x1800030ad  jmp     short $+2
0x1800030af  jmp     rax
```
