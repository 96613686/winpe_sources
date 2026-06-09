# AccessibilityCplCore::SaveSoundSentry(void)

- ea: `0x180017464`
- end: `0x180017669`
- name: `?SaveSoundSentry@AccessibilityCplCore@@AEAAJXZ`
- size: `517`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x18000418c`
- `0x180004f78`
- `0x180017464`
- `0x180018294`
- `0x18001af04`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800174ae`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800174ae`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800174bf`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175b4`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175ca`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175e0`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175f6`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800174bf`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175b4`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175ca`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175e0`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800175f6`
- `DUI70!StrToID` at `0x18001748b`
- `DUI70!StrToID` at `0x180017528`
- `DUI70!StrToID` at `0x180017548`
- `DUI70!StrToID` at `0x180017568`
- `DUI70!StrToID` at `0x180017588`
- `DUI70!StrToID` at `0x18001748b`
- `DUI70!StrToID` at `0x180017528`
- `DUI70!StrToID` at `0x180017548`
- `DUI70!StrToID` at `0x180017568`
- `DUI70!StrToID` at `0x180017588`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017497`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017534`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017554`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017574`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017594`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017497`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017534`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017554`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017574`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017594`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveSoundSentry(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  unsigned int v5; // edi
  DirectUI::Element *v6; // rsi
  const wchar_t **v7; // rbx
  AccessibilityCplCore *v8; // rcx
  DirectUI::Element *v9; // rdi
  unsigned __int16 v10; // ax
  struct DirectUI::Element *v11; // rax
  DirectUI::Element *v12; // rdi
  DirectUI::Element *v13; // r12
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rax
  DirectUI::Element *v16; // rdi
  DirectUI::Element *v17; // rsi
  unsigned __int16 v18; // ax
  struct DirectUI::Element *v19; // rax
  DirectUI::Element *v20; // rdi
  DirectUI::Element *v21; // r15
  unsigned __int16 v22; // ax
  struct DirectUI::Element *v23; // rax
  DirectUI::Element *v24; // rdi
  bool Selected; // al
  int v26; // ecx
  int v27; // eax
  unsigned int v29[4]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v30; // [rsp+40h] [rbp-30h]
  __int128 v31; // [rsp+50h] [rbp-20h]
  __int64 v32; // [rsp+60h] [rbp-10h]
  unsigned int v33; // [rsp+A0h] [rbp+30h] BYREF
  int v34; // [rsp+A8h] [rbp+38h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = StrToID(L"soundsentry");
  Descendent = DirectUI::Element::FindDescendent(v1, v3);
  v5 = 0;
  v6 = Descendent;
  if ( Descendent )
  {
    if ( DirectUI::Element::GetVisible(Descendent) )
    {
      DirectUI::Element::GetSelected(v6);
      AccessibilityCplCore::VisitBOOLSetting(this);
      v7 = (const wchar_t **)Accommodation::Open(L"soundsentry");
      if ( v7 )
      {
        *(_OWORD *)v29 = 0;
        v32 = 0;
        v30 = 0;
        v31 = 0;
        Accommodation::GetData(v7, v29);
        AccessibilityCplCore::SetFlagBasedOnSelection(v8, v6, &v29[1], 1u);
        v9 = (DirectUI::Element *)*((_QWORD *)this + 12);
        v10 = StrToID(L"none");
        v11 = DirectUI::Element::FindDescendent(v9, v10);
        v12 = (DirectUI::Element *)*((_QWORD *)this + 12);
        v13 = v11;
        v14 = StrToID(L"flashactivecaptionbar");
        v15 = DirectUI::Element::FindDescendent(v12, v14);
        v16 = (DirectUI::Element *)*((_QWORD *)this + 12);
        v17 = v15;
        v18 = StrToID(L"flashactivewindow");
        v19 = DirectUI::Element::FindDescendent(v16, v18);
        v20 = (DirectUI::Element *)*((_QWORD *)this + 12);
        v21 = v19;
        v22 = StrToID(L"flashdesktop");
        v23 = DirectUI::Element::FindDescendent(v20, v22);
        v24 = v23;
        if ( v13 && v17 && v21 && v23 )
        {
          if ( DirectUI::Element::GetSelected(v13) )
          {
            LODWORD(v31) = 0;
          }
          else if ( DirectUI::Element::GetSelected(v17) )
          {
            LODWORD(v31) = 1;
          }
          else if ( DirectUI::Element::GetSelected(v21) )
          {
            LODWORD(v31) = 2;
          }
          else
          {
            Selected = DirectUI::Element::GetSelected(v24);
            v26 = v31;
            if ( Selected )
              v26 = 3;
            LODWORD(v31) = v26;
          }
        }
        v5 = (unsigned int)StartList::Start(*((Start **)this + 11), v7, v29, 0, 0);
        v33 = v5;
        v27 = 0;
        if ( (v29[1] & 1) != 0 )
          v27 = v31;
        v34 = v27;
        EaseOfAccessTelemetry::SoundSentryChangedSettingClassic<unsigned long &,long &>(&v34, &v33);
        Accommodation::`scalar deleting destructor'((Accommodation *)v7);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180017464  mov     [rsp-28h+arg_10], rbx
