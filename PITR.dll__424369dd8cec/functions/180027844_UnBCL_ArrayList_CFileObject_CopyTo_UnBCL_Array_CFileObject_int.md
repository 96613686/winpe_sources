# UnBCL::ArrayList<CFileObject *>::CopyTo(UnBCL::Array<CFileObject *> *,int)

- ea: `0x180027844`
- end: `0x180027a73`
- name: `?CopyTo@?$ArrayList@PEAVCFileObject@@@UnBCL@@UEBAXPEAV?$Array@PEAVCFileObject@@@2@H@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027830`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180027844`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027964`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800279c0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027a1c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027964`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800279c0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027a1c`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800279dd`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800279dd`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180027a39`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180027a39`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027981`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027981`

## string_xrefs

- `0x1800279d3`: `null array argument to ArrayList#CopyTo`
- `0x180027977`: `index out of range to ArrayList#CopyTo`
- `0x180027995`: `void __cdecl UnBCL::ArrayList<class CFileObject *>::CopyTo(class UnBCL::Array<class CFileObject *> *,int) const`
- `0x1800279f1`: `void __cdecl UnBCL::ArrayList<class CFileObject *>::CopyTo(class UnBCL::Array<class CFileObject *> *,int) const`
- `0x180027a4d`: `void __cdecl UnBCL::ArrayList<class CFileObject *>::CopyTo(class UnBCL::Array<class CFileObject *> *,int) const`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<CFileObject *>::CopyTo(__int64 a1, __int64 a2, int a3)
{
  int (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  __int64 (__fastcall ***v9)(_QWORD); // rcx
  __int64 result; // rax
  __int64 v11; // r15
  __int64 v12; // r14
  int i; // ebx
  __int64 (__fastcall ***v14)(_QWORD); // rcx
  UnBCL::ArgumentOutOfRangeException *v15; // rax
  UnBCL::Exception *v16; // rbx
  UnBCL::ArgumentNullException *v17; // rax
  UnBCL::Exception *v18; // rbx
  UnBCL::ArgumentException *v19; // rax
  UnBCL::Exception *v20; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  UnBCL::ArgumentNullException *v22; // [rsp+58h] [rbp+20h]

  if ( !a2 )
  {
    v17 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v18 = v17;
    v22 = v17;
    if ( v17 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v17, L"null array argument to ArrayList#CopyTo");
      *(_QWORD *)v18 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v18 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "void __cdecl UnBCL::ArrayList<class CFileObject *>::CopyTo(class UnBCL::Array<class CFileObject"
                         " *> *,int) const");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0
    || (v6 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL),
        0x7FFFFFFF - a3 < (**v6)(v6)) )
  {
    v15 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v16 = v15;
    v22 = v15;
    if ( v15 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v15, L"index out of range to ArrayList#CopyTo");
      *(_QWORD *)v16 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v16 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "void __cdecl UnBCL::ArrayList<class CFileObject *>::CopyTo(class UnBCL::Array<class CFileObject"
                         " *> *,int) const");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v7 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
  v8 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
  if ( (int)(a3 + (**v8)(v8)) > v7 )
  {
    v19 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v20 = v19;
    v22 = v19;
    if ( v19 )
    {
      UnBCL::ArgumentException::ArgumentException(v19, L"insufficient space available in target array");
      *(_QWORD *)v20 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v20 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v20,
                         "void __cdecl UnBCL::ArrayList<class CFileObject *>::CopyTo(class UnBCL::Array<class CFileObject"
                         " *> *,int) const");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
  result = (**v9)(v9);
  if ( (_DWORD)result )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 - 88) + 104LL))(a1 - 88, 0);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 56LL))(a2, 0);
    for ( i = 0; ; ++i )
    {
      v14 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 80) + 12LL) - 80LL);
      result = (**v14)(v14);
      if ( i >= (int)result )
        break;
      *(_QWORD *)(v12 + 8LL * (i + a3)) = *(_QWORD *)(v11 + 8LL * i);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027844  mov     [rsp+arg_0], rbx
