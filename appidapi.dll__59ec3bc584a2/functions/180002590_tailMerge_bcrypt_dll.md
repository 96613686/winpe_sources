# __tailMerge_bcrypt_dll

- ea: `0x180002590`
- end: `0x180002609`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000260f`
- `0x180002621`
- `0x180002633`
- `0x180002645`
- `0x180002657`
- `0x180002669`
- `0x18000267b`

## callees

- `0x180002590`
- `0x180009440`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002590  mov     [rsp+arg_0], rcx
0x180002595  mov     [rsp+arg_8], rdx
0x18000259a  mov     [rsp+arg_10], r8
0x18000259f  mov     [rsp+arg_18], r9
0x1800025a4  sub     rsp, 68h
0x1800025a8  movdqa  [rsp+68h+var_48], xmm0
0x1800025ae  movdqa  [rsp+68h+var_38], xmm1
0x1800025b4  movdqa  [rsp+68h+var_28], xmm2
0x1800025ba  movdqa  [rsp+68h+var_18], xmm3
0x1800025c0  mov     rdx, rax
0x1800025c3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800025ca  call    __delayLoadHelper2
0x1800025cf  movdqa  xmm0, [rsp+68h+var_48]
0x1800025d5  movdqa  xmm1, [rsp+68h+var_38]
0x1800025db  movdqa  xmm2, [rsp+68h+var_28]
0x1800025e1  movdqa  xmm3, [rsp+68h+var_18]
0x1800025e7  mov     rcx, [rsp+68h+arg_0]
0x1800025ec  mov     rdx, [rsp+68h+arg_8]
0x1800025f1  mov     r8, [rsp+68h+arg_10]
0x1800025f9  mov     r9, [rsp+68h+arg_18]
0x180002601  add     rsp, 68h
0x180002605  jmp     short $+2
0x180002607  jmp     rax
```
