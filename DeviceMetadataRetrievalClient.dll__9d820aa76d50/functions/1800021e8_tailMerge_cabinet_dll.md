# __tailMerge_cabinet_dll

- ea: `0x1800021e8`
- end: `0x180002261`
- name: `__tailMerge_cabinet_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002267`
- `0x180002279`
- `0x18000228b`

## callees

- `0x1800021e8`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_cabinet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cabinet_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800021e8  mov     [rsp+arg_0], rcx
0x1800021ed  mov     [rsp+arg_8], rdx
0x1800021f2  mov     [rsp+arg_10], r8
0x1800021f7  mov     [rsp+arg_18], r9
0x1800021fc  sub     rsp, 68h
0x180002200  movdqa  [rsp+68h+var_48], xmm0
0x180002206  movdqa  [rsp+68h+var_38], xmm1
0x18000220c  movdqa  [rsp+68h+var_28], xmm2
0x180002212  movdqa  [rsp+68h+var_18], xmm3
0x180002218  mov     rdx, rax
0x18000221b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cabinet_dll
0x180002222  call    __delayLoadHelper2
0x180002227  movdqa  xmm0, [rsp+68h+var_48]
0x18000222d  movdqa  xmm1, [rsp+68h+var_38]
0x180002233  movdqa  xmm2, [rsp+68h+var_28]
0x180002239  movdqa  xmm3, [rsp+68h+var_18]
0x18000223f  mov     rcx, [rsp+68h+arg_0]
0x180002244  mov     rdx, [rsp+68h+arg_8]
0x180002249  mov     r8, [rsp+68h+arg_10]
0x180002251  mov     r9, [rsp+68h+arg_18]
0x180002259  add     rsp, 68h
0x18000225d  jmp     short $+2
0x18000225f  jmp     rax
```
