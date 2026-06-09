# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,ulong>,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::get_Current(void)

- ea: `0x18002e614`
- end: `0x18002e769`
- name: `?get_Current@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@V?$DictionaryEntry@PEAVString@UnBCL@@K@2@UKeyTraits@42@$1?RetrieveEntry@42@KA?AV52@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@UEBA?AV?$DictionaryEntry@PEAVString@UnBCL@@K@3@XZ`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e600`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002e614`

## import_xrefs

- `unbcl!??0Object@UnBCL@@QEAA@AEBV01@@Z` at `0x18002e68e`
- `unbcl!??0Object@UnBCL@@QEAA@AEBV01@@Z` at `0x18002e68e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e63a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e6ea`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e63a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e6ea`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e65b`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e707`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e65b`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e707`

## string_xrefs

- `0x18002e6fd`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static UnBCL::DictionaryEntry<UnBCL::String *,unsigned long> UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::get_Current(
        __int64 a1,
        __int64 a2)
{
  UnBCL::InvalidOperationException *v4; // rax
  UnBCL::Exception *v5; // rbx
  UnBCL::InvalidOperationException *v7; // rax
  UnBCL::Exception *v8; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v10; // [rsp+50h] [rbp+18h]

  if ( !*(_QWORD *)(a1 - 104) )
  {
    if ( *(_DWORD *)(a1 - 28) )
    {
      v4 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v5 = v4;
      v10 = v4;
      if ( v4 )
      {
        UnBCL::InvalidOperationException::InvalidOperationException(
          v4,
          L"Current retrieved on enumerator beyond table end");
        *(_QWORD *)v5 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v5 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v5,
                           "class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::_::HTEnumera"
                           "tor<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigne"
                           "d long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long>,struct Un"
                           "BCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL"
                           "::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::Hashtable<class UnBCL::"
                           "String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL"
                           "::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String"
                           " *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > const *,struct __POSI"
                           "TION * const &)>::get_Current(void) const");
      throw (UnBCL::InvalidOperationException **)&pExceptionObject;
    }
    v7 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v8 = v7;
    v10 = v7;
    if ( v7 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(
        v7,
        L"Current retrieved on enumerator before MoveNext()");
      *(_QWORD *)v8 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v8 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v8,
                         "class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::_::HTEnumerato"
                         "r<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned lo"
                         "ng>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long>,struct UnBCL::H"
                         "ashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::Dictio"
                         "naryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::Hashtable<class UnBCL::String *,u"
                         "nsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,u"
                         "nsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned lo"
                         "ng>::KeyTraits,class ATL::CElementTraits<unsigned long> > const *,struct __POSITION * const &)>"
                         "::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  *(_QWORD *)(a2 + 8) = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vbtable';
  UnBCL::Object::Object(
    (UnBCL::Object *)(a2 + 48),
    (const struct UnBCL::Object *)(a1 + *(int *)(*(_QWORD *)(a1 - 88) + 4LL) - 88LL));
  *(_QWORD *)a2 = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a2 + 8) + 4LL) + a2 + 8) = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>::`vftable'{for `UnBCL::Object'};
  *(_DWORD *)(*(int *)(*(_QWORD *)(a2 + 8) + 4LL) + a2 + 4) = 0;
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 - 80);
  *(_DWORD *)(a2 + 24) = *(_DWORD *)(a1 - 72);
  *(_DWORD *)(a2 + 28) = *(_DWORD *)(a1 - 68);
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a1 - 64);
  return a2;
}

