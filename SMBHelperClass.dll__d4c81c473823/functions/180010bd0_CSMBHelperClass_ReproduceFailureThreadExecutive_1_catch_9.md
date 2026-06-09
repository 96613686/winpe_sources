# _CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::catch$9

- ea: `0x180010bd0`
- end: `0x180010c76`
- name: `_CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::catch$9`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004ee0`
- `0x180010bd0`
- `0x180012010`

## string_xrefs

- `0x180010c07`: `CSMBHelperClass::ReproduceFailure UNCPath not found`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::catch_9(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx

  v3 = *(_QWORD *)(a2 + 48);
  if ( v3 )
  {
    *(_QWORD *)(a2 + 48) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a2 + 48,
      L"CSMBHelperClass::ReproduceFailure UNCPath not found");
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
0x180010bd0  mov     [rsp+arg_8], rdx
0x180010bd5  push    rbx
0x180010bd6  push    rbp
0x180010bd7  push    rdi
0x180010bd8  sub     rsp, 30h
0x180010bdc  mov     rbp, rdx
0x180010bdf  mov     rdi, [rbp+30h]
0x180010be3  test    rdi, rdi
0x180010be6  jz      short loc_180010C63
0x180010be8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010bef  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010bf6  mov     rax, [rax+18h]
0x180010bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bff  add     rax, 18h
0x180010c03  mov     [rbp+30h], rax
0x180010c07  lea     rdx, aCsmbhelperclas_17; "CSMBHelperClass::ReproduceFailure UNCPa"...
0x180010c0e  lea     rcx, [rbp+30h]
0x180010c12  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180010c17  mov     rax, [rdi]
0x180010c1a  xor     r8d, r8d
0x180010c1d  mov     rbx, [rbp+30h]
0x180010c21  mov     [rsp+48h+var_28], rbx
0x180010c26  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180010c2d  lea     edx, [r8+2]
0x180010c31  mov     rcx, rdi
0x180010c34  mov     rax, [rax+18h]
0x180010c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c3d  nop
0x180010c3e  or      eax, 0FFFFFFFFh
0x180010c41  lock xadd [rbx-8], eax
0x180010c46  sub     eax, 1
0x180010c49  jg      short loc_180010C63
0x180010c4b  mov     rax, [rbx-18h]
0x180010c4f  mov     r8, [rax]
0x180010c52  lea     rdx, [rbx-18h]
0x180010c56  mov     rcx, rax
0x180010c59  mov     rax, [r8+8]
0x180010c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c62  nop
0x180010c63  mov     rax, 0
0x180010c6d  add     rsp, 30h
0x180010c71  pop     rdi
0x180010c72  pop     rbp
0x180010c73  pop     rbx
0x180010c74  retn
```
