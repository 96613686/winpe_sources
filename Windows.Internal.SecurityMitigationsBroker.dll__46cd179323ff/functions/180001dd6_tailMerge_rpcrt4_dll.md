# __tailMerge_rpcrt4_dll

- ea: `0x180001dd6`
- end: `0x180001e4f`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e55`
- `0x180001e9c`
- `0x180001edc`
- `0x180001eee`

## callees

- `0x180001dd6`
- `0x180006880`

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
0x180001dd6  mov     [rsp+arg_0], rcx
0x180001ddb  mov     [rsp+arg_8], rdx
0x180001de0  mov     [rsp+arg_10], r8
0x180001de5  mov     [rsp+arg_18], r9
0x180001dea  sub     rsp, 68h
0x180001dee  movdqa  [rsp+68h+var_48], xmm0
0x180001df4  movdqa  [rsp+68h+var_38], xmm1
0x180001dfa  movdqa  [rsp+68h+var_28], xmm2
0x180001e00  movdqa  [rsp+68h+var_18], xmm3
0x180001e06  mov     rdx, rax
0x180001e09  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180001e10  call    __delayLoadHelper2
0x180001e15  movdqa  xmm0, [rsp+68h+var_48]
0x180001e1b  movdqa  xmm1, [rsp+68h+var_38]
0x180001e21  movdqa  xmm2, [rsp+68h+var_28]
0x180001e27  movdqa  xmm3, [rsp+68h+var_18]
0x180001e2d  mov     rcx, [rsp+68h+arg_0]
0x180001e32  mov     rdx, [rsp+68h+arg_8]
0x180001e37  mov     r8, [rsp+68h+arg_10]
0x180001e3f  mov     r9, [rsp+68h+arg_18]
0x180001e47  add     rsp, 68h
0x180001e4b  jmp     short $+2
0x180001e4d  jmp     rax
```
