# __tailMerge_ws2_32_dll

- ea: `0x180002e01`
- end: `0x180002e7a`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e80`
- `0x180002e92`

## callees

- `0x180002e01`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002e01  mov     [rsp+arg_0], rcx
0x180002e06  mov     [rsp+arg_8], rdx
0x180002e0b  mov     [rsp+arg_10], r8
0x180002e10  mov     [rsp+arg_18], r9
0x180002e15  sub     rsp, 68h
0x180002e19  movdqa  [rsp+68h+var_48], xmm0
0x180002e1f  movdqa  [rsp+68h+var_38], xmm1
0x180002e25  movdqa  [rsp+68h+var_28], xmm2
0x180002e2b  movdqa  [rsp+68h+var_18], xmm3
0x180002e31  mov     rdx, rax
0x180002e34  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180002e3b  call    __delayLoadHelper2
0x180002e40  movdqa  xmm0, [rsp+68h+var_48]
0x180002e46  movdqa  xmm1, [rsp+68h+var_38]
0x180002e4c  movdqa  xmm2, [rsp+68h+var_28]
0x180002e52  movdqa  xmm3, [rsp+68h+var_18]
0x180002e58  mov     rcx, [rsp+68h+arg_0]
0x180002e5d  mov     rdx, [rsp+68h+arg_8]
0x180002e62  mov     r8, [rsp+68h+arg_10]
0x180002e6a  mov     r9, [rsp+68h+arg_18]
0x180002e72  add     rsp, 68h
0x180002e76  jmp     short $+2
0x180002e78  jmp     rax
```