0x180017469  mov     [rsp-28h+arg_18], rsi
0x18001746e  push    rbp
0x18001746f  push    rdi
0x180017470  push    r12
0x180017472  push    r14
0x180017474  push    r15
0x180017476  mov     rbp, rsp
0x180017479  sub     rsp, 70h
0x18001747d  mov     rbx, [rcx+60h]
0x180017481  mov     r14, rcx
0x180017484  lea     rcx, aSoundsentry; "soundsentry"
0x18001748b  call    cs:__imp_StrToID
0x180017491  movzx   edx, ax
0x180017494  mov     rcx, rbx
0x180017497  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001749d  xor     edi, edi
0x18001749f  mov     rsi, rax
0x1800174a2  test    rax, rax
0x1800174a5  jz      loc_18001764E
0x1800174ab  mov     rcx, rax
0x1800174ae  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800174b4  test    al, al
0x1800174b6  jz      loc_18001764E
0x1800174bc  mov     rcx, rsi
0x1800174bf  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800174c5  movzx   r8d, al; int
0x1800174c9  lea     edx, [rdi+0Bh]; unsigned int
0x1800174cc  mov     rcx, r14; this
0x1800174cf  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x1800174d4  lea     rcx, aSoundsentry; "soundsentry"
0x1800174db  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800174e0  mov     rbx, rax
0x1800174e3  test    rax, rax
0x1800174e6  jz      loc_18001764E
0x1800174ec  xorps   xmm0, xmm0
0x1800174ef  lea     rdx, [rbp+var_40]; void *
0x1800174f3  xor     eax, eax
0x1800174f5  mov     rcx, rbx; this
0x1800174f8  movups  xmmword ptr [rbp+var_40], xmm0
0x1800174fc  mov     [rbp+var_10], rax
0x180017500  movups  [rbp+var_30], xmm0
0x180017504  movups  [rbp+var_20], xmm0
0x180017508  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x18001750d  lea     r9d, [rdi+1]; unsigned int
0x180017511  mov     rdx, rsi; struct DirectUI::Element *
0x180017514  lea     r8, [rbp+var_40+4]; unsigned int *
0x180017518  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x18001751d  mov     rdi, [r14+60h]
0x180017521  lea     rcx, aNone; "none"
0x180017528  call    cs:__imp_StrToID
0x18001752e  movzx   edx, ax
0x180017531  mov     rcx, rdi
0x180017534  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001753a  mov     rdi, [r14+60h]
0x18001753e  lea     rcx, aFlashactivecap; "flashactivecaptionbar"
0x180017545  mov     r12, rax
0x180017548  call    cs:__imp_StrToID
0x18001754e  movzx   edx, ax
0x180017551  mov     rcx, rdi
0x180017554  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001755a  mov     rdi, [r14+60h]
0x18001755e  lea     rcx, aFlashactivewin; "flashactivewindow"
0x180017565  mov     rsi, rax
0x180017568  call    cs:__imp_StrToID
0x18001756e  movzx   edx, ax
0x180017571  mov     rcx, rdi
0x180017574  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001757a  mov     rdi, [r14+60h]
0x18001757e  lea     rcx, aFlashdesktop; "flashdesktop"
0x180017585  mov     r15, rax
0x180017588  call    cs:__imp_StrToID
0x18001758e  movzx   edx, ax
0x180017591  mov     rcx, rdi
0x180017594  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001759a  mov     rdi, rax
0x18001759d  test    r12, r12
0x1800175a0  jz      short loc_18001760C
0x1800175a2  test    rsi, rsi
0x1800175a5  jz      short loc_18001760C
0x1800175a7  test    r15, r15
0x1800175aa  jz      short loc_18001760C
0x1800175ac  test    rax, rax
0x1800175af  jz      short loc_18001760C
0x1800175b1  mov     rcx, r12
0x1800175b4  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800175ba  test    al, al
0x1800175bc  jz      short loc_1800175C7
0x1800175be  mov     dword ptr [rbp+var_20], 0
0x1800175c5  jmp     short loc_18001760C
0x1800175c7  mov     rcx, rsi
0x1800175ca  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800175d0  test    al, al
0x1800175d2  jz      short loc_1800175DD
0x1800175d4  mov     dword ptr [rbp+var_20], 1
0x1800175db  jmp     short loc_18001760C
0x1800175dd  mov     rcx, r15
0x1800175e0  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800175e6  test    al, al
0x1800175e8  jz      short loc_1800175F3
0x1800175ea  mov     dword ptr [rbp+var_20], 2
0x1800175f1  jmp     short loc_18001760C
0x1800175f3  mov     rcx, rdi
0x1800175f6  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800175fc  mov     ecx, dword ptr [rbp+var_20]
0x1800175ff  mov     edx, 3
0x180017604  test    al, al
0x180017606  cmovnz  ecx, edx
0x180017609  mov     dword ptr [rbp+var_20], ecx
0x18001760c  mov     rcx, [r14+58h]; this
0x180017610  lea     r8, [rbp+var_40]; void *
0x180017614  xor     r9d, r9d; int
0x180017617  mov     [rsp+70h+var_50], 0; int
0x18001761f  mov     rdx, rbx; struct Accommodation *
0x180017622  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017627  mov     edi, eax
0x180017629  mov     [rbp+arg_0], eax
0x18001762c  xor     eax, eax
0x18001762e  lea     rdx, [rbp+arg_0]
0x180017632  test    byte ptr [rbp+var_40+4], 1
0x180017636  lea     rcx, [rbp+arg_8]
0x18001763a  cmovnz  eax, dword ptr [rbp+var_20]
0x18001763e  mov     [rbp+arg_8], eax
0x180017641  call    ??$SoundSentryChangedSettingClassic@AEAKAEAJ@EaseOfAccessTelemetry@@SAXAEAKAEAJ@Z; EaseOfAccessTelemetry::SoundSentryChangedSettingClassic<ulong &,long &>(ulong &,long &)
0x180017646  mov     rcx, rbx; this
0x180017649  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x18001764e  lea     r11, [rsp+70h+var_s0]
0x180017653  mov     eax, edi
0x180017655  mov     rbx, [r11+40h]
0x180017659  mov     rsi, [r11+48h]
0x18001765d  mov     rsp, r11
0x180017660  pop     r15
0x180017662  pop     r14
0x180017664  pop     r12
0x180017666  pop     rdi
0x180017667  pop     rbp
0x180017668  retn
```
