# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180009b34`
- end: `0x180009b7b`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000126c`
- `0x180001418`
- `0x180009b34`

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
0x180009b34  mov     [rsp+arg_8], rdx
0x180009b39  push    rbp
0x180009b3a  sub     rsp, 20h
0x180009b3e  mov     rbp, rdx
0x180009b41  mov     rcx, [rbp+58h]
0x180009b45  mov     [rbp+58h], rcx
0x180009b49  xor     eax, eax
0x180009b4b  add     rcx, 1; Size
0x180009b4f  jz      short loc_180009B66
0x180009b51  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009b55  ja      short loc_180009B61
0x180009b57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b5c  test    rax, rax
0x180009b5f  jnz     short loc_180009B66
0x180009b61  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009b66  mov     [rbp+68h], rax
0x180009b6a  mov     rax, 0
0x180009b74  add     rsp, 20h
0x180009b78  pop     rbp
0x180009b79  retn
```
