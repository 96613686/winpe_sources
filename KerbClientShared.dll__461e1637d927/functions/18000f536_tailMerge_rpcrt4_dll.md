# __tailMerge_rpcrt4_dll

- ea: `0x18000f536`
- end: `0x18000f5af`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f5b5`
- `0x18000f5c7`
- `0x18000f5d9`

## callees

- `0x18000f536`
- `0x1800282b0`

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
0x18000f536  mov     [rsp+arg_0], rcx
0x18000f53b  mov     [rsp+arg_8], rdx
0x18000f540  mov     [rsp+arg_10], r8
0x18000f545  mov     [rsp+arg_18], r9
0x18000f54a  sub     rsp, 68h
0x18000f54e  movdqa  [rsp+68h+var_48], xmm0
0x18000f554  movdqa  [rsp+68h+var_38], xmm1
0x18000f55a  movdqa  [rsp+68h+var_28], xmm2
0x18000f560  movdqa  [rsp+68h+var_18], xmm3
0x18000f566  mov     rdx, rax
0x18000f569  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000f570  call    __delayLoadHelper2
0x18000f575  movdqa  xmm0, [rsp+68h+var_48]
0x18000f57b  movdqa  xmm1, [rsp+68h+var_38]
0x18000f581  movdqa  xmm2, [rsp+68h+var_28]
0x18000f587  movdqa  xmm3, [rsp+68h+var_18]
0x18000f58d  mov     rcx, [rsp+68h+arg_0]
0x18000f592  mov     rdx, [rsp+68h+arg_8]
0x18000f597  mov     r8, [rsp+68h+arg_10]
0x18000f59f  mov     r9, [rsp+68h+arg_18]
0x18000f5a7  add     rsp, 68h
0x18000f5ab  jmp     short $+2
0x18000f5ad  jmp     rax
```
