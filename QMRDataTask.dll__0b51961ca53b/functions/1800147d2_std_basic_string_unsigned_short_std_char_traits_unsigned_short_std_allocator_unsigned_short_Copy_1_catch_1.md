# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x1800147d2`
- end: `0x180014825`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001404`
- `0x1800015a8`
- `0x1800147d2`

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
0x1800147d2  mov     [rsp+arg_8], rdx
0x1800147d7  push    rbp
0x1800147d8  sub     rsp, 20h
0x1800147dc  mov     rbp, rdx
0x1800147df  mov     rcx, [rbp+58h]
0x1800147e3  mov     [rbp+58h], rcx
0x1800147e7  xor     eax, eax
0x1800147e9  add     rcx, 1
0x1800147ed  jz      short loc_180014810
0x1800147ef  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800147f9  cmp     rcx, rax
0x1800147fc  ja      short loc_18001480B
0x1800147fe  add     rcx, rcx; Size
0x180014801  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014806  test    rax, rax
0x180014809  jnz     short loc_180014810
0x18001480b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180014810  mov     [rbp+68h], rax
0x180014814  mov     rax, 0
0x18001481e  add     rsp, 20h
0x180014822  pop     rbp
0x180014823  retn
```
