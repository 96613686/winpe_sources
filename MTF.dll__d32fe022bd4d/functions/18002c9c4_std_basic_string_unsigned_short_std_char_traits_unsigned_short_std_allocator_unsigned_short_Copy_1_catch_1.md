# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18002c9c4`
- end: `0x18002ca17`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x18002c9c4`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18002c9c4  mov     [rsp+arg_8], rdx
0x18002c9c9  push    rbp
0x18002c9ca  sub     rsp, 20h
0x18002c9ce  mov     rbp, rdx
0x18002c9d1  mov     rcx, [rbp+58h]
0x18002c9d5  mov     [rbp+58h], rcx
0x18002c9d9  xor     eax, eax
0x18002c9db  add     rcx, 1
0x18002c9df  jz      short loc_18002CA02
0x18002c9e1  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002c9eb  cmp     rcx, rax
0x18002c9ee  ja      short loc_18002C9FD
0x18002c9f0  add     rcx, rcx; Size
0x18002c9f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c9f8  test    rax, rax
0x18002c9fb  jnz     short loc_18002CA02
0x18002c9fd  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002ca02  mov     [rbp+68h], rax
0x18002ca06  mov     rax, 0
0x18002ca10  add     rsp, 20h
0x18002ca14  pop     rbp
0x18002ca15  retn
```
