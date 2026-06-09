# _CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::catch$10

- ea: `0x180010c7c`
- end: `0x180010d22`
- name: `_CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::catch$10`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004ee0`
- `0x180010c7c`
- `0x180012010`

## string_xrefs

- `0x180010cb3`: `CSMBHelperClass::ReproduceFailureThreadExecutive Unknown Exception`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::catch_10(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx

  v3 = *(_QWORD *)(a2 + 48);
  if ( v3 )
  {
    *(_QWORD *)(a2 + 48) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a2 + 48,
      L"CSMBHelperClass::ReproduceFailureThreadExecutive Unknown Exception");
    v4 = *(_QWORD *)(a2 + 48);
    (*(void (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v3 + 24LL))(
      v3,
      2,
      0,
      L"SMBHelperClass",
      v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 - 8), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v4 - 24) + 8LL))(*(_QWORD *)(v4 - 24), v4 - 24);
  }
  return 0;
}

```

## disassembly

```asm
0x180010c7c  mov     [rsp+arg_8], rdx
0x180010c81  push    rbx
0x180010c82  push    rbp
0x180010c83  push    rdi
0x180010c84  sub     rsp, 30h
0x180010c88  mov     rbp, rdx
0x180010c8b  mov     rdi, [rbp+30h]
0x180010c8f  test    rdi, rdi
0x180010c92  jz      short loc_180010D0F
0x180010c94  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010c9b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010ca2  mov     rax, [rax+18h]
0x180010ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cab  add     rax, 18h
0x180010caf  mov     [rbp+30h], rax
0x180010cb3  lea     rdx, aCsmbhelperclas_1; "CSMBHelperClass::ReproduceFailureThread"...
0x180010cba  lea     rcx, [rbp+30h]
0x180010cbe  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180010cc3  mov     rax, [rdi]
0x180010cc6  xor     r8d, r8d
0x180010cc9  mov     rbx, [rbp+30h]
0x180010ccd  mov     [rsp+48h+var_28], rbx
0x180010cd2  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180010cd9  lea     edx, [r8+2]
0x180010cdd  mov     rcx, rdi
0x180010ce0  mov     rax, [rax+18h]
0x180010ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce9  nop
0x180010cea  or      eax, 0FFFFFFFFh
0x180010ced  lock xadd [rbx-8], eax
0x180010cf2  sub     eax, 1
0x180010cf5  jg      short loc_180010D0F
0x180010cf7  mov     rax, [rbx-18h]
0x180010cfb  mov     r8, [rax]
0x180010cfe  lea     rdx, [rbx-18h]
0x180010d02  mov     rcx, rax
0x180010d05  mov     rax, [r8+8]
0x180010d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d0e  nop
0x180010d0f  mov     rax, 0
0x180010d19  add     rsp, 30h
0x180010d1d  pop     rdi
0x180010d1e  pop     rbp
0x180010d1f  pop     rbx
0x180010d20  retn
```
