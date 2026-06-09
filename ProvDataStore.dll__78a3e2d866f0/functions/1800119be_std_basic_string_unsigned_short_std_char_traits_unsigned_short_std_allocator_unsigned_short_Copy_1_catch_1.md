# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x1800119be`
- end: `0x180011a12`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800018f4`
- `0x1800119be`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800119f7`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800119f7`

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
0x1800119be  mov     [rsp+arg_8], rdx
0x1800119c3  push    rbp
0x1800119c4  sub     rsp, 20h
0x1800119c8  mov     rbp, rdx
0x1800119cb  mov     rcx, [rbp+58h]
0x1800119cf  mov     [rbp+58h], rcx
0x1800119d3  xor     eax, eax
0x1800119d5  add     rcx, 1
0x1800119d9  jz      short loc_1800119FD
0x1800119db  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800119e5  cmp     rcx, rax
0x1800119e8  ja      short loc_1800119F7
0x1800119ea  add     rcx, rcx; Size
0x1800119ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800119f2  test    rax, rax
0x1800119f5  jnz     short loc_1800119FD
0x1800119f7  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800119fd  mov     [rbp+68h], rax
0x180011a01  mov     rax, 0
0x180011a0b  add     rsp, 20h
0x180011a0f  pop     rbp
0x180011a10  retn
```
