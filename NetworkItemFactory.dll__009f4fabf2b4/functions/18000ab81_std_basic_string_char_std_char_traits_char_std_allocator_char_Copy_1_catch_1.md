# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000ab81`
- end: `0x18000abc8`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001218`
- `0x1800070c8`
- `0x18000ab81`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
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
0x18000ab81  mov     [rsp+arg_8], rdx
0x18000ab86  push    rbp
0x18000ab87  sub     rsp, 20h
0x18000ab8b  mov     rbp, rdx
0x18000ab8e  mov     rcx, [rbp+58h]
0x18000ab92  mov     [rbp+58h], rcx
0x18000ab96  xor     eax, eax
0x18000ab98  add     rcx, 1; unsigned __int64
0x18000ab9c  jz      short loc_18000ABB3
0x18000ab9e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000aba2  ja      short loc_18000ABAE
0x18000aba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aba9  test    rax, rax
0x18000abac  jnz     short loc_18000ABB3
0x18000abae  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000abb3  mov     [rbp+68h], rax
0x18000abb7  mov     rax, 0
0x18000abc1  add     rsp, 20h
0x18000abc5  pop     rbp
0x18000abc6  retn
```
