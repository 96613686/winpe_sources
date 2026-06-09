# _UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::QuickSort_::_1_::catch$3

- ea: `0x18005100b`
- end: `0x1800510ae`
- name: `_UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::QuickSort_::_1_::catch$3`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18005100b`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18005101f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051039`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18005101f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051039`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051058`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051058`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180051076`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180051076`

## string_xrefs

- `0x18005104e`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::QuickSort_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  UnBCL::InvalidOperationException *v3; // rbx
  UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rdi

  v3 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
  *(_QWORD *)(a2 + 160) = v3;
  if ( v3 )
  {
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v5 = v4;
    *(_QWORD *)(a2 + 144) = v4;
    if ( v4 )
    {
      UnBCL::String::String(v4, L"sort failed -- bad comparison routines?");
      *(_QWORD *)v5 = &UnBCL::String::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    UnBCL::InvalidOperationException::InvalidOperationException(v3, v5, *(struct UnBCL::Exception **)(a2 + 64));
    *(_QWORD *)v3 = &UnBCL::InvalidOperationException::`local vftable';
  }
  else
  {
    v3 = 0;
  }
  *(_QWORD *)(a2 + 48) = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v3,
                           "void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __i"
                           "nt64> *>::QuickSort(class UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *"
                           ",unsigned __int64> *> *,class UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::Stri"
                           "ng *,unsigned __int64> *> *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x18005100b  mov     [rsp+arg_8], rdx
0x180051010  push    rbx
0x180051011  push    rbp
0x180051012  push    rdi
0x180051013  sub     rsp, 30h
0x180051017  mov     rbp, rdx
0x18005101a  mov     ecx, 38h ; '8'
0x18005101f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051025  mov     rbx, rax
0x180051028  mov     [rbp+0A0h], rax
0x18005102f  test    rax, rax
0x180051032  jz      short loc_180051088
0x180051034  mov     ecx, 18h
0x180051039  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005103f  mov     rdi, rax
0x180051042  mov     [rbp+90h], rax
0x180051049  test    rax, rax
0x18005104c  jz      short loc_18005106A
0x18005104e  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180051055  mov     rcx, rax
0x180051058  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18005105e  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180051065  mov     [rdi], rax
0x180051068  jmp     short loc_18005106C
0x18005106a  xor     edi, edi
0x18005106c  mov     r8, [rbp+40h]
0x180051070  mov     rdx, rdi
0x180051073  mov     rcx, rbx
0x180051076  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x18005107c  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180051083  mov     [rbx], rax
0x180051086  jmp     short loc_18005108A
0x180051088  xor     ebx, ebx
0x18005108a  lea     rdx, aVoidCdeclUnbcl_16; "void __cdecl UnBCL::ArrayList<class UnB"...
0x180051091  mov     rcx, rbx
0x180051094  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180051099  mov     [rbp+30h], rax
0x18005109d  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x1800510a4  lea     rcx, [rbp+30h]; pExceptionObject
0x1800510a8  call    _CxxThrowException_0
```
