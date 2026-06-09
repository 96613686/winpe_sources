# __tailMerge_rpcrt4_dll

- ea: `0x140003227`
- end: `0x1400032a0`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400032a6`
- `0x1400032b8`
- `0x1400032ca`
- `0x14000339c`
- `0x1400033bc`

## callees

- `0x140003227`
- `0x14001d800`

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
0x140003227  mov     [rsp+arg_0], rcx
0x14000322c  mov     [rsp+arg_8], rdx
0x140003231  mov     [rsp+arg_10], r8
0x140003236  mov     [rsp+arg_18], r9
0x14000323b  sub     rsp, 68h
0x14000323f  movdqa  [rsp+68h+var_48], xmm0
0x140003245  movdqa  [rsp+68h+var_38], xmm1
0x14000324b  movdqa  [rsp+68h+var_28], xmm2
0x140003251  movdqa  [rsp+68h+var_18], xmm3
0x140003257  mov     rdx, rax
0x14000325a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x140003261  call    __delayLoadHelper2
0x140003266  movdqa  xmm0, [rsp+68h+var_48]
0x14000326c  movdqa  xmm1, [rsp+68h+var_38]
0x140003272  movdqa  xmm2, [rsp+68h+var_28]
0x140003278  movdqa  xmm3, [rsp+68h+var_18]
0x14000327e  mov     rcx, [rsp+68h+arg_0]
0x140003283  mov     rdx, [rsp+68h+arg_8]
0x140003288  mov     r8, [rsp+68h+arg_10]
0x140003290  mov     r9, [rsp+68h+arg_18]
0x140003298  add     rsp, 68h
0x14000329c  jmp     short $+2
0x14000329e  jmp     rax
```
