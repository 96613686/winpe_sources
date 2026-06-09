# __tailMerge_wininet_dll

- ea: `0x180002d1c`
- end: `0x180002d95`
- name: `__tailMerge_wininet_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d9b`
- `0x180002dad`
- `0x180002dbf`
- `0x180002dd1`
- `0x180002de3`
- `0x180002df5`

## callees

- `0x180002d1c`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_wininet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wininet_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002d1c  mov     [rsp+arg_0], rcx
0x180002d21  mov     [rsp+arg_8], rdx
0x180002d26  mov     [rsp+arg_10], r8
0x180002d2b  mov     [rsp+arg_18], r9
0x180002d30  sub     rsp, 68h
0x180002d34  movdqa  [rsp+68h+var_48], xmm0
0x180002d3a  movdqa  [rsp+68h+var_38], xmm1
0x180002d40  movdqa  [rsp+68h+var_28], xmm2
0x180002d46  movdqa  [rsp+68h+var_18], xmm3
0x180002d4c  mov     rdx, rax
0x180002d4f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wininet_dll
0x180002d56  call    __delayLoadHelper2
0x180002d5b  movdqa  xmm0, [rsp+68h+var_48]
0x180002d61  movdqa  xmm1, [rsp+68h+var_38]
0x180002d67  movdqa  xmm2, [rsp+68h+var_28]
0x180002d6d  movdqa  xmm3, [rsp+68h+var_18]
0x180002d73  mov     rcx, [rsp+68h+arg_0]
0x180002d78  mov     rdx, [rsp+68h+arg_8]
0x180002d7d  mov     r8, [rsp+68h+arg_10]
0x180002d85  mov     r9, [rsp+68h+arg_18]
0x180002d8d  add     rsp, 68h
0x180002d91  jmp     short $+2
0x180002d93  jmp     rax
```
