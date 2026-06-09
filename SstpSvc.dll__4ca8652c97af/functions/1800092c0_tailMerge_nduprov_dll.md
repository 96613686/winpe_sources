# __tailMerge_nduprov_dll

- ea: `0x1800092c0`
- end: `0x180009339`
- name: `__tailMerge_nduprov_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000933f`
- `0x180009351`
- `0x180009363`

## callees

- `0x180007290`
- `0x1800092c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_nduprov_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_nduprov_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800092c0  mov     [rsp+arg_0], rcx
0x1800092c5  mov     [rsp+arg_8], rdx
0x1800092ca  mov     [rsp+arg_10], r8
0x1800092cf  mov     [rsp+arg_18], r9
0x1800092d4  sub     rsp, 68h
0x1800092d8  movdqa  [rsp+68h+var_48], xmm0
0x1800092de  movdqa  [rsp+68h+var_38], xmm1
0x1800092e4  movdqa  [rsp+68h+var_28], xmm2
0x1800092ea  movdqa  [rsp+68h+var_18], xmm3
0x1800092f0  mov     rdx, rax
0x1800092f3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_nduprov_dll
0x1800092fa  call    __delayLoadHelper2
0x1800092ff  movdqa  xmm0, [rsp+68h+var_48]
0x180009305  movdqa  xmm1, [rsp+68h+var_38]
0x18000930b  movdqa  xmm2, [rsp+68h+var_28]
0x180009311  movdqa  xmm3, [rsp+68h+var_18]
0x180009317  mov     rcx, [rsp+68h+arg_0]
0x18000931c  mov     rdx, [rsp+68h+arg_8]
0x180009321  mov     r8, [rsp+68h+arg_10]
0x180009329  mov     r9, [rsp+68h+arg_18]
0x180009331  add     rsp, 68h
0x180009335  jmp     short $+2
0x180009337  jmp     rax
```
