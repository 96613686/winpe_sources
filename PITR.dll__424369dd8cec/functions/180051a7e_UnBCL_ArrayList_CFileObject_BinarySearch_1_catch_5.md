# _UnBCL::ArrayList_CFileObject___::BinarySearch_::_1_::catch$5

- ea: `0x180051a7e`
- end: `0x180051b1b`
- name: `_UnBCL::ArrayList_CFileObject___::BinarySearch_::_1_::catch$5`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180051a7e`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051a92`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051aa9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051a92`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051aa9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051ac5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051ac5`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180051ae3`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180051ae3`

## string_xrefs

- `0x180051abb`: `Compare failed -- bad comparison routines?`
- `0x180051af7`: `int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,struct UnBCL::IComparer<class CFileObject *> *)`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_CFileObject___::BinarySearch_::_1_::catch_5(__int64 a1, __int64 a2)
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
                           "int __cdecl UnBCL::ArrayList<class CFileObject *>::BinarySearch(int,int,class CFileObject *,s"
                           "truct UnBCL::IComparer<class CFileObject *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 40);
}

```

## disassembly

```asm
0x180051a7e  mov     [rsp+arg_8], rdx
0x180051a83  push    rbx
0x180051a84  push    rbp
0x180051a85  push    rdi
0x180051a86  sub     rsp, 20h
0x180051a8a  mov     rbp, rdx
0x180051a8d  mov     ecx, 38h ; '8'
0x180051a92  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051a98  mov     rbx, rax
0x180051a9b  mov     [rbp+40h], rax
0x180051a9f  test    rax, rax
0x180051aa2  jz      short loc_180051AF5
0x180051aa4  mov     ecx, 18h
0x180051aa9  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051aaf  mov     rdi, rax
0x180051ab2  mov     [rbp+48h], rax
0x180051ab6  test    rax, rax
0x180051ab9  jz      short loc_180051AD7
0x180051abb  lea     rdx, aCompareFailedB; "Compare failed -- bad comparison routin"...
0x180051ac2  mov     rcx, rax
0x180051ac5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180051acb  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180051ad2  mov     [rdi], rax
0x180051ad5  jmp     short loc_180051AD9
0x180051ad7  xor     edi, edi
0x180051ad9  mov     r8, [rbp+50h]
0x180051add  mov     rdx, rdi
0x180051ae0  mov     rcx, rbx
0x180051ae3  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x180051ae9  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180051af0  mov     [rbx], rax
0x180051af3  jmp     short loc_180051AF7
0x180051af5  xor     ebx, ebx
0x180051af7  lea     rdx, aIntCdeclUnbclA_4; "int __cdecl UnBCL::ArrayList<class CFil"...
0x180051afe  mov     rcx, rbx
0x180051b01  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180051b06  mov     [rbp+28h], rax
0x180051b0a  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180051b11  lea     rcx, [rbp+28h]; pExceptionObject
0x180051b15  call    _CxxThrowException_0
```
