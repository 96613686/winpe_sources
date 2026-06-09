# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$3

- ea: `0x18001c48b`
- end: `0x18001c519`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$3`
- size: `142`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008700`
- `0x180008fce`
- `0x18001c48b`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001c4e0`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001c4e0`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 136);
  *(_QWORD *)(a2 + 136) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
    {
      *(_QWORD *)(a2 + 136) = 0;
      exception::exception((exception *)(a2 + 56), (const char *const *)(a2 + 136));
      *(_QWORD *)(a2 + 56) = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)(a2 + 56);
    }
  }
  *(_QWORD *)(a2 + 152) = v4;
  return 0;
}

```

## disassembly

```asm
0x18001c48b  mov     [rsp+arg_8], rdx
0x18001c490  push    rbp
0x18001c491  sub     rsp, 20h
0x18001c495  mov     rbp, rdx
0x18001c498  mov     rcx, [rbp+88h]
0x18001c49f  mov     [rbp+88h], rcx
0x18001c4a6  xor     eax, eax
0x18001c4a8  add     rcx, 1
0x18001c4ac  jz      short loc_18001C501
0x18001c4ae  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001c4b8  cmp     rcx, rax
0x18001c4bb  ja      short loc_18001C4CA
0x18001c4bd  add     rcx, rcx; Size
0x18001c4c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c4c5  test    rax, rax
0x18001c4c8  jnz     short loc_18001C501
0x18001c4ca  mov     qword ptr [rbp+88h], 0
0x18001c4d5  lea     rdx, [rbp+88h]
0x18001c4dc  lea     rcx, [rbp+38h]
0x18001c4e0  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001c4e6  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001c4ed  mov     [rbp+38h], rax
0x18001c4f1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001c4f8  lea     rcx, [rbp+38h]; pExceptionObject
0x18001c4fc  call    _CxxThrowException_0
0x18001c501  mov     [rbp+98h], rax
0x18001c508  mov     rax, 0
0x18001c512  add     rsp, 20h
0x18001c516  pop     rbp
0x18001c517  retn
```
