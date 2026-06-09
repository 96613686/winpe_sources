# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::MoveNext(void)

- ea: `0x18002a154`
- end: `0x18002a213`
- name: `?MoveNext@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@KUKeyTraits@42@$1?RetrieveValue@42@KAKPEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@UEAAHXZ`
- size: `191`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a140`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180028ed0`
- `0x180028fbc`
- `0x18002a154`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a1bc`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a1bc`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a1d9`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a1d9`

## string_xrefs

- `0x18002a1cf`: `MoveNext() called on invalidated enumerator`
- `0x18002a1ed`: `int __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned lon`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static unsigned long UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::MoveNext(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // r10
  __int64 v5; // r11
  __int64 StartPosition; // rax
  UnBCL::InvalidOperationException *v8; // rax
  UnBCL::Exception *v9; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  UnBCL::InvalidOperationException *v11; // [rsp+38h] [rbp+10h]

  v2 = *(_QWORD *)(a1 - 56);
  if ( *(_DWORD *)(a1 - 36) != *(_DWORD *)(v2 + 48) )
  {
    v8 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
    v9 = v8;
    v11 = v8;
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
                         "class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBC"
                         "L::String *,unsigned long>::KeyTraits,&protected: static unsigned long __cdecl UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::RetrieveValue(class ATL::CAtlMap<struct UnBCL::Hashtable"
                         "<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnB"
                         "CL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> > const *,struc"
                         "t __POSITION * const &)>::MoveNext(void)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  if ( !*(_DWORD *)(a1 - 32) )
  {
    v3 = *(_QWORD *)(v2 + 40);
    if ( *(_QWORD *)(a1 - 48) )
    {
      ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetNext(
        v3,
        (__int64 *)(a1 - 48));
    }
    else
    {
      StartPosition = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetStartPosition(v3);
      *(_QWORD *)v5 = StartPosition;
    }
    if ( *(_QWORD *)v5 )
    {
      *(_DWORD *)(v4 - 40) = *(_DWORD *)(*(_QWORD *)v5 + 16LL);
      return 1;
    }
    *(_DWORD *)(v4 - 32) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a154  push    rbx
0x18002a156  sub     rsp, 20h
0x18002a15a  mov     r10, rcx
0x18002a15d  mov     rcx, [rcx-38h]
0x18002a161  mov     eax, [rcx+30h]
0x18002a164  cmp     [r10-24h], eax
0x18002a168  jnz     short loc_18002A1B7
0x18002a16a  cmp     dword ptr [r10-20h], 0
0x18002a16f  jnz     short loc_18002A1AF
0x18002a171  lea     r11, [r10-30h]
0x18002a175  mov     rcx, [rcx+28h]
0x18002a179  cmp     qword ptr [r11], 0
0x18002a17d  jz      short loc_18002A189
0x18002a17f  mov     rdx, r11
0x18002a182  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNext(__POSITION * &)
0x18002a187  jmp     short loc_18002A191
0x18002a189  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetStartPosition(void)
0x18002a18e  mov     [r11], rax
0x18002a191  mov     rax, [r11]
0x18002a194  test    rax, rax
0x18002a197  jz      short loc_18002A1A7
0x18002a199  mov     eax, [rax+10h]
0x18002a19c  mov     [r10-28h], eax
0x18002a1a0  mov     eax, 1
0x18002a1a5  jmp     short loc_18002A1B1
0x18002a1a7  mov     dword ptr [r10-20h], 1
0x18002a1af  xor     eax, eax
0x18002a1b1  add     rsp, 20h
0x18002a1b5  pop     rbx
0x18002a1b6  retn
0x18002a1b7  mov     ecx, 38h ; '8'
0x18002a1bc  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002a1c2  mov     rbx, rax
0x18002a1c5  mov     [rsp+28h+arg_8], rax
0x18002a1ca  test    rax, rax
0x18002a1cd  jz      short loc_18002A1EB
0x18002a1cf  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x18002a1d6  mov     rcx, rax
0x18002a1d9  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002a1df  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002a1e6  mov     [rbx], rax
0x18002a1e9  jmp     short loc_18002A1ED
0x18002a1eb  xor     ebx, ebx
0x18002a1ed  lea     rdx, aIntCdeclUnbclH_2; "int __cdecl UnBCL::_::HTEnumerator<clas"...
0x18002a1f4  mov     rcx, rbx
0x18002a1f7  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002a1fc  mov     [rsp+28h+pExceptionObject], rax
0x18002a201  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002a208  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002a20d  call    _CxxThrowException_0
```
