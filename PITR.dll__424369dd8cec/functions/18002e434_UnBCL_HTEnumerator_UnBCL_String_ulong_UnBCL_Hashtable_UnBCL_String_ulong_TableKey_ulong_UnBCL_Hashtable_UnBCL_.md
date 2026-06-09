# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::get_Current(void)

- ea: `0x18002e434`
- end: `0x18002e503`
- name: `?get_Current@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@KUKeyTraits@42@$1?RetrieveValue@42@KAKPEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@UEBAKXZ`
- size: `207`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e420`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x18002e434`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e44c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e484`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e44c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002e484`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e469`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e4a1`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e469`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002e4a1`

## string_xrefs

- `0x18002e497`: `Current retrieved on enumerator before MoveNext()`

## pseudocode

```c
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::get_Current(
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
    if ( *(_DWORD *)(a1 - 32) )
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
                           "unsigned long __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL"
                           "::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashta"
                           "ble<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl "
                           "UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struc"
                           "t UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL:"
                           ":Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned"
                           " long> > const *,struct __POSITION * const &)>::get_Current(void) const");
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
                         "unsigned long __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::"
                         "Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<"
                         "class UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL:"
                         ":Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > con"
                         "st *,struct __POSITION * const &)>::get_Current(void) const");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  return *(unsigned int *)(a1 - 40);
}

```

## disassembly

```asm
0x18002e434  push    rbx
0x18002e436  sub     rsp, 20h
0x18002e43a  cmp     qword ptr [rcx-30h], 0
0x18002e43f  jnz     short loc_18002E47B
0x18002e441  cmp     dword ptr [rcx-20h], 0
0x18002e445  mov     ecx, 38h ; '8'
0x18002e44a  jz      short loc_18002E484
0x18002e44c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e452  mov     rbx, rax
0x18002e455  mov     [rsp+28h+arg_8], rax
0x18002e45a  test    rax, rax
0x18002e45d  jz      short loc_18002E4DB
0x18002e45f  lea     rdx, aCurrentRetriev_0; "Current retrieved on enumerator beyond "...
0x18002e466  mov     rcx, rax
0x18002e469  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e46f  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e476  mov     [rbx], rax
0x18002e479  jmp     short loc_18002E4DD
0x18002e47b  mov     eax, [rcx-28h]
0x18002e47e  add     rsp, 20h
0x18002e482  pop     rbx
0x18002e483  retn
0x18002e484  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e48a  mov     rbx, rax
0x18002e48d  mov     [rsp+28h+arg_8], rax
0x18002e492  test    rax, rax
0x18002e495  jz      short loc_18002E4B3
0x18002e497  lea     rdx, aCurrentRetriev; "Current retrieved on enumerator before "...
0x18002e49e  mov     rcx, rax
0x18002e4a1  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002e4a7  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002e4ae  mov     [rbx], rax
0x18002e4b1  jmp     short loc_18002E4B5
0x18002e4b3  xor     ebx, ebx
0x18002e4b5  lea     rdx, aUnsignedLongCd; "unsigned long __cdecl UnBCL::_::HTEnume"...
0x18002e4bc  mov     rcx, rbx
0x18002e4bf  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e4c4  mov     [rsp+28h+pExceptionObject], rax
0x18002e4c9  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e4d0  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e4d5  call    _CxxThrowException_0
0x18002e4db  xor     ebx, ebx
0x18002e4dd  lea     rdx, aUnsignedLongCd; "unsigned long __cdecl UnBCL::_::HTEnume"...
0x18002e4e4  mov     rcx, rbx
0x18002e4e7  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e4ec  mov     [rsp+28h+pExceptionObject], rax
0x18002e4f1  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002e4f8  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002e4fd  call    _CxxThrowException_0
```
