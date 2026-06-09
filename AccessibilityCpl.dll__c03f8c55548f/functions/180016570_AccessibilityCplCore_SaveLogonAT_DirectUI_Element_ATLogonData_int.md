# AccessibilityCplCore::SaveLogonAT(DirectUI::Element *,ATLogonData *,int)

- ea: `0x180016570`
- end: `0x18001668d`
- name: `?SaveLogonAT@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@PEAVATLogonData@@H@Z`
- size: `285`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *, struct ATLogonData *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180019570`

## callees

- `0x180005340`
- `0x180005534`
- `0x1800063c0`
- `0x180015780`
- `0x180015848`
- `0x180016570`
- `0x18001aab0`
- `0x18001af04`
- `0x18001fe70`
- `0x18002e010`

## import_xrefs

- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800165b2`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016652`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800165b2`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016652`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveLogonAT(
        AccessibilityCplCore *this,
        struct DirectUI::Element *a2,
        struct ATLogonData *a3,
        int a4)
{
  struct Accommodation *v7; // rax
  struct Accommodation *v8; // rdi
  char *v10; // rsi
  bool Selected; // al
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  ATL::CStringData *v15; // r11
  ATL::CStringData *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rbx
  ATL::CStringData *v19; // r11

  v7 = (struct Accommodation *)(*(__int64 (__fastcall **)(struct ATLogonData *))(*(_QWORD *)a3 + 16LL))(a3);
  v8 = v7;
  if ( !v7 )
    return 2147500037LL;
  if ( a4 )
  {
    v10 = (char *)this + 40;
    Selected = DirectUI::Element::GetSelected(a2);
    v12 = *(_QWORD *)v8 - 24LL;
    if ( Selected )
    {
      v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12);
      v14 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              v10,
              v13 + 24);
      ATL::CStringData::Release(v15);
      if ( !v14 )
      {
        v16 = (ATL::CStringData *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)v8 - 24LL);
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          v10,
          (char *)v16 + 24);
        ATL::CStringData::Release(v16);
      }
    }
    else
    {
      v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12);
      v18 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              v10,
              v17 + 24);
      ATL::CStringData::Release(v19);
      if ( v18 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
          v10,
          v18);
    }
  }
  else
  {
    if ( (unsigned int)SettingIDFromName(*(_QWORD *)v7) )
    {
      DirectUI::Element::GetSelected(a2);
      AccessibilityCplCore::VisitBOOLSetting(this);
    }
    AccessibilityCplCore::ToggleAT(this, v8, a2, 1, *((_DWORD *)v8 + 20) != 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180016570  push    rbx
0x180016572  push    rbp
0x180016573  push    rsi
0x180016574  push    rdi
0x180016575  sub     rsp, 38h
0x180016579  mov     rax, [r8]
0x18001657c  mov     rsi, rcx
0x18001657f  mov     rcx, r8
0x180016582  mov     ebx, r9d
0x180016585  mov     rbp, rdx
0x180016588  mov     rax, [rax+10h]
0x18001658c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016591  mov     rdi, rax
0x180016594  test    rax, rax
0x180016597  jnz     short loc_1800165A3
0x180016599  mov     eax, 80004005h
0x18001659e  jmp     loc_180016684
0x1800165a3  test    ebx, ebx
0x1800165a5  jz      loc_180016641
0x1800165ab  mov     rcx, rbp
0x1800165ae  add     rsi, 28h ; '('
0x1800165b2  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800165b8  mov     rcx, [rdi]
0x1800165bb  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800165bf  test    al, al
0x1800165c1  jz      short loc_180016610
0x1800165c3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800165c8  mov     rcx, rsi
0x1800165cb  mov     r11, rax
0x1800165ce  lea     rdx, [rax+18h]
0x1800165d2  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x1800165d7  mov     rcx, r11; this
0x1800165da  mov     rbx, rax
0x1800165dd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800165e2  test    rbx, rbx
0x1800165e5  jnz     loc_180016682
0x1800165eb  mov     rcx, [rdi]
0x1800165ee  sub     rcx, 18h
0x1800165f2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800165f7  mov     rcx, rsi
0x1800165fa  mov     rbx, rax
0x1800165fd  lea     rdx, [rax+18h]
0x180016601  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x180016606  mov     rcx, rbx; this
0x180016609  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001660e  jmp     short loc_180016682
0x180016610  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180016615  mov     rcx, rsi
0x180016618  mov     r11, rax
0x18001661b  lea     rdx, [rax+18h]
0x18001661f  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x180016624  mov     rcx, r11; this
0x180016627  mov     rbx, rax
0x18001662a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001662f  test    rbx, rbx
0x180016632  jz      short loc_180016682
0x180016634  mov     rdx, rbx
0x180016637  mov     rcx, rsi
0x18001663a  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x18001663f  jmp     short loc_180016682
0x180016641  mov     rcx, [rax]
0x180016644  call    ?SettingIDFromName@@YA?AW4CPL_SETTING_ID@@PEBG@Z; SettingIDFromName(ushort const *)
0x180016649  mov     ebx, eax
0x18001664b  test    eax, eax
0x18001664d  jz      short loc_180016666
0x18001664f  mov     rcx, rbp
0x180016652  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180016658  movzx   r8d, al; int
0x18001665c  mov     edx, ebx; unsigned int
0x18001665e  mov     rcx, rsi; this
0x180016661  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x180016666  cmp     dword ptr [rdi+50h], 1
0x18001666a  mov     r9b, 1; bool
0x18001666d  mov     r8, rbp; struct DirectUI::Element *
0x180016670  mov     rdx, rdi; struct Accommodation *
0x180016673  setnz   al
0x180016676  mov     rcx, rsi; this
0x180016679  mov     [rsp+58h+var_38], al; bool
0x18001667d  call    ?ToggleAT@AccessibilityCplCore@@AEAAJPEAVAccommodation@@PEAVElement@DirectUI@@_N2@Z; AccessibilityCplCore::ToggleAT(Accommodation *,DirectUI::Element *,bool,bool)
0x180016682  xor     eax, eax
0x180016684  add     rsp, 38h
0x180016688  pop     rdi
0x180016689  pop     rsi
0x18001668a  pop     rbp
0x18001668b  pop     rbx
0x18001668c  retn
```
