# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18001ea72`
- end: `0x18001eac5`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001444`
- `0x1800015e8`
- `0x18001ea72`

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
0x18001ea72  mov     [rsp+arg_8], rdx
0x18001ea77  push    rbp
0x18001ea78  sub     rsp, 20h
0x18001ea7c  mov     rbp, rdx
0x18001ea7f  mov     rcx, [rbp+58h]
0x18001ea83  mov     [rbp+58h], rcx
0x18001ea87  xor     eax, eax
0x18001ea89  add     rcx, 1
0x18001ea8d  jz      short loc_18001EAB0
0x18001ea8f  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001ea99  cmp     rcx, rax
0x18001ea9c  ja      short loc_18001EAAB
0x18001ea9e  add     rcx, rcx; Size
0x18001eaa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eaa6  test    rax, rax
0x18001eaa9  jnz     short loc_18001EAB0
0x18001eaab  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001eab0  mov     [rbp+68h], rax
0x18001eab4  mov     rax, 0
0x18001eabe  add     rsp, 20h
0x18001eac2  pop     rbp
0x18001eac3  retn
```
