# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,ulong>,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::CopyToArray(UnBCL::Hashtable<UnBCL::String *,ulong> const *,UnBCL::Array<UnBCL::DictionaryEntry<UnBCL::String *,ulong>> *,int)

- ea: `0x180027ec0`
- end: `0x180028144`
- name: `?CopyToArray@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@V?$DictionaryEntry@PEAVString@UnBCL@@K@2@UKeyTraits@42@$1?RetrieveEntry@42@KA?AV52@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@SAXPEBV?$Hashtable@PEAVString@UnBCL@@K@3@PEAV?$Array@V?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@@3@H@Z`
- size: `644`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180027a94`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180025888`
- `0x180027ec0`
- `0x180028ed0`
- `0x180028fbc`
- `0x18002d4dc`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `unbcl!??0Object@UnBCL@@QEAA@AEBV01@@Z` at `0x180027f89`
- `unbcl!??0Object@UnBCL@@QEAA@AEBV01@@Z` at `0x180027f89`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002803e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180028097`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800280f0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002803e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180028097`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800280f0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800280b3`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800280b3`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18002805a`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18002805a`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18002810c`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18002810c`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180028005`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180028005`

## string_xrefs

- `0x18002806e`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::S`
- `0x1800280c7`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::S`
- `0x180028120`: `void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::S`
- `0x1800280a9`: `null array to Hashtable#CopyTo`
- `0x180028102`: `negative start index to CopyTo`
- `0x180028050`: `array of insufficient size to CopyTo`

## pseudocode

```c
void __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static UnBCL::DictionaryEntry<UnBCL::String *,unsigned long> UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::CopyToArray(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v3; // r15d
  __int64 (__fastcall ***v6)(_QWORD); // rcx
  signed int v7; // ebx
  void (__fastcall *v8)(__int64, void ***, _QWORD); // rdi
  unsigned int v9; // ebx
  UnBCL::ArgumentException *v10; // rax
  UnBCL::Exception *v11; // rbx
  UnBCL::ArgumentNullException *v12; // rax
  UnBCL::Exception *v13; // rbx
  UnBCL::ArgumentOutOfRangeException *v14; // rax
  UnBCL::Exception *v15; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+20h] [rbp-69h] BYREF
  UnBCL::ArgumentNullException *v17; // [rsp+28h] [rbp-61h]
  void **v18; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-51h]
  int v20; // [rsp+48h] [rbp-41h]
  int v21; // [rsp+4Ch] [rbp-3Dh]
  int v22; // [rsp+50h] [rbp-39h]
  char v23[16]; // [rsp+60h] [rbp-29h] BYREF
  char v24[8]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v25[2]; // [rsp+78h] [rbp-11h] BYREF
  int v26; // [rsp+88h] [rbp-1h]
  int v27; // [rsp+8Ch] [rbp+3h]
  int v28; // [rsp+90h] [rbp+7h]
  _BYTE v29[16]; // [rsp+A0h] [rbp+17h] BYREF

  v3 = a3;
  if ( !a2 )
  {
    v12 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v13 = v12;
    v17 = v12;
    if ( v12 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v12, L"null array to Hashtable#CopyTo");
      *(_QWORD *)v13 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v13 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::Strin"
                         "g *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&pro"
                         "tected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > con"
                         "st *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::Strin"
                         "g *,unsigned long> *,class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsi"
                         "gned long> > *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v14 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v15 = v14;
    v17 = v14;
    if ( v14 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v14, L"negative start index to CopyTo");
      *(_QWORD *)v15 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v15 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v15,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::Strin"
                         "g *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&pro"
                         "tected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > con"
                         "st *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::Strin"
                         "g *,unsigned long> *,class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsi"
                         "gned long> > *,int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v6 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  v7 = (**v6)(v6);
  if ( (int)((**(__int64 (__fastcall ***)(__int64))a2)(a2) - v3) < v7 )
  {
    v10 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v11 = v10;
    v17 = v10;
    if ( v10 )
    {
      UnBCL::ArgumentException::ArgumentException(v10, L"array of insufficient size to CopyTo");
      *(_QWORD *)v11 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v11 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::Strin"
                         "g *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&pro"
                         "tected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > con"
                         "st *,struct __POSITION * const &)>::CopyToArray(const class UnBCL::Hashtable<class UnBCL::Strin"
                         "g *,unsigned long> *,class UnBCL::Array<class UnBCL::DictionaryEntry<class UnBCL::String *,unsi"
                         "gned long> > *,int)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  pExceptionObject = (UnBCL::Exception *)ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetStartPosition(*(_QWORD *)(a1 + 40));
  while ( pExceptionObject )
  {
    UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveEntry(v24, *(_QWORD *)(a1 + 40), &pExceptionObject);
    v8 = *(void (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)a2 + 40LL);
    v9 = v3++;
    v19[0] = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vbtable';
    UnBCL::Object::Object((UnBCL::Object *)v23, (const struct UnBCL::Object *)((char *)v25 + *(int *)(v25[0] + 4LL)));
    v18 = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>'};
    *(_QWORD *)((char *)v19 + *(int *)(v19[0] + 4LL)) = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>::`vftable'{for `UnBCL::Object'};
    *(_DWORD *)((char *)&v18 + *(int *)(v19[0] + 4LL) + 4) = 0;
    v19[1] = v25[1];
    v20 = v26;
    v21 = v27;
    v22 = v28;
    v8(a2, &v18, v9);
    ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetNext(
      *(_QWORD *)(a1 + 40),
      &pExceptionObject);
    UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>::~DictionaryEntry<UnBCL::String *,unsigned long>((__int64)v29);
    UnBCL::Object::~Object((UnBCL::Object *)v29);
  }
}

