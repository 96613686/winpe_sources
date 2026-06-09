# UnBCL::Hashtable<UnBCL::String *,ulong>::Remove(UnBCL::String *)

- ea: `0x18002c8b4`
- end: `0x18002c9b3`
- name: `?Remove@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@UEAAXPEAVString@2@@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002c8a0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x180028f14`
- `0x18002c8b4`
- `0x18002cef4`
- `0x180053010`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002c95f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002c95f`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18002c97b`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18002c97b`

## string_xrefs

- `0x18002c98f`: `void __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::Remove(class UnBCL::String *)`
- `0x18002c971`: `null key to Hashtable#Remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnBCL::Hashtable<UnBCL::String *,unsigned long>::Remove(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 (__fastcall ***v4)(_QWORD, __int64); // rdi
  UnBCL::ArgumentNullException *v5; // rax
  UnBCL::Exception *v6; // rbx
  _QWORD v7[2]; // [rsp+30h] [rbp-10h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+68h] [rbp+28h] BYREF
  UnBCL::ArgumentNullException *v9; // [rsp+70h] [rbp+30h] BYREF
  __int64 v10; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 )
  {
    v5 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v6 = v5;
    v9 = v5;
    if ( v5 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v5, L"null key to Hashtable#Remove");
      *(_QWORD *)v6 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v6 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v6,
                         "void __cdecl UnBCL::Hashtable<class UnBCL::String *,unsigned long>::Remove(class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v7[0] = a1 - 128;
  v7[1] = a2;
  if ( !*(_DWORD *)(a1 - 112) && !*(_DWORD *)(a1 - 108) )
    return ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::RemoveKey(
             *(_QWORD *)(a1 - 88),
             v7);
  LODWORD(v9) = 0;
  LODWORD(pExceptionObject) = 0;
  result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::GetNode(
             *(_QWORD *)(a1 - 88),
             (__int64)v7,
             (int *)&v9,
             (unsigned int *)&pExceptionObject,
             &v10);
  if ( result )
  {
    v4 = *(__int64 (__fastcall ****)(_QWORD, __int64))(result + 8);
    result = ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,unsigned long>::TableKey,unsigned long,UnBCL::Hashtable<UnBCL::String *,unsigned long>::KeyTraits,ATL::CElementTraits<unsigned long>>::RemoveKey(
               *(_QWORD *)(a1 - 88),
               v7);
    if ( *(_DWORD *)(a1 - 112) )
    {
      if ( v4 )
        return (**v4)(v4, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c8b4  push    rbp
0x18002c8b6  push    rbx
0x18002c8b7  push    rdi
0x18002c8b8  mov     rbp, rsp
0x18002c8bb  sub     rsp, 40h
0x18002c8bf  mov     rbx, rcx
0x18002c8c2  test    rdx, rdx
0x18002c8c5  jz      loc_18002C95A
0x18002c8cb  lea     rax, [rcx-80h]
0x18002c8cf  mov     [rbp+var_10], rax
0x18002c8d3  mov     [rbp+var_8], rdx
0x18002c8d7  cmp     dword ptr [rcx-70h], 0
0x18002c8db  jnz     short loc_18002C8F2
0x18002c8dd  cmp     dword ptr [rcx-6Ch], 0
0x18002c8e1  jnz     short loc_18002C8F2
0x18002c8e3  lea     rdx, [rbp+var_10]
0x18002c8e7  mov     rcx, [rcx-58h]
0x18002c8eb  call    ?RemoveKey@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAA_NAEBUTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::RemoveKey(UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey const &)
0x18002c8f0  jmp     short loc_18002C952
0x18002c8f2  mov     dword ptr [rbp+arg_10], 0
0x18002c8f9  mov     dword ptr [rbp+pExceptionObject], 0
0x18002c900  lea     rax, [rbp+arg_18]
0x18002c904  mov     [rsp+40h+var_20], rax
0x18002c909  lea     r9, [rbp+pExceptionObject]
0x18002c90d  lea     r8, [rbp+arg_10]
0x18002c911  lea     rdx, [rbp+var_10]
0x18002c915  mov     rcx, [rcx-58h]
0x18002c919  call    ?GetNode@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@AEBAPEAVCNode@12@AEBUTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@AEAI1AEAPEAV312@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::GetNode(UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey const &,uint &,uint &,ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::CNode * &)
0x18002c91e  test    rax, rax
0x18002c921  jz      short loc_18002C952
0x18002c923  mov     rdi, [rax+8]
0x18002c927  lea     rdx, [rbp+var_10]
0x18002c92b  mov     rcx, [rbx-58h]
0x18002c92f  call    ?RemoveKey@?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@KUKeyTraits@23@V?$CElementTraits@K@ATL@@@ATL@@QEAA_NAEBUTableKey@?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@@Z; ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey,ulong,UnBCL::Hashtable<UnBCL::String *,ulong>::KeyTraits,ATL::CElementTraits<ulong>>::RemoveKey(UnBCL::Hashtable<UnBCL::String *,ulong>::TableKey const &)
0x18002c934  cmp     dword ptr [rbx-70h], 0
0x18002c938  jz      short loc_18002C952
0x18002c93a  test    rdi, rdi
0x18002c93d  jz      short loc_18002C952
0x18002c93f  mov     rax, [rdi]
0x18002c942  mov     edx, 1
0x18002c947  mov     rcx, rdi
0x18002c94a  mov     rax, [rax]
0x18002c94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c952  add     rsp, 40h
0x18002c956  pop     rdi
0x18002c957  pop     rbx
0x18002c958  pop     rbp
0x18002c959  retn
0x18002c95a  mov     ecx, 38h ; '8'
0x18002c95f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002c965  mov     rbx, rax
0x18002c968  mov     [rbp+arg_10], rax
0x18002c96c  test    rax, rax
0x18002c96f  jz      short loc_18002C98D
0x18002c971  lea     rdx, aNullKeyToHasht_0; "null key to Hashtable#Remove"
0x18002c978  mov     rcx, rax
0x18002c97b  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18002c981  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x18002c988  mov     [rbx], rax
0x18002c98b  jmp     short loc_18002C98F
0x18002c98d  xor     ebx, ebx
0x18002c98f  lea     rdx, aVoidCdeclUnbcl_3; "void __cdecl UnBCL::Hashtable<class UnB"...
0x18002c996  mov     rcx, rbx
0x18002c999  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002c99e  mov     [rbp+pExceptionObject], rax
0x18002c9a2  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18002c9a9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002c9ad  call    _CxxThrowException_0
```
