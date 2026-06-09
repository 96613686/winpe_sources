# __tailMerge_propsys_dll

- ea: `0x1800026bb`
- end: `0x180002734`
- name: `__tailMerge_propsys_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000273a`

## callees

- `0x1800026bb`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_propsys_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_propsys_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026bb  mov     [rsp+arg_0], rcx
0x1800026c0  mov     [rsp+arg_8], rdx
0x1800026c5  mov     [rsp+arg_10], r8
0x1800026ca  mov     [rsp+arg_18], r9
0x1800026cf  sub     rsp, 68h
0x1800026d3  movdqa  [rsp+68h+var_48], xmm0
0x1800026d9  movdqa  [rsp+68h+var_38], xmm1
0x1800026df  movdqa  [rsp+68h+var_28], xmm2
0x1800026e5  movdqa  [rsp+68h+var_18], xmm3
0x1800026eb  mov     rdx, rax
0x1800026ee  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_propsys_dll
0x1800026f5  call    __delayLoadHelper2
0x1800026fa  movdqa  xmm0, [rsp+68h+var_48]
0x180002700  movdqa  xmm1, [rsp+68h+var_38]
0x180002706  movdqa  xmm2, [rsp+68h+var_28]
0x18000270c  movdqa  xmm3, [rsp+68h+var_18]
0x180002712  mov     rcx, [rsp+68h+arg_0]
0x180002717  mov     rdx, [rsp+68h+arg_8]
0x18000271c  mov     r8, [rsp+68h+arg_10]
0x180002724  mov     r9, [rsp+68h+arg_18]
0x18000272c  add     rsp, 68h
0x180002730  jmp     short $+2
0x180002732  jmp     rax
```
