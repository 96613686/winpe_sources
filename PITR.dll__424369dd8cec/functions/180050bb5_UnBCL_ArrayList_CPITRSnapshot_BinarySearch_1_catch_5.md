# _UnBCL::ArrayList_CPITRSnapshot___::BinarySearch_::_1_::catch$5

- ea: `0x180050bb5`
- end: `0x180050c52`
- name: `_UnBCL::ArrayList_CPITRSnapshot___::BinarySearch_::_1_::catch$5`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180050bb5`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050bc9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050be0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050bc9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180050be0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180050bfc`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180050bfc`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180050c1a`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180050c1a`

## string_xrefs

- `0x180050c2e`: `int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot *,struct UnBCL::IComparer<class CPITRSnapshot *> *)`
- `0x180050bf2`: `Compare failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_CPITRSnapshot___::BinarySearch_::_1_::catch_5(__int64 a1, __int64 a2)
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
                           "int __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::BinarySearch(int,int,class CPITRSnapshot"
                           " *,struct UnBCL::IComparer<class CPITRSnapshot *> *)");
  throw (UnBCL::InvalidOperationException **)(a2 + 40);
}

```

## disassembly

```asm
0x180050bb5  mov     [rsp+arg_8], rdx
0x180050bba  push    rbx
0x180050bbb  push    rbp
0x180050bbc  push    rdi
0x180050bbd  sub     rsp, 20h
0x180050bc1  mov     rbp, rdx
0x180050bc4  mov     ecx, 38h ; '8'
0x180050bc9  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180050bcf  mov     rbx, rax
0x180050bd2  mov     [rbp+40h], rax
0x180050bd6  test    rax, rax
0x180050bd9  jz      short loc_180050C2C
0x180050bdb  mov     ecx, 18h
0x180050be0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180050be6  mov     rdi, rax
0x180050be9  mov     [rbp+48h], rax
0x180050bed  test    rax, rax
0x180050bf0  jz      short loc_180050C0E
0x180050bf2  lea     rdx, aCompareFailedB; "Compare failed -- bad comparison routin"...
0x180050bf9  mov     rcx, rax
0x180050bfc  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180050c02  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180050c09  mov     [rdi], rax
0x180050c0c  jmp     short loc_180050C10
0x180050c0e  xor     edi, edi
0x180050c10  mov     r8, [rbp+50h]
0x180050c14  mov     rdx, rdi
0x180050c17  mov     rcx, rbx
0x180050c1a  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x180050c20  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180050c27  mov     [rbx], rax
0x180050c2a  jmp     short loc_180050C2E
0x180050c2c  xor     ebx, ebx
0x180050c2e  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class CPIT"...
0x180050c35  mov     rcx, rbx
0x180050c38  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180050c3d  mov     [rbp+28h], rax
0x180050c41  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180050c48  lea     rcx, [rbp+28h]; pExceptionObject
0x180050c4c  call    _CxxThrowException_0
```
