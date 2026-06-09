# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1800118a1`
- end: `0x1800118e8`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800015c0`
- `0x180001768`
- `0x1800118a1`

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
0x1800118a1  mov     [rsp+arg_8], rdx
0x1800118a6  push    rbp
0x1800118a7  sub     rsp, 20h
0x1800118ab  mov     rbp, rdx
0x1800118ae  mov     rcx, [rbp+58h]
0x1800118b2  mov     [rbp+58h], rcx
0x1800118b6  xor     eax, eax
0x1800118b8  add     rcx, 1; Size
0x1800118bc  jz      short loc_1800118D3
0x1800118be  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800118c2  ja      short loc_1800118CE
0x1800118c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800118c9  test    rax, rax
0x1800118cc  jnz     short loc_1800118D3
0x1800118ce  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800118d3  mov     [rbp+68h], rax
0x1800118d7  mov     rax, 0
0x1800118e1  add     rsp, 20h
0x1800118e5  pop     rbp
0x1800118e6  retn
```
