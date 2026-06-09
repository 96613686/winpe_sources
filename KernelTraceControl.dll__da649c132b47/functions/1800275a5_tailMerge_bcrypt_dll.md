# __tailMerge_bcrypt_dll

- ea: `0x1800275a5`
- end: `0x18002761e`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027599`
- `0x18002761e`
- `0x18002762a`
- `0x180027636`
- `0x180027642`
- `0x18002764e`
- `0x18002765a`

## callees

- `0x180025030`
- `0x1800275a5`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800275a5  mov     [rsp+arg_0], rcx
0x1800275aa  mov     [rsp+arg_8], rdx
0x1800275af  mov     [rsp+arg_10], r8
0x1800275b4  mov     [rsp+arg_18], r9
0x1800275b9  sub     rsp, 68h
0x1800275bd  movdqa  [rsp+68h+var_48], xmm0
0x1800275c3  movdqa  [rsp+68h+var_38], xmm1
0x1800275c9  movdqa  [rsp+68h+var_28], xmm2
0x1800275cf  movdqa  [rsp+68h+var_18], xmm3
0x1800275d5  mov     rdx, rax
0x1800275d8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800275df  call    __delayLoadHelper2
0x1800275e4  movdqa  xmm0, [rsp+68h+var_48]
0x1800275ea  movdqa  xmm1, [rsp+68h+var_38]
0x1800275f0  movdqa  xmm2, [rsp+68h+var_28]
0x1800275f6  movdqa  xmm3, [rsp+68h+var_18]
0x1800275fc  mov     rcx, [rsp+68h+arg_0]
0x180027601  mov     rdx, [rsp+68h+arg_8]
0x180027606  mov     r8, [rsp+68h+arg_10]
0x18002760e  mov     r9, [rsp+68h+arg_18]
0x180027616  add     rsp, 68h
0x18002761a  jmp     short $+2
0x18002761c  jmp     rax
```
