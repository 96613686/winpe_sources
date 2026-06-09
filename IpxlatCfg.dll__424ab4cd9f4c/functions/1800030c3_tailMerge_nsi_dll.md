# __tailMerge_nsi_dll

- ea: `0x1800030c3`
- end: `0x18000313c`
- name: `__tailMerge_nsi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003142`
- `0x180003154`
- `0x180003166`
- `0x180003178`
- `0x18000318a`

## callees

- `0x1800030c3`
- `0x180017cd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_nsi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_nsi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800030c3  mov     [rsp+arg_0], rcx
0x1800030c8  mov     [rsp+arg_8], rdx
0x1800030cd  mov     [rsp+arg_10], r8
0x1800030d2  mov     [rsp+arg_18], r9
0x1800030d7  sub     rsp, 68h
0x1800030db  movdqa  [rsp+68h+var_48], xmm0
0x1800030e1  movdqa  [rsp+68h+var_38], xmm1
0x1800030e7  movdqa  [rsp+68h+var_28], xmm2
0x1800030ed  movdqa  [rsp+68h+var_18], xmm3
0x1800030f3  mov     rdx, rax
0x1800030f6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_nsi_dll
0x1800030fd  call    __delayLoadHelper2
0x180003102  movdqa  xmm0, [rsp+68h+var_48]
0x180003108  movdqa  xmm1, [rsp+68h+var_38]
0x18000310e  movdqa  xmm2, [rsp+68h+var_28]
0x180003114  movdqa  xmm3, [rsp+68h+var_18]
0x18000311a  mov     rcx, [rsp+68h+arg_0]
0x18000311f  mov     rdx, [rsp+68h+arg_8]
0x180003124  mov     r8, [rsp+68h+arg_10]
0x18000312c  mov     r9, [rsp+68h+arg_18]
0x180003134  add     rsp, 68h
0x180003138  jmp     short $+2
0x18000313a  jmp     rax
```
