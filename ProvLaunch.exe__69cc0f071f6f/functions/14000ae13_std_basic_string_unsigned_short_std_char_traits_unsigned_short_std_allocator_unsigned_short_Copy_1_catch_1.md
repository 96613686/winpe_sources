# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x14000ae13`
- end: `0x14000ae67`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001864`
- `0x14000ae13`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000ae4c`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000ae4c`

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
0x14000ae13  mov     [rsp+arg_8], rdx
0x14000ae18  push    rbp
0x14000ae19  sub     rsp, 20h
0x14000ae1d  mov     rbp, rdx
0x14000ae20  mov     rcx, [rbp+58h]
0x14000ae24  mov     [rbp+58h], rcx
0x14000ae28  xor     eax, eax
0x14000ae2a  add     rcx, 1
0x14000ae2e  jz      short loc_14000AE52
0x14000ae30  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000ae3a  cmp     rcx, rax
0x14000ae3d  ja      short loc_14000AE4C
0x14000ae3f  add     rcx, rcx; Size
0x14000ae42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ae47  test    rax, rax
0x14000ae4a  jnz     short loc_14000AE52
0x14000ae4c  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000ae52  mov     [rbp+68h], rax
0x14000ae56  mov     rax, 0
0x14000ae60  add     rsp, 20h
0x14000ae64  pop     rbp
0x14000ae65  retn
```
