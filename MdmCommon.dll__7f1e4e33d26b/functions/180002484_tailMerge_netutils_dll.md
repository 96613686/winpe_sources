# __tailMerge_netutils_dll

- ea: `0x180002484`
- end: `0x1800024fd`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002503`

## callees

- `0x180002484`
- `0x18001d370`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002484  mov     [rsp+arg_0], rcx
0x180002489  mov     [rsp+arg_8], rdx
0x18000248e  mov     [rsp+arg_10], r8
0x180002493  mov     [rsp+arg_18], r9
0x180002498  sub     rsp, 68h
0x18000249c  movdqa  [rsp+68h+var_48], xmm0
0x1800024a2  movdqa  [rsp+68h+var_38], xmm1
0x1800024a8  movdqa  [rsp+68h+var_28], xmm2
0x1800024ae  movdqa  [rsp+68h+var_18], xmm3
0x1800024b4  mov     rdx, rax
0x1800024b7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x1800024be  call    __delayLoadHelper2
0x1800024c3  movdqa  xmm0, [rsp+68h+var_48]
0x1800024c9  movdqa  xmm1, [rsp+68h+var_38]
0x1800024cf  movdqa  xmm2, [rsp+68h+var_28]
0x1800024d5  movdqa  xmm3, [rsp+68h+var_18]
0x1800024db  mov     rcx, [rsp+68h+arg_0]
0x1800024e0  mov     rdx, [rsp+68h+arg_8]
0x1800024e5  mov     r8, [rsp+68h+arg_10]
0x1800024ed  mov     r9, [rsp+68h+arg_18]
0x1800024f5  add     rsp, 68h
0x1800024f9  jmp     short $+2
0x1800024fb  jmp     rax
```
