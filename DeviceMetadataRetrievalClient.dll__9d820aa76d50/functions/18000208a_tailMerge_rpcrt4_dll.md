# __tailMerge_rpcrt4_dll

- ea: `0x18000208a`
- end: `0x180002103`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002109`
- `0x1800028dc`
- `0x1800028fc`
- `0x18000290e`
- `0x180002920`

## callees

- `0x18000208a`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000208a  mov     [rsp+arg_0], rcx
0x18000208f  mov     [rsp+arg_8], rdx
0x180002094  mov     [rsp+arg_10], r8
0x180002099  mov     [rsp+arg_18], r9
0x18000209e  sub     rsp, 68h
0x1800020a2  movdqa  [rsp+68h+var_48], xmm0
0x1800020a8  movdqa  [rsp+68h+var_38], xmm1
0x1800020ae  movdqa  [rsp+68h+var_28], xmm2
0x1800020b4  movdqa  [rsp+68h+var_18], xmm3
0x1800020ba  mov     rdx, rax
0x1800020bd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x1800020c4  call    __delayLoadHelper2
0x1800020c9  movdqa  xmm0, [rsp+68h+var_48]
0x1800020cf  movdqa  xmm1, [rsp+68h+var_38]
0x1800020d5  movdqa  xmm2, [rsp+68h+var_28]
0x1800020db  movdqa  xmm3, [rsp+68h+var_18]
0x1800020e1  mov     rcx, [rsp+68h+arg_0]
0x1800020e6  mov     rdx, [rsp+68h+arg_8]
0x1800020eb  mov     r8, [rsp+68h+arg_10]
0x1800020f3  mov     r9, [rsp+68h+arg_18]
0x1800020fb  add     rsp, 68h
0x1800020ff  jmp     short $+2
0x180002101  jmp     rax
```
