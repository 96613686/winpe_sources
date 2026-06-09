# __tailMerge_rpcrt4_dll

- ea: `0x18000a830`
- end: `0x18000a8a9`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a8af`
- `0x18000a8d3`
- `0x18000a8e5`
- `0x18000a8f7`
- `0x18000aa79`
- `0x18000aa8b`
- `0x18000aa9d`
- `0x18000abe9`

## callees

- `0x180007cd0`
- `0x18000a830`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a830  mov     [rsp+arg_0], rcx
0x18000a835  mov     [rsp+arg_8], rdx
0x18000a83a  mov     [rsp+arg_10], r8
0x18000a83f  mov     [rsp+arg_18], r9
0x18000a844  sub     rsp, 68h
0x18000a848  movdqa  [rsp+68h+var_48], xmm0
0x18000a84e  movdqa  [rsp+68h+var_38], xmm1
0x18000a854  movdqa  [rsp+68h+var_28], xmm2
0x18000a85a  movdqa  [rsp+68h+var_18], xmm3
0x18000a860  mov     rdx, rax
0x18000a863  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000a86a  call    __delayLoadHelper2
0x18000a86f  movdqa  xmm0, [rsp+68h+var_48]
0x18000a875  movdqa  xmm1, [rsp+68h+var_38]
0x18000a87b  movdqa  xmm2, [rsp+68h+var_28]
0x18000a881  movdqa  xmm3, [rsp+68h+var_18]
0x18000a887  mov     rcx, [rsp+68h+arg_0]
0x18000a88c  mov     rdx, [rsp+68h+arg_8]
0x18000a891  mov     r8, [rsp+68h+arg_10]
0x18000a899  mov     r9, [rsp+68h+arg_18]
0x18000a8a1  add     rsp, 68h
0x18000a8a5  jmp     short $+2
0x18000a8a7  jmp     rax
```
