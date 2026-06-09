# _CSMBHelperClass::ReproduceFailure_::_1_::catch$18

- ea: `0x180010a50`
- end: `0x180010b01`
- name: `_CSMBHelperClass::ReproduceFailure_::_1_::catch$18`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004ee0`
- `0x180010a50`
- `0x180012010`

## string_xrefs

- `0x180010a8d`: `CSMBHelperClass::ReproduceFailure UNCPath not found`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ReproduceFailure_::_1_::catch_18(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx

  v3 = *(_QWORD *)(a2 + 88);
  if ( *(_QWORD *)(v3 + 120) )
  {
    *(_QWORD *)(a2 + 80) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a2 + 80,
      L"CSMBHelperClass::ReproduceFailure UNCPath not found");
    v4 = *(_QWORD *)(a2 + 80);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, __int64))(**(_QWORD **)(v3 + 120) + 24LL))(
      *(_QWORD *)(v3 + 120),
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
0x180010a50  mov     [rsp+arg_8], rdx
0x180010a55  push    rbx
0x180010a56  push    rbp
0x180010a57  push    rdi
0x180010a58  sub     rsp, 50h
0x180010a5c  mov     rbp, rdx
0x180010a5f  mov     rdi, [rbp+58h]
0x180010a63  cmp     qword ptr [rdi+78h], 0
0x180010a68  jz      loc_180010AEE
0x180010a6e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010a75  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010a7c  mov     rax, [rax+18h]
0x180010a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a85  add     rax, 18h
0x180010a89  mov     [rbp+50h], rax
0x180010a8d  lea     rdx, aCsmbhelperclas_17; "CSMBHelperClass::ReproduceFailure UNCPa"...
0x180010a94  lea     rcx, [rbp+50h]
0x180010a98  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180010a9d  mov     rax, [rdi+78h]
0x180010aa1  mov     rdx, [rax]
0x180010aa4  xor     r8d, r8d
0x180010aa7  mov     rax, [rdx+18h]
0x180010aab  mov     rbx, [rbp+50h]
0x180010aaf  mov     [rsp+68h+var_48], rbx
0x180010ab4  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180010abb  lea     edx, [r8+2]
0x180010abf  mov     rcx, [rdi+78h]
0x180010ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac8  nop
0x180010ac9  or      eax, 0FFFFFFFFh
0x180010acc  lock xadd [rbx-8], eax
0x180010ad1  sub     eax, 1
0x180010ad4  jg      short loc_180010AEE
0x180010ad6  mov     rax, [rbx-18h]
0x180010ada  mov     r8, [rax]
0x180010add  lea     rdx, [rbx-18h]
0x180010ae1  mov     rcx, rax
0x180010ae4  mov     rax, [r8+8]
0x180010ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aed  nop
0x180010aee  mov     rax, 0
0x180010af8  add     rsp, 50h
0x180010afc  pop     rdi
0x180010afd  pop     rbp
0x180010afe  pop     rbx
0x180010aff  retn
```
