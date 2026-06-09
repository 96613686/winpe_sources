# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,ulong>,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::MoveNext(void)

- ea: `0x18002a314`
- end: `0x18002a446`
- name: `?MoveNext@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@V?$DictionaryEntry@PEAVString@UnBCL@@K@2@UKeyTraits@42@$1?RetrieveEntry@42@KA?AV52@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@UEAAHXZ`
- size: `306`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002a300`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180025888`
- `0x180028ed0`
- `0x180028fbc`
- `0x18002a314`
- `0x18002d4dc`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a3ef`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a3ef`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a40c`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a40c`
- `unbcl!??4Object@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18002a397`
- `unbcl!??4Object@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18002a397`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x18002a3c6`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x18002a3c6`

## string_xrefs

- `0x18002a402`: `MoveNext() called on invalidated enumerator`
- `0x18002a420`: `int __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::St`

## pseudocode

```c
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static UnBCL::DictionaryEntry<UnBCL::String *,unsigned long> UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::MoveNext(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 *v4; // r10
  __int64 StartPosition; // rax
  __int64 Entry; // rbx
  UnBCL::InvalidOperationException *v8; // rax
  UnBCL::Exception *v9; // rbx
  _BYTE v10[48]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v11[24]; // [rsp+50h] [rbp-18h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v13; // [rsp+78h] [rbp+10h]

  v2 = *(_QWORD *)(a1 - 112);
  if ( *(_DWORD *)(a1 - 32) != *(_DWORD *)(v2 + 48) )
  {
    v8 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v9 = v8;
    v13 = v8;
    if ( v8 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(v8, L"MoveNext() called on invalidated enumerator");
      *(_QWORD *)v9 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v9 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v9,
                         "int __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<"
                         "class UnBCL::String *,unsigned long>::TableKey,class UnBCL::DictionaryEntry<class UnBCL::String"
                         " *,unsigned long>,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&prot"
                         "ected: static class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned long> __cdecl UnBCL::"
                         "Hashtable<class UnBCL::String *,unsigned long>::RetrieveEntry(class ATL::CAtlMap<struct UnBCL::"
                         "Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<"
                         "class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > cons"
                         "t *,struct __POSITION * const &)>::MoveNext(void)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  if ( !*(_DWORD *)(a1 - 28) )
  {
    v3 = *(_QWORD *)(v2 + 40);
    if ( *(_QWORD *)(a1 - 104) )
    {
      ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetNext(
        v3,
        (__int64 *)(a1 - 104));
    }
    else
    {
      StartPosition = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetStartPosition(v3);
      *v4 = StartPosition;
    }
    if ( *v4 )
    {
      Entry = UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveEntry(
                v10,
                *(_QWORD *)(*(_QWORD *)(a1 - 112) + 40LL),
                v4);
      UnBCL::Object::operator=(
        a1 + *(int *)(*(_QWORD *)(a1 - 88) + 4LL) - 88LL,
        Entry + 8 + *(int *)(*(_QWORD *)(Entry + 8) + 4LL));
      *(_QWORD *)(a1 - 80) = *(_QWORD *)(Entry + 16);
      *(_DWORD *)(a1 - 72) = *(_DWORD *)(Entry + 24);
      *(_DWORD *)(a1 - 68) = *(_DWORD *)(Entry + 28);
      *(_DWORD *)(a1 - 64) = *(_DWORD *)(Entry + 32);
      UnBCL::DictionaryEntry<UnBCL::String *,unsigned long>::~DictionaryEntry<UnBCL::String *,unsigned long>((__int64)v11);
      UnBCL::Object::~Object((UnBCL::Object *)v11);
      return 1;
    }
    *(_DWORD *)(a1 - 28) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a314  mov     [rsp+arg_10], rbx
0x18002a319  push    rdi
0x18002a31a  sub     rsp, 60h
0x18002a31e  mov     rdi, rcx
0x18002a321  mov     rcx, [rcx-70h]
0x18002a325  mov     eax, [rcx+30h]
0x18002a328  cmp     [rdi-20h], eax
0x18002a32b  jnz     loc_18002A3EA
0x18002a331  cmp     dword ptr [rdi-1Ch], 0
0x18002a335  jnz     loc_18002A3DA
0x18002a33b  lea     r10, [rdi-68h]
0x18002a33f  mov     rcx, [rcx+28h]
0x18002a343  cmp     qword ptr [r10], 0
0x18002a347  jz      short loc_18002A353
0x18002a349  mov     rdx, r10
0x18002a34c  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNext(__POSITION * &)
0x18002a351  jmp     short loc_18002A35B
0x18002a353  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetStartPosition(void)
0x18002a358  mov     [r10], rax
0x18002a35b  cmp     qword ptr [r10], 0
0x18002a35f  jz      short loc_18002A3D3
0x18002a361  mov     rdx, [rdi-70h]
0x18002a365  mov     r8, r10
0x18002a368  mov     rdx, [rdx+28h]
0x18002a36c  lea     rcx, [rsp+68h+var_48]
0x18002a371  call    ?RetrieveEntry@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KA?AV?$DictionaryEntry@PEAVString@UnBCL@@K@2@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z; UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveEntry(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)
0x18002a376  mov     rbx, rax
0x18002a379  mov     rcx, [rax+8]
0x18002a37d  movsxd  rdx, dword ptr [rcx+4]
0x18002a381  add     rax, 8
0x18002a385  add     rdx, rax
0x18002a388  mov     rcx, [rdi-58h]
0x18002a38c  movsxd  rcx, dword ptr [rcx+4]
0x18002a390  add     rcx, 0FFFFFFFFFFFFFFA8h
0x18002a394  add     rcx, rdi
0x18002a397  call    cs:__imp_??4Object@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::Object::operator=(UnBCL::Object const &)
0x18002a39d  mov     rcx, [rbx+10h]
0x18002a3a1  mov     [rdi-50h], rcx
0x18002a3a5  mov     ecx, [rbx+18h]
0x18002a3a8  mov     [rdi-48h], ecx
0x18002a3ab  mov     ecx, [rbx+1Ch]
0x18002a3ae  mov     [rdi-44h], ecx
0x18002a3b1  mov     eax, [rbx+20h]
0x18002a3b4  mov     [rdi-40h], eax
0x18002a3b7  lea     rcx, [rsp+68h+var_18]
0x18002a3bc  call    ??1?$DictionaryEntry@PEAVString@UnBCL@@K@UnBCL@@UEAA@XZ; UnBCL::DictionaryEntry<UnBCL::String *,ulong>::~DictionaryEntry<UnBCL::String *,ulong>(void)
0x18002a3c1  lea     rcx, [rsp+68h+var_18]
0x18002a3c6  call    cs:__imp_??1Object@UnBCL@@UEAA@XZ; UnBCL::Object::~Object(void)
0x18002a3cc  mov     eax, 1
0x18002a3d1  jmp     short loc_18002A3DC
0x18002a3d3  mov     dword ptr [rdi-1Ch], 1
0x18002a3da  xor     eax, eax
0x18002a3dc  mov     rbx, [rsp+68h+arg_10]
0x18002a3e4  add     rsp, 60h
0x18002a3e8  pop     rdi
0x18002a3e9  retn
0x18002a3ea  mov     ecx, 38h ; '8'
0x18002a3ef  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002a3f5  mov     rbx, rax
0x18002a3f8  mov     [rsp+68h+arg_8], rax
0x18002a3fd  test    rax, rax
0x18002a400  jz      short loc_18002A41E
0x18002a402  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x18002a409  mov     rcx, rax
0x18002a40c  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002a412  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002a419  mov     [rbx], rax
0x18002a41c  jmp     short loc_18002A420
0x18002a41e  xor     ebx, ebx
0x18002a420  lea     rdx, aIntCdeclUnbclH_1; "int __cdecl UnBCL::_::HTEnumerator<clas"...
0x18002a427  mov     rcx, rbx
0x18002a42a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002a42f  mov     [rsp+68h+pExceptionObject], rax
0x18002a434  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002a43b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002a440  call    _CxxThrowException_0
```
