# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14000e6c7`
- end: `0x14000e70e`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001e40`
- `0x140001fe8`
- `0x14000e6c7`

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
0x14000e6c7  mov     [rsp+arg_8], rdx
0x14000e6cc  push    rbp
0x14000e6cd  sub     rsp, 20h
0x14000e6d1  mov     rbp, rdx
0x14000e6d4  mov     rcx, [rbp+58h]
0x14000e6d8  mov     [rbp+58h], rcx
0x14000e6dc  xor     eax, eax
0x14000e6de  add     rcx, 1; Size
0x14000e6e2  jz      short loc_14000E6F9
0x14000e6e4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e6e8  ja      short loc_14000E6F4
0x14000e6ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e6ef  test    rax, rax
0x14000e6f2  jnz     short loc_14000E6F9
0x14000e6f4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000e6f9  mov     [rbp+68h], rax
0x14000e6fd  mov     rax, 0
0x14000e707  add     rsp, 20h
0x14000e70b  pop     rbp
0x14000e70c  retn
```
