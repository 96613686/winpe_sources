# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::String *,ulong> const *,UnBCL::Array<ulong> *,int)

- ea: `0x180027b04`
- end: `0x180027cda`
- name: `?CopyToArray@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@KUKeyTraits@42@$1?RetrieveValue@42@KAKPEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVString@UnBCL@@K@3@PEAV?$Array@K@3@H@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027af4`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800082e4`
- `0x180027b04`
- `0x180028ed0`
- `0x180028fbc`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027bd4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027c2d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027c86`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027bd4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027c2d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180027c86`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180027bf0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180027bf0`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180027ca2`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x180027ca2`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027c49`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180027c49`

## string_xrefs

- `0x180027be6`: `null array to Hashtable#CopyTo`
- `0x180027c3f`: `negative start index to CopyTo`
- `0x180027c98`: `array of insufficient size to CopyTo`
- `0x180027c04`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned lo`
- `0x180027c5d`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned lo`
- `0x180027cb6`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned lo`

## pseudocode

```c
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::CopyToArray(
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
                         "<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnB"
                         "CL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtabl"
                         "e<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtabl"
                         "e<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class Un"
                         "BCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > const *,stru"
                         "ct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,unsig"
                         "ned long> *,class UnBCL::Array<unsigned long> *,int)");
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
                         "<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnB"
                         "CL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtabl"
                         "e<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtabl"
                         "e<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class Un"
                         "BCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > const *,stru"
                         "ct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,unsig"
                         "ned long> *,class UnBCL::Array<unsigned long> *,int)");
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
                         "<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnB"
                         "CL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtabl"
                         "e<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtabl"
                         "e<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class Un"
                         "BCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > const *,stru"
                         "ct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::String *,unsig"
                         "ned long> *,class UnBCL::Array<unsigned long> *,int)");
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
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, *(unsigned int *)(v9 + 16), v3);
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
0x180027b04  mov     [rsp-18h+arg_0], rbx
0x180027b09  mov     [rsp-18h+arg_10], rsi
0x180027b0e  push    rbp
0x180027b0f  push    rdi
0x180027b10  push    r14
0x180027b12  mov     rbp, rsp
0x180027b15  sub     rsp, 20h
0x180027b19  mov     edi, r8d
0x180027b1c  mov     rsi, rdx
0x180027b1f  mov     r14, rcx
0x180027b22  test    rdx, rdx
0x180027b25  jz      loc_180027BCF
0x180027b2b  test    r8d, r8d
0x180027b2e  js      loc_180027C28
0x180027b34  mov     rax, [rcx+8]
0x180027b38  movsxd  rcx, dword ptr [rax+0Ch]
0x180027b3c  add     rcx, 8
0x180027b40  add     rcx, r14
0x180027b43  mov     rax, [rcx]
0x180027b46  mov     rax, [rax]
0x180027b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b4e  mov     ebx, eax
0x180027b50  mov     rcx, [rsi]
0x180027b53  mov     rax, [rcx]
0x180027b56  mov     rcx, rsi
0x180027b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b5e  sub     eax, edi
0x180027b60  cmp     eax, ebx
0x180027b62  jl      loc_180027C81
0x180027b68  mov     rcx, [r14+28h]
0x180027b6c  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetStartPosition(void)
0x180027b71  mov     rcx, rax
0x180027b74  mov     [rbp+pExceptionObject], rax
0x180027b78  test    rax, rax
0x180027b7b  jz      short loc_180027BB1
0x180027b7d  test    rcx, rcx
0x180027b80  jz      short loc_180027BC4
0x180027b82  mov     rax, [rsi]
0x180027b85  mov     r8d, edi
0x180027b88  mov     edx, [rcx+10h]
0x180027b8b  mov     rcx, rsi
0x180027b8e  mov     rax, [rax+28h]
0x180027b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b97  lea     rdx, [rbp+pExceptionObject]
0x180027b9b  mov     rcx, [r14+28h]
0x180027b9f  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNext(__POSITION * &)
0x180027ba4  mov     rcx, [rbp+pExceptionObject]
0x180027ba8  test    rcx, rcx
0x180027bab  jz      short loc_180027BB1
0x180027bad  inc     edi
0x180027baf  jmp     short loc_180027B7D
0x180027bb1  mov     rbx, [rsp+20h+arg_0]
0x180027bb6  mov     rsi, [rsp+20h+arg_10]
0x180027bbb  add     rsp, 20h
0x180027bbf  pop     r14
0x180027bc1  pop     rdi
0x180027bc2  pop     rbp
0x180027bc3  retn
0x180027bc4  mov     ecx, 80004005h; int
0x180027bc9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180027bcf  mov     ecx, 38h ; '8'
0x180027bd4  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027bda  mov     rbx, rax
0x180027bdd  mov     [rbp+arg_18], rax
0x180027be1  test    rax, rax
0x180027be4  jz      short loc_180027C02
0x180027be6  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x180027bed  mov     rcx, rax
0x180027bf0  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180027bf6  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x180027bfd  mov     [rbx], rax
0x180027c00  jmp     short loc_180027C04
0x180027c02  xor     ebx, ebx
0x180027c04  lea     rdx, aVoidCdeclUnbcl_43; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180027c0b  mov     rcx, rbx
0x180027c0e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027c13  mov     [rbp+pExceptionObject], rax
0x180027c17  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180027c1e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027c22  call    _CxxThrowException_0
0x180027c28  mov     ecx, 38h ; '8'
0x180027c2d  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027c33  mov     rbx, rax
0x180027c36  mov     [rbp+arg_18], rax
0x180027c3a  test    rax, rax
0x180027c3d  jz      short loc_180027C5B
0x180027c3f  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180027c46  mov     rcx, rax
0x180027c49  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180027c4f  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180027c56  mov     [rbx], rax
0x180027c59  jmp     short loc_180027C5D
0x180027c5b  xor     ebx, ebx
0x180027c5d  lea     rdx, aVoidCdeclUnbcl_43; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180027c64  mov     rcx, rbx
0x180027c67  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027c6c  mov     [rbp+pExceptionObject], rax
0x180027c70  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180027c77  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027c7b  call    _CxxThrowException_0
0x180027c81  mov     ecx, 38h ; '8'
0x180027c86  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180027c8c  mov     rbx, rax
0x180027c8f  mov     [rbp+arg_18], rax
0x180027c93  test    rax, rax
0x180027c96  jz      short loc_180027CB4
0x180027c98  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180027c9f  mov     rcx, rax
0x180027ca2  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180027ca8  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180027caf  mov     [rbx], rax
0x180027cb2  jmp     short loc_180027CB6
0x180027cb4  xor     ebx, ebx
0x180027cb6  lea     rdx, aVoidCdeclUnbcl_43; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180027cbd  mov     rcx, rbx
0x180027cc0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180027cc5  mov     [rbp+pExceptionObject], rax
0x180027cc9  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180027cd0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027cd4  call    _CxxThrowException_0
```
