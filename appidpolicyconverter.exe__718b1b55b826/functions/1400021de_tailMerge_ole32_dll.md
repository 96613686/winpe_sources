# __tailMerge_ole32_dll

- ea: `0x1400021de`
- end: `0x140002257`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000225d`

## callees

- `0x1400021de`
- `0x140009150`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400021de  mov     [rsp+arg_0], rcx
0x1400021e3  mov     [rsp+arg_8], rdx
0x1400021e8  mov     [rsp+arg_10], r8
0x1400021ed  mov     [rsp+arg_18], r9
0x1400021f2  sub     rsp, 68h
0x1400021f6  movdqa  [rsp+68h+var_48], xmm0
0x1400021fc  movdqa  [rsp+68h+var_38], xmm1
0x140002202  movdqa  [rsp+68h+var_28], xmm2
0x140002208  movdqa  [rsp+68h+var_18], xmm3
0x14000220e  mov     rdx, rax
0x140002211  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x140002218  call    __delayLoadHelper2
0x14000221d  movdqa  xmm0, [rsp+68h+var_48]
0x140002223  movdqa  xmm1, [rsp+68h+var_38]
0x140002229  movdqa  xmm2, [rsp+68h+var_28]
0x14000222f  movdqa  xmm3, [rsp+68h+var_18]
0x140002235  mov     rcx, [rsp+68h+arg_0]
0x14000223a  mov     rdx, [rsp+68h+arg_8]
0x14000223f  mov     r8, [rsp+68h+arg_10]
0x140002247  mov     r9, [rsp+68h+arg_18]
0x14000224f  add     rsp, 68h
0x140002253  jmp     short $+2
0x140002255  jmp     rax
```
