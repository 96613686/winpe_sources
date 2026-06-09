# AccessibilityCplCore::SetupLogonAT(DirectUI::Element *,ATLogonData *,int)

- ea: `0x180018f40`
- end: `0x180018fe1`
- name: `?SetupLogonAT@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@PEAVATLogonData@@H@Z`
- size: `161`
- prototype: `int(AccessibilityCplCore *__hidden this, struct DirectUI::Element *, struct ATLogonData *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180019570`

## callees

- `0x180005534`
- `0x1800063c0`
- `0x180015780`
- `0x180018f40`
- `0x18001f3d8`
- `0x180022318`
- `0x180023090`
- `0x18002e010`

## import_xrefs

- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018fce`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018fce`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SetupLogonAT(
        AccessibilityCplCore *this,
        struct DirectUI::Element *a2,
        struct ATLogonData *a3,
        int a4)
{
  _QWORD *v8; // r14
  StartList *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  ATL::CStringData *v13; // r11

  ATLogonData::SetAccessibleName(a3, a2, a4);
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(struct ATLogonData *))(*(_QWORD *)a3 + 16LL))(a3);
  if ( !v8 )
    return 2147500037LL;
  if ( a4 )
  {
    v10 = (AccessibilityCplCore *)((char *)this + 40);
    StartList::GetLogonConfigList((__int64)this + 40);
  }
  else
  {
    v10 = (StartList *)*((_QWORD *)this + 11);
    StartList::LoadSettings(v10);
  }
  v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*v8 - 24LL);
  v12 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
          v10,
          v11 + 24);
  ATL::CStringData::Release(v13);
  if ( v12 )
    DirectUI::Element::SetSelected(a2, 1);
  return 0;
}

```

## disassembly

```asm
0x180018f40  push    rbx
0x180018f42  push    rbp
0x180018f43  push    rsi
0x180018f44  push    rdi
0x180018f45  push    r14
0x180018f47  sub     rsp, 20h
0x180018f4b  mov     rbx, r8
0x180018f4e  mov     rdi, rcx
0x180018f51  mov     rcx, rbx; this
0x180018f54  mov     r8d, r9d; int
0x180018f57  mov     esi, r9d
0x180018f5a  mov     rbp, rdx
0x180018f5d  call    ?SetAccessibleName@ATLogonData@@QEAAJPEAVElement@DirectUI@@H@Z; ATLogonData::SetAccessibleName(DirectUI::Element *,int)
0x180018f62  mov     rax, [rbx]
0x180018f65  mov     rcx, rbx
0x180018f68  mov     rax, [rax+10h]
0x180018f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f71  mov     r14, rax
0x180018f74  test    rax, rax
0x180018f77  jnz     short loc_180018F80
0x180018f79  mov     eax, 80004005h
0x180018f7e  jmp     short loc_180018FD6
0x180018f80  test    esi, esi
0x180018f82  jz      short loc_180018F92
0x180018f84  lea     rbx, [rdi+28h]
0x180018f88  mov     rcx, rbx
0x180018f8b  call    ?GetLogonConfigList@StartList@@SAXAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; StartList::GetLogonConfigList(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x180018f90  jmp     short loc_180018F9E
0x180018f92  mov     rbx, [rdi+58h]
0x180018f96  mov     rcx, rbx; this
0x180018f99  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x180018f9e  mov     rcx, [r14]
0x180018fa1  sub     rcx, 18h
0x180018fa5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180018faa  mov     rcx, rbx
0x180018fad  mov     r11, rax
0x180018fb0  lea     rdx, [rax+18h]
0x180018fb4  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x180018fb9  mov     rcx, r11; this
0x180018fbc  mov     rbx, rax
0x180018fbf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018fc4  test    rbx, rbx
0x180018fc7  jz      short loc_180018FD4
0x180018fc9  mov     dl, 1
0x180018fcb  mov     rcx, rbp
0x180018fce  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018fd4  xor     eax, eax
0x180018fd6  add     rsp, 20h
0x180018fda  pop     r14
0x180018fdc  pop     rdi
0x180018fdd  pop     rsi
0x180018fde  pop     rbp
0x180018fdf  pop     rbx
0x180018fe0  retn
```
