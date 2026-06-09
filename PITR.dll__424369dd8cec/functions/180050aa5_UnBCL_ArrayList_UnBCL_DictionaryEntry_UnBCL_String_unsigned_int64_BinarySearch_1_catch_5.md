# _UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::BinarySearch_::_1_::catch$5

- ea: `0x180050aa5`
- end: `0x180050b42`
- name: `_UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::BinarySearch_::_1_::catch$5`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180050aa5`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050ab9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050ad0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050ab9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050ad0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180050aec`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180050aec`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180050b0a`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180050b0a`

## string_xrefs

- `0x180050ae2`: `Compare failed -- bad comparison routines?`
- `0x180050b1e`: `int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_UnBCL::DictionaryEntry_UnBCL::String___unsigned___int64____::BinarySearch_::_1_::catch_5(
        __int64 a1,
        __int64 a2)
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
                           "int __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __in"
                           "t64> *>::BinarySearch(int,int,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __i"
                           "nt64> *,struct UnBCL::IComparer<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 40);
}

```

## disassembly

```asm
0x180050aa5  mov     [rsp+arg_8], rdx
0x180050aaa  push    rbx
0x180050aab  push    rbp
0x180050aac  push    rdi
0x180050aad  sub     rsp, 20h
0x180050ab1  mov     rbp, rdx
0x180050ab4  mov     ecx, 38h ; '8'
0x180050ab9  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180050abf  mov     rbx, rax
0x180050ac2  mov     [rbp+40h], rax
0x180050ac6  test    rax, rax
0x180050ac9  jz      short loc_180050B1C
0x180050acb  mov     ecx, 18h
0x180050ad0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180050ad6  mov     rdi, rax
0x180050ad9  mov     [rbp+48h], rax
0x180050add  test    rax, rax
0x180050ae0  jz      short loc_180050AFE
0x180050ae2  lea     rdx, aCompareFailedB; "Compare failed -- bad comparison routin"...
0x180050ae9  mov     rcx, rax
0x180050aec  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180050af2  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180050af9  mov     [rdi], rax
0x180050afc  jmp     short loc_180050B00
0x180050afe  xor     edi, edi
0x180050b00  mov     r8, [rbp+50h]
0x180050b04  mov     rdx, rdi
0x180050b07  mov     rcx, rbx
0x180050b0a  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x180050b10  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180050b17  mov     [rbx], rax
0x180050b1a  jmp     short loc_180050B1E
0x180050b1c  xor     ebx, ebx
0x180050b1e  lea     rdx, aIntCdeclUnbclA_17; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x180050b25  mov     rcx, rbx
0x180050b28  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180050b2d  mov     [rbp+28h], rax
0x180050b31  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180050b38  lea     rcx, [rbp+28h]; pExceptionObject
0x180050b3c  call    _CxxThrowException_0
```
