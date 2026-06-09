# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180010d09`
- end: `0x180010d50`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800014b4`
- `0x180001658`
- `0x180010d09`

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
0x180010d09  mov     [rsp+arg_8], rdx
0x180010d0e  push    rbp
0x180010d0f  sub     rsp, 20h
0x180010d13  mov     rbp, rdx
0x180010d16  mov     rcx, [rbp+58h]
0x180010d1a  mov     [rbp+58h], rcx
0x180010d1e  xor     eax, eax
0x180010d20  add     rcx, 1; Size
0x180010d24  jz      short loc_180010D3B
0x180010d26  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010d2a  ja      short loc_180010D36
0x180010d2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d31  test    rax, rax
0x180010d34  jnz     short loc_180010D3B
0x180010d36  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180010d3b  mov     [rbp+68h], rax
0x180010d3f  mov     rax, 0
0x180010d49  add     rsp, 20h
0x180010d4d  pop     rbp
0x180010d4e  retn
```
