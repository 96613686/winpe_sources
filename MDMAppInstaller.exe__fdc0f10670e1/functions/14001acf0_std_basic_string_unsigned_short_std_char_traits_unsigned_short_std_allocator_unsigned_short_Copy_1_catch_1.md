# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x14001acf0`
- end: `0x14001ad44`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ba8`
- `0x14001acf0`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14001ad29`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14001ad29`

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
0x14001acf0  mov     [rsp+arg_8], rdx
0x14001acf5  push    rbp
0x14001acf6  sub     rsp, 20h
0x14001acfa  mov     rbp, rdx
0x14001acfd  mov     rcx, [rbp+58h]
0x14001ad01  mov     [rbp+58h], rcx
0x14001ad05  xor     eax, eax
0x14001ad07  add     rcx, 1
0x14001ad0b  jz      short loc_14001AD2F
0x14001ad0d  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001ad17  cmp     rcx, rax
0x14001ad1a  ja      short loc_14001AD29
0x14001ad1c  add     rcx, rcx; Size
0x14001ad1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ad24  test    rax, rax
0x14001ad27  jnz     short loc_14001AD2F
0x14001ad29  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14001ad2f  mov     [rbp+68h], rax
0x14001ad33  mov     rax, 0
0x14001ad3d  add     rsp, 20h
0x14001ad41  pop     rbp
0x14001ad42  retn
```
