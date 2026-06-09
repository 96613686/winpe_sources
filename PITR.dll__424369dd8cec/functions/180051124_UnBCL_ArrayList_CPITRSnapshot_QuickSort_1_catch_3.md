# _UnBCL::ArrayList_CPITRSnapshot___::QuickSort_::_1_::catch$3

- ea: `0x180051124`
- end: `0x1800511c7`
- name: `_UnBCL::ArrayList_CPITRSnapshot___::QuickSort_::_1_::catch$3`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180051124`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051138`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051152`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051138`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051152`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051171`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051171`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x18005118f`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x18005118f`

## string_xrefs

- `0x180051167`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_CPITRSnapshot___::QuickSort_::_1_::catch_3(__int64 a1, __int64 a2)
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
                           "void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::QuickSort(class UnBCL::ArrayList<class "
                           "CPITRSnapshot *> *,class UnBCL::ArrayList<class CPITRSnapshot *> *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180051124  mov     [rsp+arg_8], rdx
0x180051129  push    rbx
0x18005112a  push    rbp
0x18005112b  push    rdi
0x18005112c  sub     rsp, 30h
0x180051130  mov     rbp, rdx
0x180051133  mov     ecx, 38h ; '8'
0x180051138  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18005113e  mov     rbx, rax
0x180051141  mov     [rbp+0A0h], rax
0x180051148  test    rax, rax
0x18005114b  jz      short loc_1800511A1
0x18005114d  mov     ecx, 18h
0x180051152  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051158  mov     rdi, rax
0x18005115b  mov     [rbp+90h], rax
0x180051162  test    rax, rax
0x180051165  jz      short loc_180051183
0x180051167  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x18005116e  mov     rcx, rax
0x180051171  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180051177  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18005117e  mov     [rdi], rax
0x180051181  jmp     short loc_180051185
0x180051183  xor     edi, edi
0x180051185  mov     r8, [rbp+40h]
0x180051189  mov     rdx, rdi
0x18005118c  mov     rcx, rbx
0x18005118f  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x180051195  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18005119c  mov     [rbx], rax
0x18005119f  jmp     short loc_1800511A3
0x1800511a1  xor     ebx, ebx
0x1800511a3  lea     rdx, aVoidCdeclUnbcl_39; "void __cdecl UnBCL::ArrayList<class CPI"...
0x1800511aa  mov     rcx, rbx
0x1800511ad  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800511b2  mov     [rbp+30h], rax
0x1800511b6  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x1800511bd  lea     rcx, [rbp+30h]; pExceptionObject
0x1800511c1  call    _CxxThrowException_0
```
