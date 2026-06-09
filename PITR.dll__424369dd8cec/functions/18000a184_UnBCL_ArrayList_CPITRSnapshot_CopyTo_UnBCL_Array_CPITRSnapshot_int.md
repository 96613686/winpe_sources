# UnBCL::ArrayList<CPITRSnapshot *>::CopyTo(UnBCL::Array<CPITRSnapshot *> *,int)

- ea: `0x18000a184`
- end: `0x18000a3b3`
- name: `?CopyTo@?$ArrayList@PEAVCPITRSnapshot@@@UnBCL@@UEBAXPEAV?$Array@PEAVCPITRSnapshot@@@2@H@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a170`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18000a184`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a2a4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a300`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a35c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a2a4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a300`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000a35c`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000a31d`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18000a31d`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000a379`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000a379`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000a2c1`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000a2c1`

## string_xrefs

- `0x18000a2d5`: `void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::CopyTo(class UnBCL::Array<class CPITRSnapshot *> *,int) const`
- `0x18000a331`: `void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::CopyTo(class UnBCL::Array<class CPITRSnapshot *> *,int) const`
- `0x18000a38d`: `void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::CopyTo(class UnBCL::Array<class CPITRSnapshot *> *,int) const`
- `0x18000a313`: `null array argument to ArrayList#CopyTo`
- `0x18000a2b7`: `index out of range to ArrayList#CopyTo`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<CPITRSnapshot *>::CopyTo(__int64 a1, __int64 a2, int a3)
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
                         "void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::CopyTo(class UnBCL::Array<class CPITRSnap"
                         "shot *> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::CopyTo(class UnBCL::Array<class CPITRSnap"
                         "shot *> *,int) const");
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
                         "void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::CopyTo(class UnBCL::Array<class CPITRSnap"
                         "shot *> *,int) const");
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
0x18000a184  mov     [rsp+arg_0], rbx
0x18000a189  mov     [rsp+arg_10], rsi
0x18000a18e  push    rdi
0x18000a18f  push    r14
0x18000a191  push    r15
0x18000a193  sub     rsp, 20h
0x18000a197  mov     esi, r8d
0x18000a19a  mov     r14, rdx
0x18000a19d  mov     rdi, rcx
0x18000a1a0  test    rdx, rdx
0x18000a1a3  jz      loc_18000A2FB
0x18000a1a9  test    r8d, r8d
0x18000a1ac  js      loc_18000A29F
0x18000a1b2  mov     rax, [rcx-50h]
0x18000a1b6  movsxd  rcx, dword ptr [rax+0Ch]
0x18000a1ba  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000a1be  add     rcx, rdi
0x18000a1c1  mov     rax, [rcx]
0x18000a1c4  mov     rax, [rax]
0x18000a1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1cc  mov     ecx, 7FFFFFFFh
0x18000a1d1  sub     ecx, esi
0x18000a1d3  cmp     ecx, eax
0x18000a1d5  jl      loc_18000A29F
0x18000a1db  mov     rax, [r14]
0x18000a1de  mov     rcx, r14
0x18000a1e1  mov     rax, [rax]
0x18000a1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e9  mov     ebx, eax
0x18000a1eb  mov     rcx, [rdi-50h]
0x18000a1ef  movsxd  rcx, dword ptr [rcx+0Ch]
0x18000a1f3  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000a1f7  add     rcx, rdi
0x18000a1fa  mov     rdx, [rcx]
0x18000a1fd  mov     rax, [rdx]
0x18000a200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a205  add     eax, esi
0x18000a207  cmp     eax, ebx
0x18000a209  jg      loc_18000A357
0x18000a20f  mov     rax, [rdi-50h]
0x18000a213  movsxd  rcx, dword ptr [rax+0Ch]
0x18000a217  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000a21b  add     rcx, rdi
0x18000a21e  mov     rax, [rcx]
0x18000a221  mov     rax, [rax]
0x18000a224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a229  test    eax, eax
0x18000a22b  jz      short loc_18000A28B
0x18000a22d  lea     rcx, [rdi-58h]
0x18000a231  mov     rax, [rcx]
0x18000a234  xor     edx, edx
0x18000a236  mov     rax, [rax+68h]
0x18000a23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a23f  mov     r15, rax
0x18000a242  mov     rcx, [r14]
0x18000a245  mov     rax, [rcx+38h]
0x18000a249  xor     edx, edx
0x18000a24b  mov     rcx, r14
0x18000a24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a253  mov     r14, rax
0x18000a256  xor     ebx, ebx
0x18000a258  mov     rcx, [rdi-50h]
0x18000a25c  movsxd  rcx, dword ptr [rcx+0Ch]
0x18000a260  add     rcx, 0FFFFFFFFFFFFFFB0h
0x18000a264  add     rcx, rdi
0x18000a267  mov     rdx, [rcx]
0x18000a26a  mov     rax, [rdx]
0x18000a26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a272  cmp     ebx, eax
0x18000a274  jge     short loc_18000A28B
0x18000a276  movsxd  rdx, ebx
0x18000a279  lea     eax, [rbx+rsi]
0x18000a27c  movsxd  rcx, eax
0x18000a27f  mov     rax, [r15+rdx*8]
0x18000a283  mov     [r14+rcx*8], rax
0x18000a287  inc     ebx
0x18000a289  jmp     short loc_18000A258
0x18000a28b  mov     rbx, [rsp+38h+arg_0]
0x18000a290  mov     rsi, [rsp+38h+arg_10]
0x18000a295  add     rsp, 20h
0x18000a299  pop     r15
0x18000a29b  pop     r14
0x18000a29d  pop     rdi
0x18000a29e  retn
0x18000a29f  mov     ecx, 38h ; '8'
0x18000a2a4  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a2aa  mov     rbx, rax
0x18000a2ad  mov     [rsp+38h+arg_18], rax
0x18000a2b2  test    rax, rax
0x18000a2b5  jz      short loc_18000A2D3
0x18000a2b7  lea     rdx, aIndexOutOfRang; "index out of range to ArrayList#CopyTo"
0x18000a2be  mov     rcx, rax
0x18000a2c1  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000a2c7  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18000a2ce  mov     [rbx], rax
0x18000a2d1  jmp     short loc_18000A2D5
0x18000a2d3  xor     ebx, ebx
0x18000a2d5  lea     rdx, aVoidCdeclUnbcl_49; "void __cdecl UnBCL::ArrayList<class CPI"...
0x18000a2dc  mov     rcx, rbx
0x18000a2df  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000a2e4  mov     [rsp+38h+pExceptionObject], rax
0x18000a2e9  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18000a2f0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000a2f5  call    _CxxThrowException_0
0x18000a2fb  mov     ecx, 38h ; '8'
0x18000a300  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a306  mov     rbx, rax
0x18000a309  mov     [rsp+38h+arg_18], rax
0x18000a30e  test    rax, rax
0x18000a311  jz      short loc_18000A32F
0x18000a313  lea     rdx, aNullArrayArgum; "null array argument to ArrayList#CopyTo"
0x18000a31a  mov     rcx, rax
0x18000a31d  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18000a323  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18000a32a  mov     [rbx], rax
0x18000a32d  jmp     short loc_18000A331
0x18000a32f  xor     ebx, ebx
0x18000a331  lea     rdx, aVoidCdeclUnbcl_49; "void __cdecl UnBCL::ArrayList<class CPI"...
0x18000a338  mov     rcx, rbx
0x18000a33b  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000a340  mov     [rsp+38h+pExceptionObject], rax
0x18000a345  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18000a34c  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000a351  call    _CxxThrowException_0
0x18000a357  mov     ecx, 38h ; '8'
0x18000a35c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000a362  mov     rbx, rax
0x18000a365  mov     [rsp+38h+arg_18], rax
0x18000a36a  test    rax, rax
0x18000a36d  jz      short loc_18000A38B
0x18000a36f  lea     rdx, aInsufficientSp; "insufficient space available in target "...
0x18000a376  mov     rcx, rax
0x18000a379  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18000a37f  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x18000a386  mov     [rbx], rax
0x18000a389  jmp     short loc_18000A38D
0x18000a38b  xor     ebx, ebx
0x18000a38d  lea     rdx, aVoidCdeclUnbcl_49; "void __cdecl UnBCL::ArrayList<class CPI"...
0x18000a394  mov     rcx, rbx
0x18000a397  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18000a39c  mov     [rsp+38h+pExceptionObject], rax
0x18000a3a1  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18000a3a8  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000a3ad  call    _CxxThrowException_0
```
