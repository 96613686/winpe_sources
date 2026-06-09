# _UnBCL::ArrayList_CFileObject___::QuickSort_::_1_::catch$3

- ea: `0x180051f9c`
- end: `0x18005203f`
- name: `_UnBCL::ArrayList_CFileObject___::QuickSort_::_1_::catch$3`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180051f9c`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051fb0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051fca`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051fb0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180051fca`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051fe9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180051fe9`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180052007`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z` at `0x180052007`

## string_xrefs

- `0x180051fdf`: `sort failed -- bad comparison routines?`

## pseudocode

```c
void __fastcall __noreturn UnBCL::ArrayList_CFileObject___::QuickSort_::_1_::catch_3(__int64 a1, __int64 a2)
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
                           "void __cdecl UnBCL::ArrayList<class CFileObject *>::QuickSort(class UnBCL::ArrayList<class CF"
                           "ileObject *> *,class UnBCL::ArrayList<class CFileObject *> *,int,int)");
  throw (UnBCL::InvalidOperationException **)(a2 + 48);
}

```

## disassembly

```asm
0x180051f9c  mov     [rsp+arg_8], rdx
0x180051fa1  push    rbx
0x180051fa2  push    rbp
0x180051fa3  push    rdi
0x180051fa4  sub     rsp, 30h
0x180051fa8  mov     rbp, rdx
0x180051fab  mov     ecx, 38h ; '8'
0x180051fb0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051fb6  mov     rbx, rax
0x180051fb9  mov     [rbp+0A0h], rax
0x180051fc0  test    rax, rax
0x180051fc3  jz      short loc_180052019
0x180051fc5  mov     ecx, 18h
0x180051fca  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180051fd0  mov     rdi, rax
0x180051fd3  mov     [rbp+90h], rax
0x180051fda  test    rax, rax
0x180051fdd  jz      short loc_180051FFB
0x180051fdf  lea     rdx, aSortFailedBadC; "sort failed -- bad comparison routines?"
0x180051fe6  mov     rcx, rax
0x180051fe9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180051fef  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180051ff6  mov     [rdi], rax
0x180051ff9  jmp     short loc_180051FFD
0x180051ffb  xor     edi, edi
0x180051ffd  mov     r8, [rbp+40h]
0x180052001  mov     rdx, rdi
0x180052004  mov     rcx, rbx
0x180052007  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBVString@1@PEAVException@1@@Z; UnBCL::InvalidOperationException::InvalidOperationException(UnBCL::String const *,UnBCL::Exception *)
0x18005200d  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x180052014  mov     [rbx], rax
0x180052017  jmp     short loc_18005201B
0x180052019  xor     ebx, ebx
0x18005201b  lea     rdx, aVoidCdeclUnbcl_21; "void __cdecl UnBCL::ArrayList<class CFi"...
0x180052022  mov     rcx, rbx
0x180052025  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18005202a  mov     [rbp+30h], rax
0x18005202e  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x180052035  lea     rcx, [rbp+30h]; pExceptionObject
0x180052039  call    _CxxThrowException_0
```
