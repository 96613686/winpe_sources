# __tailMerge_iphlpapi_dll

- ea: `0x18000a903`
- end: `0x18000a97c`
- name: `__tailMerge_iphlpapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a982`
- `0x18000a994`

## callees

- `0x180007cd0`
- `0x18000a903`

## pseudocode

```c
__int64 __fastcall _tailMerge_iphlpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a903  mov     [rsp+arg_0], rcx
0x18000a908  mov     [rsp+arg_8], rdx
0x18000a90d  mov     [rsp+arg_10], r8
0x18000a912  mov     [rsp+arg_18], r9
0x18000a917  sub     rsp, 68h
0x18000a91b  movdqa  [rsp+68h+var_48], xmm0
0x18000a921  movdqa  [rsp+68h+var_38], xmm1
0x18000a927  movdqa  [rsp+68h+var_28], xmm2
0x18000a92d  movdqa  [rsp+68h+var_18], xmm3
0x18000a933  mov     rdx, rax
0x18000a936  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll
0x18000a93d  call    __delayLoadHelper2
0x18000a942  movdqa  xmm0, [rsp+68h+var_48]
0x18000a948  movdqa  xmm1, [rsp+68h+var_38]
0x18000a94e  movdqa  xmm2, [rsp+68h+var_28]
0x18000a954  movdqa  xmm3, [rsp+68h+var_18]
0x18000a95a  mov     rcx, [rsp+68h+arg_0]
0x18000a95f  mov     rdx, [rsp+68h+arg_8]
0x18000a964  mov     r8, [rsp+68h+arg_10]
0x18000a96c  mov     r9, [rsp+68h+arg_18]
0x18000a974  add     rsp, 68h
0x18000a978  jmp     short $+2
0x18000a97a  jmp     rax
```