```

## disassembly

```asm
0x180027ec0  mov     [rsp-8+arg_18], rbx
0x180027ec5  push    rbp
0x180027ec6  push    rsi
0x180027ec7  push    rdi
0x180027ec8  push    r14
0x180027eca  push    r15
0x180027ecc  lea     rbp, [rsp-37h]
0x180027ed1  sub     rsp, 0C0h
0x180027ed8  mov     rax, cs:__security_cookie
0x180027edf  xor     rax, rsp
0x180027ee2  mov     [rbp+57h+var_30], rax
0x180027ee6  mov     r15d, r8d
0x180027ee9  mov     r14, rdx
0x180027eec  mov     rsi, rcx
0x180027eef  test    rdx, rdx
0x180027ef2  jz      loc_180028092
0x180027ef8  test    r8d, r8d
0x180027efb  js      loc_1800280EB
0x180027f01  mov     rax, [rcx+8]
0x180027f05  movsxd  rcx, dword ptr [rax+0Ch]
0x180027f09  add     rcx, 8
0x180027f0d  add     rcx, rsi
0x180027f10  mov     rax, [rcx]
0x180027f13  mov     rax, [rax]
0x180027f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f1b  mov     ebx, eax
0x180027f1d  mov     rcx, [r14]
0x180027f20  mov     rax, [rcx]
0x180027f23  mov     rcx, r14
0x180027f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f2b  sub     eax, r15d
0x180027f2e  cmp     eax, ebx
0x180027f30  jl      loc_180028039
0x180027f36  mov     rcx, [rsi+28h]
0x180027f3a  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetStartPosition(void)
0x180027f3f  mov     [rbp+57h+pExceptionObject], rax
0x180027f43  test    rax, rax
0x180027f46  jz      loc_180028016
0x180027f4c  lea     r8, [rbp+57h+pExceptionObject]
0x180027f50  mov     rdx, [rsi+28h]
0x180027f54  lea     rcx, [rbp+57h+var_70]
0x180027f58  call    ?RetrieveEntry@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KA?AV?$DictionaryEntry@PEAVString@UnBCL@@K@2@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z; UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)
0x180027f5d  nop
0x180027f5e  mov     rax, [r14]
0x180027f61  mov     rdi, [rax+28h]
0x180027f65  mov     ebx, r15d
0x180027f68  inc     r15d
0x180027f6b  lea     rax, ??_8?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@7B@; const UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vbtable'
0x180027f72  mov     [rbp+57h+var_A8], rax
0x180027f76  mov     rax, [rbp+57h+var_68]
0x180027f7a  movsxd  rcx, dword ptr [rax+4]
0x180027f7e  lea     rdx, [rbp+57h+var_68]
0x180027f82  add     rdx, rcx
0x180027f85  lea     rcx, [rbp+57h+var_80]
0x180027f89  call    cs:__imp_??0Object@UnBCL@@QEAA@AEBV01@@Z; UnBCL::Object::Object(UnBCL::Object const &)
0x180027f8f  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@6B01@@; const UnBCL::DictionaryEntry<UnBCL::String *,ulong>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,ulong>'}
0x180027f96  mov     [rbp+57h+var_B0], rax
0x180027f9a  mov     rax, [rbp+57h+var_A8]
0x180027f9e  movsxd  rcx, dword ptr [rax+4]
0x180027fa2  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@6BObject@1@@; const UnBCL::DictionaryEntry<UnBCL::String *,ulong>::`vftable'{for `UnBCL::Object'}
0x180027fa9  mov     [rbp+rcx+57h+var_A8], rax
0x180027fae  mov     rax, [rbp+57h+var_A8]
0x180027fb2  movsxd  rcx, dword ptr [rax+4]
0x180027fb6  mov     dword ptr [rbp+rcx+57h+var_B0+4], 0
0x180027fbe  mov     rcx, [rbp+57h+var_60]
0x180027fc2  mov     [rbp+57h+var_A0], rcx
0x180027fc6  mov     ecx, [rbp+57h+var_58]
0x180027fc9  mov     [rbp+57h+var_98], ecx
0x180027fcc  mov     ecx, [rbp+57h+var_54]
0x180027fcf  mov     [rbp+57h+var_94], ecx
0x180027fd2  mov     ecx, [rbp+57h+var_50]
0x180027fd5  mov     [rbp+57h+var_90], ecx
0x180027fd8  mov     r8d, ebx
0x180027fdb  lea     rdx, [rbp+57h+var_B0]
0x180027fdf  mov     rcx, r14
0x180027fe2  mov     rax, rdi
0x180027fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fea  lea     rdx, [rbp+57h+pExceptionObject]
0x180027fee  mov     rcx, [rsi+28h]
0x180027ff2  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNext(__POSITION * &)
0x180027ff7  nop
0x180027ff8  lea     rcx, [rbp+57h+var_40]
0x180027ffc  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,ulong>::~DictionaryEntry<UnBCL::String *,ulong>(void)
0x180028001  lea     rcx, [rbp+57h+var_40]
0x180028005  call    cs:__imp_??1Object@UnBCL@@UEAA@XZ; UnBCL::Object::~Object(void)
0x18002800b  cmp     [rbp+57h+pExceptionObject], 0
0x180028010  jnz     loc_180027F4C
0x180028016  mov     rcx, [rbp+57h+var_30]
0x18002801a  xor     rcx, rsp; StackCookie
0x18002801d  call    __security_check_cookie
0x180028022  mov     rbx, [rsp+0E0h+arg_18]
0x18002802a  add     rsp, 0C0h
0x180028031  pop     r15
0x180028033  pop     r14
0x180028035  pop     rdi
0x180028036  pop     rsi
0x180028037  pop     rbp
0x180028038  retn
0x180028039  mov     ecx, 38h ; '8'
0x18002803e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180028044  mov     rbx, rax
0x180028047  mov     [rbp+57h+var_B8], rax
0x18002804b  test    rax, rax
0x18002804e  jz      short loc_18002806C
0x180028050  lea     rdx, aArrayOfInsuffi; "array of insufficient size to CopyTo"
0x180028057  mov     rcx, rax
0x18002805a  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180028060  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x180028067  mov     [rbx], rax
0x18002806a  jmp     short loc_18002806E
0x18002806c  xor     ebx, ebx
0x18002806e  lea     rdx, aVoidCdeclUnbcl_1; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180028075  mov     rcx, rbx
0x180028078  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002807d  mov     [rbp+57h+pExceptionObject], rax
0x180028081  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180028088  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002808c  call    _CxxThrowException_0
0x180028092  mov     ecx, 38h ; '8'
0x180028097  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002809d  mov     rbx, rax
0x1800280a0  mov     [rbp+57h+var_B8], rax
0x1800280a4  test    rax, rax
0x1800280a7  jz      short loc_1800280C5
0x1800280a9  lea     rdx, aNullArrayToHas; "null array to Hashtable#CopyTo"
0x1800280b0  mov     rcx, rax
0x1800280b3  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1800280b9  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x1800280c0  mov     [rbx], rax
0x1800280c3  jmp     short loc_1800280C7
0x1800280c5  xor     ebx, ebx
0x1800280c7  lea     rdx, aVoidCdeclUnbcl_1; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x1800280ce  mov     rcx, rbx
0x1800280d1  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800280d6  mov     [rbp+57h+pExceptionObject], rax
0x1800280da  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1800280e1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800280e5  call    _CxxThrowException_0
0x1800280eb  mov     ecx, 38h ; '8'
0x1800280f0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800280f6  mov     rbx, rax
0x1800280f9  mov     [rbp+57h+var_B8], rax
0x1800280fd  test    rax, rax
0x180028100  jz      short loc_18002811E
0x180028102  lea     rdx, aNegativeStartI; "negative start index to CopyTo"
0x180028109  mov     rcx, rax
0x18002810c  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180028112  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180028119  mov     [rbx], rax
0x18002811c  jmp     short loc_180028120
0x18002811e  xor     ebx, ebx
0x180028120  lea     rdx, aVoidCdeclUnbcl_1; "void __cdecl UnBCL::_::HTEnumerator<cla"...
0x180028127  mov     rcx, rbx
0x18002812a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002812f  mov     [rbp+57h+pExceptionObject], rax
0x180028133  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18002813a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002813e  call    _CxxThrowException_0
```
