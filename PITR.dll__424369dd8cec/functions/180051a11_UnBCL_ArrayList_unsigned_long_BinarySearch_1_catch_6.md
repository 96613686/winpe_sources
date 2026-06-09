# _UnBCL::ArrayList_unsigned_long_::BinarySearch_::_1_::catch$6

- ea: `0x180051a11`
- end: `0x180051a78`
- name: `_UnBCL::ArrayList_unsigned_long_::BinarySearch_::_1_::catch$6`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180051a11`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051a24`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051a24`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180051a40`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x180051a40`

## string_xrefs

- `0x180051a36`: `sort failed -- bad comparison routines?`
- `0x180051a54`: `int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL::IComparer<unsigned long> *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_unsigned_long_::BinarySearch_::_1_::catch_6(__int64 a1, __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rax
  UnBCL::Exception *v4; // rbx

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  v4 = v3;
  *(_QWORD *)(a2 + 72) = v3;
  if ( v3 )
  {
    UnBCL::InvalidOperationException::InvalidOperationException(v3, L"sort failed -- bad comparison routines?");
    *(_QWORD *)v4 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a2 + 48) = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v4,
                           "int __cdecl UnBCL::ArrayList<unsigned long>::BinarySearch(int,int,unsigned long,struct UnBCL:"
                           ":IComparer<unsigned long> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180051a11  mov     [rsp+arg_8], rdx
0x180051a16  push    rbx
0x180051a17  push    rbp
0x180051a18  sub     rsp, 28h
0x180051a1c  mov     rbp, rdx
0x180051a1f  mov     ecx, 38h ; '8'
0x180051a24  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051a2a  mov     rbx, rax
0x180051a2d  mov     [rbp+48h], rax
0x180051a31  test    rax, rax
0x180051a34  jz      short loc_180051A52
0x180051a36  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180051a3d  mov     rcx, rax
0x180051a40  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x180051a46  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180051a4d  mov     [rbx], rax
0x180051a50  jmp     short loc_180051A54
0x180051a52  xor     ebx, ebx
0x180051a54  lea     rdx, aIntCdeclUnbclA_16; "int __cdecl UnBCL::ArrayList<unsigned l"...
0x180051a5b  mov     rcx, rbx
0x180051a5e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180051a63  mov     [rbp+30h], rax
0x180051a67  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180051a6e  lea     rcx, [rbp+30h]; pExceptionObject
0x180051a72  call    _CxxThrowException_0
```
