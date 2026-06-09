# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$3

- ea: `0x180022e00`
- end: `0x180022e92`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$3`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011a64`
- `0x180013294`
- `0x180022e00`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180022e69`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180022e69`

## pseudocode

```c
void *__fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rax
  unsigned __int64 v4; // rcx
  __int64 v6; // rcx

  v6 = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a2 + 152) = v6;
  v3 = 0;
  v4 = v6 + 1;
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFFFFFFFFFFLL || (v3 = operator new(2 * v4)) == 0 )
    {
      *(_QWORD *)(a2 + 152) = 0;
      exception::exception((exception *)(a2 + 64), (const char *const *)(a2 + 152));
      *(_QWORD *)(a2 + 64) = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)(a2 + 64);
    }
  }
  *(_QWORD *)(a2 + 168) = v3;
  return &loc_180004FCD;
}

```

## disassembly

```asm
0x180022e00  mov     [rsp+arg_8], rdx
0x180022e05  push    rbp
0x180022e06  sub     rsp, 20h
0x180022e0a  mov     rbp, rdx
0x180022e0d  jmp     short loc_180022E43
0x180022e0f  xor     eax, eax
0x180022e11  add     rcx, 1
0x180022e15  jz      short loc_180022E33
0x180022e17  mov     rax, 7FFFFFFFFFFFFFFFh
0x180022e21  cmp     rcx, rax
0x180022e24  ja      short loc_180022E53
0x180022e26  add     rcx, rcx; Size
0x180022e29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022e2e  test    rax, rax
0x180022e31  jz      short loc_180022E53
0x180022e33  mov     [rbp+0A8h], rax
0x180022e3a  lea     rax, loc_180004FCD
0x180022e41  jmp     short loc_180022E8B
0x180022e43  mov     rcx, [rbp+98h]
0x180022e4a  mov     [rbp+98h], rcx
0x180022e51  jmp     short loc_180022E0F
0x180022e53  mov     qword ptr [rbp+98h], 0
0x180022e5e  lea     rdx, [rbp+98h]
0x180022e65  lea     rcx, [rbp+40h]
0x180022e69  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180022e6f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180022e76  mov     [rbp+40h], rax
0x180022e7a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180022e81  lea     rcx, [rbp+40h]; pExceptionObject
0x180022e85  call    _CxxThrowException_0
0x180022e8b  add     rsp, 20h
0x180022e8f  pop     rbp
0x180022e90  retn; const std::bad_alloc::`vftable'
```
