# _CSMBHelperClass::Repair_::_1_::catch$4

- ea: `0x180010960`
- end: `0x180010a26`
- name: `_CSMBHelperClass::Repair_::_1_::catch$4`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180004ee0`
- `0x180010960`
- `0x180012010`

## string_xrefs

- `0x1800109a6`: `CSMBHelperClass::Repair Failed `

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::Repair_::_1_::catch_4(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx

  v3 = *(_QWORD *)(a2 + 192);
  if ( *(_QWORD *)(v3 + 176) )
  {
    *(_QWORD *)(a2 + 192) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a2 + 192,
      L"CSMBHelperClass::Repair Failed ");
    v4 = *(_QWORD *)(a2 + 192);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, __int64))(**(_QWORD **)(v3 + 176) + 24LL))(
      *(_QWORD *)(v3 + 176),
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
0x180010960  mov     [rsp+arg_8], rdx
0x180010965  push    rbx
0x180010966  push    rbp
0x180010967  push    rdi
0x180010968  sub     rsp, 30h
0x18001096c  mov     rbp, rdx
0x18001096f  mov     rdi, [rbp+0C0h]
0x180010976  cmp     qword ptr [rdi+0B0h], 0
0x18001097e  jz      loc_180010A13
0x180010984  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001098b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010992  mov     rax, [rax+18h]
0x180010996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099b  add     rax, 18h
0x18001099f  mov     [rbp+0C0h], rax
0x1800109a6  lea     rdx, aCsmbhelperclas_2; "CSMBHelperClass::Repair Failed "
0x1800109ad  lea     rcx, [rbp+0C0h]
0x1800109b4  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800109b9  mov     rax, [rdi+0B0h]
0x1800109c0  mov     rdx, [rax]
0x1800109c3  xor     r8d, r8d
0x1800109c6  mov     rax, [rdx+18h]
0x1800109ca  mov     rbx, [rbp+0C0h]
0x1800109d1  mov     [rsp+48h+var_28], rbx
0x1800109d6  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x1800109dd  lea     edx, [r8+2]
0x1800109e1  mov     rcx, [rdi+0B0h]
0x1800109e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ed  nop
0x1800109ee  or      eax, 0FFFFFFFFh
0x1800109f1  lock xadd [rbx-8], eax
0x1800109f6  sub     eax, 1
0x1800109f9  jg      short loc_180010A13
0x1800109fb  mov     rax, [rbx-18h]
0x1800109ff  mov     r8, [rax]
0x180010a02  lea     rdx, [rbx-18h]
0x180010a06  mov     rcx, rax
0x180010a09  mov     rax, [r8+8]
0x180010a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a12  nop
0x180010a13  mov     rax, 0
0x180010a1d  add     rsp, 30h
0x180010a21  pop     rdi
0x180010a22  pop     rbp
0x180010a23  pop     rbx
0x180010a24  retn
```
