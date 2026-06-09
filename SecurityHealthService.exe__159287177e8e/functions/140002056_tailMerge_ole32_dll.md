# __tailMerge_ole32_dll

- ea: `0x140002056`
- end: `0x1400020cf`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400020d5`
- `0x1400020e7`
- `0x1400020f9`
- `0x140002640`

## callees

- `0x140002056`
- `0x140011350`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002056  mov     [rsp+arg_0], rcx
0x14000205b  mov     [rsp+arg_8], rdx
0x140002060  mov     [rsp+arg_10], r8
0x140002065  mov     [rsp+arg_18], r9
0x14000206a  sub     rsp, 68h
0x14000206e  movdqa  [rsp+68h+var_48], xmm0
0x140002074  movdqa  [rsp+68h+var_38], xmm1
0x14000207a  movdqa  [rsp+68h+var_28], xmm2
0x140002080  movdqa  [rsp+68h+var_18], xmm3
0x140002086  mov     rdx, rax
0x140002089  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x140002090  call    __delayLoadHelper2
0x140002095  movdqa  xmm0, [rsp+68h+var_48]
0x14000209b  movdqa  xmm1, [rsp+68h+var_38]
0x1400020a1  movdqa  xmm2, [rsp+68h+var_28]
0x1400020a7  movdqa  xmm3, [rsp+68h+var_18]
0x1400020ad  mov     rcx, [rsp+68h+arg_0]
0x1400020b2  mov     rdx, [rsp+68h+arg_8]
0x1400020b7  mov     r8, [rsp+68h+arg_10]
0x1400020bf  mov     r9, [rsp+68h+arg_18]
0x1400020c7  add     rsp, 68h
0x1400020cb  jmp     short $+2
0x1400020cd  jmp     rax
```
