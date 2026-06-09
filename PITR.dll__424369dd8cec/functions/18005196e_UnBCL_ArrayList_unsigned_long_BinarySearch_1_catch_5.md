# _UnBCL::ArrayList_unsigned_long_::BinarySearch_::_1_::catch$5

- ea: `0x18005196e`
- end: `0x180051a0b`
- name: `_UnBCL::ArrayList_unsigned_long_::BinarySearch_::_1_::catch$5`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18005196e`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051982`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051999`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051982`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051999`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800519b5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800519b5`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x1800519d3`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x1800519d3`

## string_xrefs

- `0x1800519ab`: `Compare failed -- bad comparison routines?`
- `0x1800519e7`: `int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_unsigned_long_::BinarySearch_::_1_::catch_5(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 64) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 72) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"Compare failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 80));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 40) = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v3,
                           "int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL:"
                           ":IComparer<unsigned long> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 40);
}

```

## disassembly

```asm
0x18005196e  mov     [rsp+arg_8], rdx
0x180051973  push    rbx
0x180051974  push    rbp
0x180051975  push    rdi
0x180051976  sub     rsp, 20h
0x18005197a  mov     rbp, rdx
0x18005197d  mov     ecx, 38h ; '8'
0x180051982  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051988  mov     rbx, rax
0x18005198b  mov     [rbp+40h], rax
0x18005198f  test    rax, rax
0x180051992  jz      short loc_1800519E5
0x180051994  mov     ecx, 18h
0x180051999  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005199f  mov     rdi, rax
0x1800519a2  mov     [rbp+48h], rax
0x1800519a6  test    rax, rax
0x1800519a9  jz      short loc_1800519C7
0x1800519ab  lea     rdx, aCompareFailedB; "Compare failed -- bad comparison routin"...
0x1800519b2  mov     rcx, rax
0x1800519b5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800519bb  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x1800519c2  mov     [rdi], rax
0x1800519c5  jmp     short loc_1800519C9
0x1800519c7  xor     edi, edi
0x1800519c9  mov     r8, [rbp+50h]
0x1800519cd  mov     rdx, rdi
0x1800519d0  mov     rcx, rbx
0x1800519d3  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x1800519d9  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x1800519e0  mov     [rbx], rax
0x1800519e3  jmp     short loc_1800519E7
0x1800519e5  xor     ebx, ebx
0x1800519e7  lea     rdx, aIntCdeclUnbclA_16; "int __cdecl UnBCL::ArrayList<unsigned l"...
0x1800519ee  mov     rcx, rbx
0x1800519f1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800519f6  mov     [rbp+28h], rax
0x1800519fa  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180051a01  lea     rcx, [rbp+28h]; pExceptionObject
0x180051a05  call    _CxxThrowException_0
```
