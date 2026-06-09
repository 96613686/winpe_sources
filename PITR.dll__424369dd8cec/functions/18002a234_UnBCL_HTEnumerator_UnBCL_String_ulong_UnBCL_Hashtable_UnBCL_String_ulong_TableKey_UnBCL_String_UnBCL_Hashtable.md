# UnBCL::_::HTEnumerator<UnBCL::String *,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,ulong>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>> const *,__POSITION * const &)>::MoveNext(void)

- ea: `0x18002a234`
- end: `0x18002a2f4`
- name: `?MoveNext@?$HTEnumerator@PEAVString@UnBCL@@KUTableKey@?$Hashtable@PEAVString@UnBCL@@K@2@PEAV12@UKeyTraits@42@$1?RetrieveKey@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@UEAAHXZ`
- size: `192`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a220`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180028ed0`
- `0x180028fbc`
- `0x18002a234`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a29d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a29d`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a2ba`
- `unbcl!??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z` at `0x18002a2ba`

## string_xrefs

- `0x18002a2b0`: `MoveNext() called on invalidated enumerator`
- `0x18002a2ce`: `int __cdecl UnBCL::_::HTEnumerator<class UnBCL::String *,unsigned long,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct UnBCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hashtable<class UnBCL::String `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnBCL::_::HTEnumerator<UnBCL::String *,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,unsigned long>::RetrieveKey(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>> const *,__POSITION * const &)>::MoveNext(
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
  if ( *(_DWORD *)(a1 - 32) != *(_DWORD *)(v2 + 48) )
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
                         "class UnBCL::String *,unsigned long>::TableKey,class UnBCL::String *,struct UnBCL::Hashtable<cl"
                         "ass UnBCL::String *,unsigned long>::KeyTraits,&protected: static class UnBCL::String * __cdecl "
                         "UnBCL::Hashtable<class UnBCL::String *,unsigned long>::RetrieveKey(class ATL::CAtlMap<struct Un"
                         "BCL::Hashtable<class UnBCL::String *,unsigned long>::TableKey,unsigned long,struct UnBCL::Hasht"
                         "able<class UnBCL::String *,unsigned long>::KeyTraits,class ATL::CElementTraits<unsigned long> >"
                         " const *,struct __POSITION * const &)>::MoveNext(void)");
    throw (UnBCL::InvalidOperationException **)&pExceptionObject;
  }
  if ( !*(_DWORD *)(a1 - 28) )
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
      *(_QWORD *)(v4 - 40) = *(_QWORD *)(*(_QWORD *)v5 + 8LL);
      return 1;
    }
    *(_DWORD *)(v4 - 28) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a234  push    rbx
0x18002a236  sub     rsp, 20h
0x18002a23a  mov     r10, rcx
0x18002a23d  mov     rcx, [rcx-38h]
0x18002a241  mov     eax, [rcx+30h]
0x18002a244  cmp     [r10-20h], eax
0x18002a248  jnz     short loc_18002A298
0x18002a24a  cmp     dword ptr [r10-1Ch], 0
0x18002a24f  jnz     short loc_18002A290
0x18002a251  lea     r11, [r10-30h]
0x18002a255  mov     rcx, [rcx+28h]
0x18002a259  cmp     qword ptr [r11], 0
0x18002a25d  jz      short loc_18002A269
0x18002a25f  mov     rdx, r11
0x18002a262  call    ?GetNext@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNext(__POSITION * &)
0x18002a267  jmp     short loc_18002A271
0x18002a269  call    ?GetStartPosition@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetStartPosition(void)
0x18002a26e  mov     [r11], rax
0x18002a271  mov     rax, [r11]
0x18002a274  test    rax, rax
0x18002a277  jz      short loc_18002A288
0x18002a279  mov     rax, [rax+8]
0x18002a27d  mov     [r10-28h], rax
0x18002a281  mov     eax, 1
0x18002a286  jmp     short loc_18002A292
0x18002a288  mov     dword ptr [r10-1Ch], 1
0x18002a290  xor     eax, eax
0x18002a292  add     rsp, 20h
0x18002a296  pop     rbx
0x18002a297  retn
0x18002a298  mov     ecx, 38h ; '8'
0x18002a29d  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002a2a3  mov     rbx, rax
0x18002a2a6  mov     [rsp+28h+arg_8], rax
0x18002a2ab  test    rax, rax
0x18002a2ae  jz      short loc_18002A2CC
0x18002a2b0  lea     rdx, aMovenextCalled; "MoveNext() called on invalidated enumer"...
0x18002a2b7  mov     rcx, rax
0x18002a2ba  call    cs:__imp_??0InvalidOperationException@UnBCL@@QEAA@PEBG@Z; UnBCL::InvalidOperationException::InvalidOperationException(ushort const *)
0x18002a2c0  lea     rax, ??_SInvalidOperationException@UnBCL@@6B@; const UnBCL::InvalidOperationException::`local vftable'
0x18002a2c7  mov     [rbx], rax
0x18002a2ca  jmp     short loc_18002A2CE
0x18002a2cc  xor     ebx, ebx
0x18002a2ce  lea     rdx, aIntCdeclUnbclH; "int __cdecl UnBCL::_::HTEnumerator<clas"...
0x18002a2d5  mov     rcx, rbx
0x18002a2d8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002a2dd  mov     [rsp+28h+pExceptionObject], rax
0x18002a2e2  lea     rdx, _TI5PEAVInvalidOperationException@UnBCL@@; pThrowInfo
0x18002a2e9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002a2ee  call    _CxxThrowException_0
```
