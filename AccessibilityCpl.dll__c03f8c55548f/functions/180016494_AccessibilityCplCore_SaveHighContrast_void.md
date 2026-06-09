# AccessibilityCplCore::SaveHighContrast(void)

- ea: `0x180016494`
- end: `0x180016569`
- name: `?SaveHighContrast@AccessibilityCplCore@@AEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180016494`
- `0x1800178c0`
- `0x180018294`
- `0x18001af04`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800164ce`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800164ce`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800164df`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800164df`
- `DUI70!StrToID` at `0x1800164ad`
- `DUI70!StrToID` at `0x1800164ad`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800164b9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800164b9`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveHighContrast(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned int v3; // ebp
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rdi
  const wchar_t **v7; // rax
  const wchar_t **v8; // rbx
  AccessibilityCplCore *v9; // rcx
  Start *v10; // rcx
  UINT v12[14]; // [rsp+30h] [rbp-38h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = 0;
  v4 = StrToID(L"highcontrastshortcut");
  Descendent = DirectUI::Element::FindDescendent(v1, v4);
  v6 = Descendent;
  if ( Descendent )
  {
    if ( DirectUI::Element::GetVisible(Descendent) )
    {
      DirectUI::Element::GetSelected(v6);
      AccessibilityCplCore::VisitBOOLSetting(this);
      v7 = (const wchar_t **)Accommodation::Open(L"highcontrast");
      v8 = v7;
      if ( v7 )
      {
        *(_OWORD *)v12 = 0;
        Accommodation::GetData(v7, v12);
        AccessibilityCplCore::SetFlagBasedOnSelection(v9, v6, &v12[1], 4u);
        v10 = (Start *)*((_QWORD *)this + 11);
        v12[1] |= 0x1000u;
        StartList::Start(v10, v8, v12, 0, 0);
        v3 = AccessibilityCplCore::SaveWarnings(this);
        Accommodation::`scalar deleting destructor'((Accommodation *)v8);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180016494  push    rbx
0x180016496  push    rbp
0x180016497  push    rsi
0x180016498  push    rdi
0x180016499  sub     rsp, 48h
0x18001649d  mov     rbx, [rcx+60h]
0x1800164a1  mov     rsi, rcx
0x1800164a4  lea     rcx, aHighcontrastsh; "highcontrastshortcut"
0x1800164ab  xor     ebp, ebp
0x1800164ad  call    cs:__imp_StrToID
0x1800164b3  movzx   edx, ax
0x1800164b6  mov     rcx, rbx
0x1800164b9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800164bf  mov     rdi, rax
0x1800164c2  test    rax, rax
0x1800164c5  jz      loc_18001655E
0x1800164cb  mov     rcx, rax
0x1800164ce  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800164d4  test    al, al
0x1800164d6  jz      loc_18001655E
0x1800164dc  mov     rcx, rdi
0x1800164df  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800164e5  movzx   r8d, al; int
0x1800164e9  lea     edx, [rbp+2]; unsigned int
0x1800164ec  mov     rcx, rsi; this
0x1800164ef  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x1800164f4  lea     rcx, aHighcontrast; "highcontrast"
0x1800164fb  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180016500  mov     rbx, rax
0x180016503  test    rax, rax
0x180016506  jz      short loc_18001655E
0x180016508  xorps   xmm0, xmm0
0x18001650b  lea     rdx, [rsp+68h+var_38]; void *
0x180016510  mov     rcx, rax; this
0x180016513  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x180016518  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x18001651d  lea     r9d, [rbp+4]; unsigned int
0x180016521  mov     rdx, rdi; struct DirectUI::Element *
0x180016524  lea     r8, [rsp+68h+var_38+4]; unsigned int *
0x180016529  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x18001652e  mov     rcx, [rsi+58h]; this
0x180016532  lea     r8, [rsp+68h+var_38]; void *
0x180016537  bts     [rsp+68h+var_38+4], 0Ch
0x18001653d  xor     r9d, r9d; int
0x180016540  mov     rdx, rbx; struct Accommodation *
0x180016543  mov     [rsp+68h+var_48], ebp; int
0x180016547  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x18001654c  mov     rcx, rsi; this
0x18001654f  call    ?SaveWarnings@AccessibilityCplCore@@AEAAJXZ; AccessibilityCplCore::SaveWarnings(void)
0x180016554  mov     rcx, rbx; this
0x180016557  mov     ebp, eax
0x180016559  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x18001655e  mov     eax, ebp
0x180016560  add     rsp, 48h
0x180016564  pop     rdi
0x180016565  pop     rsi
0x180016566  pop     rbp
0x180016567  pop     rbx
0x180016568  retn
```
