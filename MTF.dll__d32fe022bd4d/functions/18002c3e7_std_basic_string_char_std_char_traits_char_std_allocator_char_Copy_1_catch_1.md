# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18002c3e7`
- end: `0x18002c42e`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x18002c3e7`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18002c3e7  mov     [rsp+arg_8], rdx
0x18002c3ec  push    rbp
0x18002c3ed  sub     rsp, 20h
0x18002c3f1  mov     rbp, rdx
0x18002c3f4  mov     rcx, [rbp+58h]
0x18002c3f8  mov     [rbp+58h], rcx
0x18002c3fc  xor     eax, eax
0x18002c3fe  add     rcx, 1; Size
0x18002c402  jz      short loc_18002C419
0x18002c404  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c408  ja      short loc_18002C414
0x18002c40a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c40f  test    rax, rax
0x18002c412  jnz     short loc_18002C419
0x18002c414  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002c419  mov     [rbp+68h], rax
0x18002c41d  mov     rax, 0
0x18002c427  add     rsp, 20h
0x18002c42b  pop     rbp
0x18002c42c  retn
```
