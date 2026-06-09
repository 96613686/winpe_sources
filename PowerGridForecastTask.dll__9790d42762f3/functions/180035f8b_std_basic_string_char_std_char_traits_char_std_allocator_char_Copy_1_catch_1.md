# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180035f8b`
- end: `0x180035fd2`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x180035f8b`

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
0x180035f8b  mov     [rsp+arg_8], rdx
0x180035f90  push    rbp
0x180035f91  sub     rsp, 20h
0x180035f95  mov     rbp, rdx
0x180035f98  mov     rcx, [rbp+58h]
0x180035f9c  mov     [rbp+58h], rcx
0x180035fa0  xor     eax, eax
0x180035fa2  add     rcx, 1; Size
0x180035fa6  jz      short loc_180035FBD
0x180035fa8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035fac  ja      short loc_180035FB8
0x180035fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035fb3  test    rax, rax
0x180035fb6  jnz     short loc_180035FBD
0x180035fb8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180035fbd  mov     [rbp+68h], rax
0x180035fc1  mov     rax, 0
0x180035fcb  add     rsp, 20h
0x180035fcf  pop     rbp
0x180035fd0  retn
```
