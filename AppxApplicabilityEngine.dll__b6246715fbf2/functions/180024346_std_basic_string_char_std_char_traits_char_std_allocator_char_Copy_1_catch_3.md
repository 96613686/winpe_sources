# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$3

- ea: `0x180024346`
- end: `0x1800243c5`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$3`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180011a64`
- `0x180013294`
- `0x180019798`
- `0x180024346`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002438f`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002438f`

## pseudocode

```c
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a2 + 152) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
    {
      *(_QWORD *)(a2 + 152) = 0;
      exception::exception((exception *)(a2 + 64), (const char *const *)(a2 + 152));
      *(_QWORD *)(a2 + 64) = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)(a2 + 64);
    }
  }
  *(_QWORD *)(a2 + 168) = v4;
  return &loc_180019857;
}

```

## disassembly

```asm
0x180024346  mov     [rsp+arg_8], rdx
0x18002434b  push    rbp
0x18002434c  sub     rsp, 20h
0x180024350  mov     rbp, rdx
0x180024353  mov     rcx, [rbp+98h]
0x18002435a  mov     [rbp+98h], rcx
0x180024361  xor     eax, eax
0x180024363  add     rcx, 1; Size
0x180024367  jz      short loc_1800243B0
0x180024369  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002436d  ja      short loc_180024379
0x18002436f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024374  test    rax, rax
0x180024377  jnz     short loc_1800243B0
0x180024379  mov     qword ptr [rbp+98h], 0
0x180024384  lea     rdx, [rbp+98h]
0x18002438b  lea     rcx, [rbp+40h]
0x18002438f  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180024395  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18002439c  mov     [rbp+40h], rax
0x1800243a0  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800243a7  lea     rcx, [rbp+40h]; pExceptionObject
0x1800243ab  call    _CxxThrowException_0
0x1800243b0  mov     [rbp+0A8h], rax
0x1800243b7  lea     rax, loc_180019857
0x1800243be  add     rsp, 20h
0x1800243c2  pop     rbp
0x1800243c3  retn
```
