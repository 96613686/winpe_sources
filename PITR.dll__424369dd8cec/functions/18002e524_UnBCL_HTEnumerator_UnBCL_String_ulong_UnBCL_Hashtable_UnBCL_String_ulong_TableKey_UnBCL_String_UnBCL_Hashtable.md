# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::get_Current(void)

- ea: `0x18002e524`
- end: `0x18002e5f4`
- name: `?get_Current@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@PEAV12@UKeyTraits@42@$1?RetrieveKey@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@UEBAPEAVString@3@XZ`
- size: `208`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e510`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002e524`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e53c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e575`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e53c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e575`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e559`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e592`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e559`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e592`

## string_xrefs

- `0x18002e588`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::get_Current(
        __int64 a1)
{
  UnBCL::InvalidOperationException *v1; // rax
  UnBCL::Exception *v2; // rbx
  UnBCL::InvalidOperationException *v4; // rax
  UnBCL::Exception *v5; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v7; // [rsp+38h] [rbp+10h]

  if ( !*(_QWORD *)(a1 - 48) )
  {
    if ( *(_DWORD *)(a1 - 28) )
    {
      v1 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v2 = v1;
      v7 = v1;
      if ( v1 )
      {
        UnBCL::InvalidOperationException::InvalidOperationException(
          v1,
          L"Current retrieved on enumerator beyond table end");
        *(_QWORD *)v2 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v2 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v2,
                           "class UnBCL::String *__cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struc"
                           "t UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struc"
                           "t UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class U"
                           "nBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(cla"
                           "ss ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsign"
                           "ed long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CE"
                           "lementTraits<unsigned long> > const *,struct __POSITION * const &)>::get_Current(void) const");
      throw (UnBCL::InvalidOperationException **)&pExceptionObject;
    }
    v4 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v5 = v4;
    v7 = v4;
    if ( v4 )
    {
      UnBCL::InvalidOperationException::InvalidOperationException(
        v4,
        L"Current retrieved on enumerator before MoveNext()");
      *(_QWORD *)v5 = &UnBCL::InvalidOperationException::`local vftable';
    }
    else
    {
      v5 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v5,
                         "class UnBCL::String *__cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct "
                         "UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct Un"
                         "BCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::"
                         "String * __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::"
                         "CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,st"
                         "ruct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits"
                         "<unsigned long> > const *,struct __POSITION * const &)>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(_QWORD *)(a1 - 40);
}

```

## disassembly

```asm
0x18002e524  push    rbx
0x18002e526  sub     rsp, 20h
0x18002e52a  cmp     qword ptr [rcx-30h], 0
0x18002e52f  jnz     short loc_18002E56B
0x18002e531  cmp     dword ptr [rcx-1Ch], 0
0x18002e535  mov     ecx, 38h ; '8'
0x18002e53a  jz      short loc_18002E575
0x18002e53c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e542  mov     rbx, rax
0x18002e545  mov     [rsp+28h+arg_8], rax
0x18002e54a  test    rax, rax
0x18002e54d  jz      short loc_18002E5CC
0x18002e54f  lea     rdx, aCurrentRetriev_0; "Current retrieved on enumerator beyond "...
0x18002e556  mov     rcx, rax
0x18002e559  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e55f  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e566  mov     [rbx], rax
0x18002e569  jmp     short loc_18002E5CE
0x18002e56b  mov     rax, [rcx-28h]
0x18002e56f  add     rsp, 20h
0x18002e573  pop     rbx
0x18002e574  retn
0x18002e575  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e57b  mov     rbx, rax
0x18002e57e  mov     [rsp+28h+arg_8], rax
0x18002e583  test    rax, rax
0x18002e586  jz      short loc_18002E5A4
0x18002e588  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18002e58f  mov     rcx, rax
0x18002e592  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e598  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e59f  mov     [rbx], rax
0x18002e5a2  jmp     short loc_18002E5A6
0x18002e5a4  xor     ebx, ebx
0x18002e5a6  lea     rdx, aClassUnbclStri; "class UnBCL::String *__cdecl UnBCL::_::"...
0x18002e5ad  mov     rcx, rbx
0x18002e5b0  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e5b5  mov     [rsp+28h+pExceptionObject], rax
0x18002e5ba  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e5c1  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e5c6  call    _CxxThrowException_0
0x18002e5cc  xor     ebx, ebx
0x18002e5ce  lea     rdx, aClassUnbclStri; "class UnBCL::String *__cdecl UnBCL::_::"...
0x18002e5d5  mov     rcx, rbx
0x18002e5d8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e5dd  mov     [rsp+28h+pExceptionObject], rax
0x18002e5e2  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e5e9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e5ee  call    _CxxThrowException_0
```
