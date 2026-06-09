# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::String *,ulong> const *,UnBCL::Array<UnBCL::String *> *,int)

- ea: `0x180027ce0`
- end: `0x180027eb7`
- name: `?CopyToArray@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@PEAV12@UKeyTraits@42@$1?RetrieveKey@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVString@UnBCL@@K@3@PEAV?$Array@PEAVString@UnBCL@@@3@H@Z`
- size: `471`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027ac4`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800082e4`
- `0x180027ce0`
- `0x180028ed0`
- `0x180028fbc`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027db1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027e0a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027e63`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027db1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027e0a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027e63`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180027dcd`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180027dcd`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180027e7f`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180027e7f`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027e26`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027e26`

## string_xrefs

- `0x180027dc3`: `null array to Hashtable#CopyTo`
- `0x180027e1c`: `negative start index to CopyTo`
- `0x180027e75`: `array of insufficient size to CopyTo`
- `0x180027de1`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String`
- `0x180027e3a`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String`
- `0x180027e93`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String`

## pseudocode

```c
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::CopyToArray(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // edi
  __int64 (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rcx
  UnBCL::ArgumentNullException *v10; // rax
  UnBCL::Exception *v11; // rbx
  UnBCL::ArgumentOutOfRangeException *v12; // rax
  UnBCL::Exception *v13; // rbx
  UnBCL::ArgumentException *v14; // rax
  UnBCL::Exception *v15; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+48h] [rbp+28h] BYREF
  UnBCL::ArgumentNullException *v17; // [rsp+58h] [rbp+38h]

  v3 = a3;
  if ( !a2 )
  {
    v10 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v11 = v10;
    v17 = v10;
    if ( v10 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v10, L"null array to Hashtable#CopyTo");
      *(_QWORD *)v11 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v11 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<c"
                         "lass UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl"
                         " UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct U"
                         "nBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hash"
                         "table<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> "
                         "> const *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::"
                         "String *,unsigned long> *,class UnBCL::Array<class UnBCL::String *> *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v12 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v13 = v12;
    v17 = v12;
    if ( v12 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v12, L"negative start index to CopyTo");
      *(_QWORD *)v13 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v13 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<c"
                         "lass UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl"
                         " UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct U"
                         "nBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hash"
                         "table<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> "
                         "> const *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::"
                         "String *,unsigned long> *,class UnBCL::Array<class UnBCL::String *> *,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v6 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  v7 = (**v6)(v6);
  if ( (int)((**(__int64 (__fastcall ***)(__int64))a2)(a2) - v3) < v7 )
  {
    v14 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v15 = v14;
    v17 = v14;
    if ( v14 )
    {
      UnBCL::ArgumentException::ArgumentException(v14, L"array of insufficient size to CopyTo");
      *(_QWORD *)v15 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v15 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v15,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<c"
                         "lass UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl"
                         " UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct U"
                         "nBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hash"
                         "table<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> "
                         "> const *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::"
                         "String *,unsigned long> *,class UnBCL::Array<class UnBCL::String *> *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetStartPosition(*(_QWORD *)(a1 + 40));
  v9 = result;
  pExceptionObject = (UnBCL::Exception *)result;
  if ( result )
  {
    while ( 1 )
    {
      if ( !v9 )
        ATL::AtlThrowImpl(-2147467259);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, *(_QWORD *)(v9 + 8), v3);
      result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetNext(
                 *(_QWORD *)(a1 + 40),
                 &pExceptionObject);
      v9 = (__int64)pExceptionObject;
      if ( !pExceptionObject )
        break;
      ++v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027ce0  mov     [rsp-18h+arg_0], rbx
0x180027ce5  mov     [rsp-18h+arg_10], rsi
0x180027cea  push    rbp
0x180027ceb  push    rdi
0x180027cec  push    r14
0x180027cee  mov     rbp, rsp
0x180027cf1  sub     rsp, 20h
0x180027cf5  mov     edi, r8d
0x180027cf8  mov     rsi, rdx
0x180027cfb  mov     r14, rcx
0x180027cfe  test    rdx, rdx
0x180027d01  jz      loc_180027DAC
0x180027d07  test    r8d, r8d
0x180027d0a  js      loc_180027E05
0x180027d10  mov     rax, [rcx+8]
0x180027d14  movsxd  rcx, dword ptr [rax+0Ch]
0x180027d18  add     rcx, 8
0x180027d1c  add     rcx, r14
0x180027d1f  mov     rax, [rcx]
0x180027d22  mov     rax, [rax]
0x180027d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d2a  mov     ebx, eax
0x180027d2c  mov     rcx, [rsi]
0x180027d2f  mov     rax, [rcx]
0x180027d32  mov     rcx, rsi
0x180027d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d3a  sub     eax, edi
0x180027d3c  cmp     eax, ebx
0x180027d3e  jl      loc_180027E5E
0x180027d44  mov     rcx, [r14+28h]
0x180027d48  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetStartPosition(void)
0x180027d4d  mov     rcx, rax
0x180027d50  mov     [rbp+pExceptionObject], rax
0x180027d54  test    rax, rax
0x180027d57  jz      short loc_180027D8E
0x180027d59  test    rcx, rcx
0x180027d5c  jz      short loc_180027DA1
0x180027d5e  mov     rax, [rsi]
0x180027d61  mov     r8d, edi
0x180027d64  mov     rdx, [rcx+8]
0x180027d68  mov     rcx, rsi
0x180027d6b  mov     rax, [rax+28h]
0x180027d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d74  lea     rdx, [rbp+pExceptionObject]
0x180027d78  mov     rcx, [r14+28h]
0x180027d7c  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNext(__POSITION * &)
0x180027d81  mov     rcx, [rbp+pExceptionObject]
0x180027d85  test    rcx, rcx
0x180027d88  jz      short loc_180027D8E
0x180027d8a  inc     edi
0x180027d8c  jmp     short loc_180027D59
0x180027d8e  mov     rbx, [rsp+20h+arg_0]
0x180027d93  mov     rsi, [rsp+20h+arg_10]
0x180027d98  add     rsp, 20h
0x180027d9c  pop     r14
0x180027d9e  pop     rdi
0x180027d9f  pop     rbp
0x180027da0  retn
0x180027da1  mov     ecx, 80004005h; int
0x180027da6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180027dac  mov     ecx, 38h ; '8'
0x180027db1  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027db7  mov     rbx, rax
0x180027dba  mov     [rbp+arg_18], rax
0x180027dbe  test    rax, rax
0x180027dc1  jz      short loc_180027DDF
0x180027dc3  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180027dca  mov     rcx, rax
0x180027dcd  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180027dd3  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x180027dda  mov     [rbx], rax
0x180027ddd  jmp     short loc_180027DE1
0x180027ddf  xor     ebx, ebx
0x180027de1  lea     rdx, aVoidCdeclUnbcl_24; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180027de8  mov     rcx, rbx
0x180027deb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027df0  mov     [rbp+pExceptionObject], rax
0x180027df4  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180027dfb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027dff  call    _CxxThrowException_0
0x180027e05  mov     ecx, 38h ; '8'
0x180027e0a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027e10  mov     rbx, rax
0x180027e13  mov     [rbp+arg_18], rax
0x180027e17  test    rax, rax
0x180027e1a  jz      short loc_180027E38
0x180027e1c  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180027e23  mov     rcx, rax
0x180027e26  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180027e2c  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180027e33  mov     [rbx], rax
0x180027e36  jmp     short loc_180027E3A
0x180027e38  xor     ebx, ebx
0x180027e3a  lea     rdx, aVoidCdeclUnbcl_24; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180027e41  mov     rcx, rbx
0x180027e44  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027e49  mov     [rbp+pExceptionObject], rax
0x180027e4d  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180027e54  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027e58  call    _CxxThrowException_0
0x180027e5e  mov     ecx, 38h ; '8'
0x180027e63  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027e69  mov     rbx, rax
0x180027e6c  mov     [rbp+arg_18], rax
0x180027e70  test    rax, rax
0x180027e73  jz      short loc_180027E91
0x180027e75  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180027e7c  mov     rcx, rax
0x180027e7f  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180027e85  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180027e8c  mov     [rbx], rax
0x180027e8f  jmp     short loc_180027E93
0x180027e91  xor     ebx, ebx
0x180027e93  lea     rdx, aVoidCdeclUnbcl_24; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180027e9a  mov     rcx, rbx
0x180027e9d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027ea2  mov     [rbp+pExceptionObject], rax
0x180027ea6  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180027ead  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027eb1  call    _CxxThrowException_0
```