```

## disassembly

```asm
0x18002e614  mov     [rsp+arg_8], rbx
0x18002e619  push    rdi
0x18002e61a  sub     rsp, 30h
0x18002e61e  mov     rbx, rdx
0x18002e621  mov     rdi, rcx
0x18002e624  cmp     qword ptr [rcx-68h], 0
0x18002e629  jnz     short loc_18002E670
0x18002e62b  cmp     dword ptr [rcx-1Ch], 0
0x18002e62f  mov     ecx, 38h ; '8'
0x18002e634  jz      loc_18002E6EA
0x18002e63a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e640  mov     rbx, rax
0x18002e643  mov     [rsp+38h+arg_10], rax
0x18002e648  test    rax, rax
0x18002e64b  jz      loc_18002E741
0x18002e651  lea     rdx, aCurrentRetriev_0; "Current retrieved on enumerator beyond "...
0x18002e658  mov     rcx, rax
0x18002e65b  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e661  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e668  mov     [rbx], rax
0x18002e66b  jmp     loc_18002E743
0x18002e670  lea     rax, ??_8?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@7B@; const UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vbtable'
0x18002e677  mov     [rdx+8], rax
0x18002e67b  mov     rax, [rcx-58h]
0x18002e67f  movsxd  rdx, dword ptr [rax+4]
0x18002e683  add     rdx, 0FFFFFFFFFFFFFFA8h
0x18002e687  add     rdx, rdi
0x18002e68a  lea     rcx, [rbx+30h]
0x18002e68e  call    cs:__imp_??0Object@UnBCL@@QEAA@AEBV01@@Z; UnBCL::Object::Object(UnBCL::Object const &)
0x18002e694  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@6B01@@; const UnBCL::DictionaryEntry<UnBCL::String *,ulong>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,ulong>'}
0x18002e69b  mov     [rbx], rax
0x18002e69e  mov     rax, [rbx+8]
0x18002e6a2  movsxd  rcx, dword ptr [rax+4]
0x18002e6a6  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@6BObject@1@@; const UnBCL::DictionaryEntry<UnBCL::String *,ulong>::`vftable'{for `UnBCL::Object'}
0x18002e6ad  mov     [rcx+rbx+8], rax
0x18002e6b2  mov     rax, [rbx+8]
0x18002e6b6  movsxd  rcx, dword ptr [rax+4]
0x18002e6ba  mov     dword ptr [rcx+rbx+4], 0
0x18002e6c2  mov     rax, [rdi-50h]
0x18002e6c6  mov     [rbx+10h], rax
0x18002e6ca  mov     eax, [rdi-48h]
0x18002e6cd  mov     [rbx+18h], eax
0x18002e6d0  mov     eax, [rdi-44h]
0x18002e6d3  mov     [rbx+1Ch], eax
0x18002e6d6  mov     eax, [rdi-40h]
0x18002e6d9  mov     [rbx+20h], eax
0x18002e6dc  mov     rax, rbx
0x18002e6df  mov     rbx, [rsp+38h+arg_8]
0x18002e6e4  add     rsp, 30h
0x18002e6e8  pop     rdi
0x18002e6e9  retn
0x18002e6ea  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e6f0  mov     rbx, rax
0x18002e6f3  mov     [rsp+38h+arg_10], rax
0x18002e6f8  test    rax, rax
0x18002e6fb  jz      short loc_18002E719
0x18002e6fd  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18002e704  mov     rcx, rax
0x18002e707  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e70d  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e714  mov     [rbx], rax
0x18002e717  jmp     short loc_18002E71B
0x18002e719  xor     ebx, ebx
0x18002e71b  lea     rdx, aClassUnbclDict_3; "class UnBCL::DictionaryEntry<class UnBC"...
0x18002e722  mov     rcx, rbx
0x18002e725  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e72a  mov     [rsp+38h+pExceptionObject], rax
0x18002e72f  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e736  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002e73b  call    _CxxThrowException_0
0x18002e741  xor     ebx, ebx
0x18002e743  lea     rdx, aClassUnbclDict_3; "class UnBCL::DictionaryEntry<class UnBC"...
0x18002e74a  mov     rcx, rbx
0x18002e74d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e752  mov     [rsp+38h+pExceptionObject], rax
0x18002e757  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e75e  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002e763  call    _CxxThrowException_0
```
