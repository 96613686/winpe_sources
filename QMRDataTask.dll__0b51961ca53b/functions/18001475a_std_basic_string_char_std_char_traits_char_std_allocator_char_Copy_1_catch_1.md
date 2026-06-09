# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18001475a`
- end: `0x1800147a1`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001404`
- `0x1800015a8`
- `0x18001475a`

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
0x18001475a  mov     [rsp+arg_8], rdx
0x18001475f  push    rbp
0x180014760  sub     rsp, 20h
0x180014764  mov     rbp, rdx
0x180014767  mov     rcx, [rbp+58h]
0x18001476b  mov     [rbp+58h], rcx
0x18001476f  xor     eax, eax
0x180014771  add     rcx, 1; Size
0x180014775  jz      short loc_18001478C
0x180014777  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001477b  ja      short loc_180014787
0x18001477d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014782  test    rax, rax
0x180014785  jnz     short loc_18001478C
0x180014787  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001478c  mov     [rbp+68h], rax
0x180014790  mov     rax, 0
0x18001479a  add     rsp, 20h
0x18001479e  pop     rbp
0x18001479f  retn
```