0x180027849  mov     [rsp+arg_10], rsi
0x18002784e  push    rdi
0x18002784f  push    r14
0x180027851  push    r15
0x180027853  sub     rsp, 20h
0x180027857  mov     esi, r8d
0x18002785a  mov     r14, rdx
0x18002785d  mov     rdi, rcx
0x180027860  test    rdx, rdx
0x180027863  jz      loc_1800279BB
0x180027869  test    r8d, r8d
0x18002786c  js      loc_18002795F
0x180027872  mov     rax, [rcx-50h]
0x180027876  movsxd  rcx, dword ptr [rax+0Ch]
0x18002787a  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18002787e  add     rcx, rdi
0x180027881  mov     rax, [rcx]
0x180027884  mov     rax, [rax]
0x180027887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002788c  mov     ecx, 7FFFFFFFh
0x180027891  sub     ecx, esi
0x180027893  cmp     ecx, eax
0x180027895  jl      loc_18002795F
0x18002789b  mov     rax, [r14]
0x18002789e  mov     rcx, r14
0x1800278a1  mov     rax, [rax]
0x1800278a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278a9  mov     ebx, eax
0x1800278ab  mov     rcx, [rdi-50h]
0x1800278af  movsxd  rcx, dword ptr [rcx+0Ch]
0x1800278b3  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800278b7  add     rcx, rdi
0x1800278ba  mov     rdx, [rcx]
0x1800278bd  mov     rax, [rdx]
0x1800278c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278c5  add     eax, esi
0x1800278c7  cmp     eax, ebx
0x1800278c9  jg      loc_180027A17
0x1800278cf  mov     rax, [rdi-50h]
0x1800278d3  movsxd  rcx, dword ptr [rax+0Ch]
0x1800278d7  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800278db  add     rcx, rdi
0x1800278de  mov     rax, [rcx]
0x1800278e1  mov     rax, [rax]
0x1800278e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e9  test    eax, eax
0x1800278eb  jz      short loc_18002794B
0x1800278ed  lea     rcx, [rdi-58h]
0x1800278f1  mov     rax, [rcx]
0x1800278f4  xor     edx, edx
0x1800278f6  mov     rax, [rax+68h]
0x1800278fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278ff  mov     r15, rax
0x180027902  mov     rcx, [r14]
0x180027905  mov     rax, [rcx+38h]
0x180027909  xor     edx, edx
0x18002790b  mov     rcx, r14
0x18002790e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027913  mov     r14, rax
0x180027916  xor     ebx, ebx
0x180027918  mov     rcx, [rdi-50h]
0x18002791c  movsxd  rcx, dword ptr [rcx+0Ch]
0x180027920  add     rcx, 0FFFFFFFFFFFFFFB0h
0x180027924  add     rcx, rdi
0x180027927  mov     rdx, [rcx]
0x18002792a  mov     rax, [rdx]
0x18002792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027932  cmp     ebx, eax
0x180027934  jge     short loc_18002794B
0x180027936  movsxd  rdx, ebx
0x180027939  lea     eax, [rbx+rsi]
0x18002793c  movsxd  rcx, eax
0x18002793f  mov     rax, [r15+rdx*8]
0x180027943  mov     [r14+rcx*8], rax
0x180027947  inc     ebx
0x180027949  jmp     short loc_180027918
0x18002794b  mov     rbx, [rsp+38h+arg_0]
0x180027950  mov     rsi, [rsp+38h+arg_10]
0x180027955  add     rsp, 20h
0x180027959  pop     r15
0x18002795b  pop     r14
0x18002795d  pop     rdi
0x18002795e  retn
0x18002795f  mov     ecx, 38h ; '8'
0x180027964  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002796a  mov     rbx, rax
0x18002796d  mov     [rsp+38h+arg_18], rax
0x180027972  test    rax, rax
0x180027975  jz      short loc_180027993
0x180027977  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x18002797e  mov     rcx, rax
0x180027981  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180027987  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18002798e  mov     [rbx], rax
0x180027991  jmp     short loc_180027995
0x180027993  xor     ebx, ebx
0x180027995  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::ArrayList<class CFi"...
0x18002799c  mov     rcx, rbx
0x18002799f  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800279a4  mov     [rsp+38h+pExceptionObject], rax
0x1800279a9  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800279b0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800279b5  call    _CxxThrowException_0
0x1800279bb  mov     ecx, 38h ; '8'
0x1800279c0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800279c6  mov     rbx, rax
0x1800279c9  mov     [rsp+38h+arg_18], rax
0x1800279ce  test    rax, rax
0x1800279d1  jz      short loc_1800279EF
0x1800279d3  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x1800279da  mov     rcx, rax
0x1800279dd  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1800279e3  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x1800279ea  mov     [rbx], rax
0x1800279ed  jmp     short loc_1800279F1
0x1800279ef  xor     ebx, ebx
0x1800279f1  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::ArrayList<class CFi"...
0x1800279f8  mov     rcx, rbx
0x1800279fb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027a00  mov     [rsp+38h+pExceptionObject], rax
0x180027a05  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180027a0c  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180027a11  call    _CxxThrowException_0
0x180027a17  mov     ecx, 38h ; '8'
0x180027a1c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027a22  mov     rbx, rax
0x180027a25  mov     [rsp+38h+arg_18], rax
0x180027a2a  test    rax, rax
0x180027a2d  jz      short loc_180027A4B
0x180027a2f  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x180027a36  mov     rcx, rax
0x180027a39  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180027a3f  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180027a46  mov     [rbx], rax
0x180027a49  jmp     short loc_180027A4D
0x180027a4b  xor     ebx, ebx
0x180027a4d  lea     rdx, aVoidCdeclUnbcl_23; "void __cdecl UnBCL::ArrayList<class CFi"...
0x180027a54  mov     rcx, rbx
0x180027a57  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027a5c  mov     [rsp+38h+pExceptionObject], rax
0x180027a61  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180027a68  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180027a6d  call    _CxxThrowException_0
```
