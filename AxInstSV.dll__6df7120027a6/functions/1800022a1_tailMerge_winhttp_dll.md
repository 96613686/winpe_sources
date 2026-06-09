# __tailMerge_winhttp_dll

- ea: `0x1800022a1`
- end: `0x18000231a`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002320`
- `0x180002417`
- `0x180002429`
- `0x18000243b`
- `0x18000244d`
- `0x18000245f`
- `0x180002471`
- `0x180002483`
- `0x180002495`
- `0x1800024a7`
- `0x1800024b9`
- `0x1800024cb`
- `0x1800024dd`
- `0x1800024ef`
- `0x180002501`
- `0x180002513`

## callees

- `0x1800022a1`
- `0x180014100`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022a1  mov     [rsp+arg_0], rcx
0x1800022a6  mov     [rsp+arg_8], rdx
0x1800022ab  mov     [rsp+arg_10], r8
0x1800022b0  mov     [rsp+arg_18], r9
0x1800022b5  sub     rsp, 68h
0x1800022b9  movdqa  [rsp+68h+var_48], xmm0
0x1800022bf  movdqa  [rsp+68h+var_38], xmm1
0x1800022c5  movdqa  [rsp+68h+var_28], xmm2
0x1800022cb  movdqa  [rsp+68h+var_18], xmm3
0x1800022d1  mov     rdx, rax
0x1800022d4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x1800022db  call    __delayLoadHelper2
0x1800022e0  movdqa  xmm0, [rsp+68h+var_48]
0x1800022e6  movdqa  xmm1, [rsp+68h+var_38]
0x1800022ec  movdqa  xmm2, [rsp+68h+var_28]
0x1800022f2  movdqa  xmm3, [rsp+68h+var_18]
0x1800022f8  mov     rcx, [rsp+68h+arg_0]
0x1800022fd  mov     rdx, [rsp+68h+arg_8]
0x180002302  mov     r8, [rsp+68h+arg_10]
0x18000230a  mov     r9, [rsp+68h+arg_18]
0x180002312  add     rsp, 68h
0x180002316  jmp     short $+2
0x180002318  jmp     rax
```
