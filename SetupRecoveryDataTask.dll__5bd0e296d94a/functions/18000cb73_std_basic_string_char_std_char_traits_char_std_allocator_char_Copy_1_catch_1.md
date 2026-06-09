# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000cb73`
- end: `0x18000cbba`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001404`
- `0x1800015a8`
- `0x18000cb73`

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
0x18000cb73  mov     [rsp+arg_8], rdx
0x18000cb78  push    rbp
0x18000cb79  sub     rsp, 20h
0x18000cb7d  mov     rbp, rdx
0x18000cb80  mov     rcx, [rbp+58h]
0x18000cb84  mov     [rbp+58h], rcx
0x18000cb88  xor     eax, eax
0x18000cb8a  add     rcx, 1; Size
0x18000cb8e  jz      short loc_18000CBA5
0x18000cb90  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cb94  ja      short loc_18000CBA0
0x18000cb96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cb9b  test    rax, rax
0x18000cb9e  jnz     short loc_18000CBA5
0x18000cba0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000cba5  mov     [rbp+68h], rax
0x18000cba9  mov     rax, 0
0x18000cbb3  add     rsp, 20h
0x18000cbb7  pop     rbp
0x18000cbb8  retn
```
