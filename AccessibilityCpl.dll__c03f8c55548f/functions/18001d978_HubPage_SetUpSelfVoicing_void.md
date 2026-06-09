# HubPage::SetUpSelfVoicing(void)

- ea: `0x18001d978`
- end: `0x18001dcc1`
- name: `?SetUpSelfVoicing@HubPage@@AEAAJXZ`
- size: `841`
- prototype: `__int64 __fastcall(HubPage *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cf40`
- `0x18001df2c`

## callees

- `0x1800043d4`
- `0x18000546c`
- `0x1800055c0`
- `0x1800057d4`
- `0x1800069a0`
- `0x180012a88`
- `0x180014b34`
- `0x180015780`
- `0x180018260`
- `0x18001d070`
- `0x18001d978`
- `0x18001ed60`
- `0x1800299c8`
- `0x180029c04`
- `0x180029fd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9df`
- `USER32!KillTimer` at `0x18001da64`
- `USER32!KillTimer` at `0x18001da64`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001dc3b`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18001dc3b`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001da38`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001dae2`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001da38`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001dae2`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001da43`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001dad7`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001da43`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001dad7`
- `DUI70!StrToID` at `0x18001da0e`
- `DUI70!StrToID` at `0x18001db54`
- `DUI70!StrToID` at `0x18001db74`
- `DUI70!StrToID` at `0x18001db98`
- `DUI70!StrToID` at `0x18001dbbc`
- `DUI70!StrToID` at `0x18001dbe0`
- `DUI70!StrToID` at `0x18001dc04`
- `DUI70!StrToID` at `0x18001da0e`
- `DUI70!StrToID` at `0x18001db54`
- `DUI70!StrToID` at `0x18001db74`
- `DUI70!StrToID` at `0x18001db98`
- `DUI70!StrToID` at `0x18001dbbc`
- `DUI70!StrToID` at `0x18001dbe0`
- `DUI70!StrToID` at `0x18001dc04`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001da1a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001db60`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001db80`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dba4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dbc8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dbec`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dc10`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001da1a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001db60`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001db80`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dba4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dbc8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dbec`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001dc10`

## string_xrefs

- `0x18001d9a8`: `Software\Microsoft\Ease of Access`
- `0x18001dbf9`: `highcontrastlink`
- `0x18001da20`: `screenreader`

## pseudocode

```c
__int64 __fastcall HubPage::SetUpSelfVoicing(HubPage *this, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rbx
  HubPage *v10; // rcx
  DuiVoice *v11; // rdi
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rax
  DirectUI::Element *v16; // rbx
  unsigned __int16 v17; // ax
  struct DirectUI::Element *v18; // rax
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  struct DirectUI::Element *v21; // rax
  DirectUI::Element *v22; // rbx
  unsigned __int16 v23; // ax
  struct DirectUI::Element *v24; // rax
  DirectUI::Element *v25; // rbx
  unsigned __int16 v26; // ax
  struct DirectUI::Element *v27; // rax
  DirectUI::Element *v28; // rbx
  unsigned __int16 v29; // ax
  unsigned int i; // esi
  DirectUI::Element *v31; // r14
  unsigned __int64 v32; // r15
  const unsigned __int16 *Buffer; // rax
  HKEY v34; // [rsp+30h] [rbp-29h]
  HKEY v35[3]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v36[11]; // [rsp+58h] [rbp-1h]
  unsigned int v37; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v38; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v39; // [rsp+D8h] [rbp+7Fh] BYREF

  memset(v35, 0, sizeof(v35));
  if ( (unsigned int)ATL::CRegKey::Create(
                       (ATL::CRegKey *)v35,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Ease of Access",
                       a4,
                       0,
                       0x2001Fu,
                       v34,
                       0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_11;
  }
  v7 = (DirectUI::Element *)*((_QWORD *)this + 32);
  v8 = StrToID(L"selfvoice");
  Descendent = DirectUI::Element::FindDescendent(v7, v8);
  if ( HubPage::IsSimpleProfileConfiguredToRun(v10, L"screenreader") )
  {
    DirectUI::Element::SetSelected(Descendent, 0);
    DirectUI::Element::SetEnabled(Descendent, 0);
    ATL::CRegKey::SetDWORDValue(v35, L"selfvoice", 0);
    KillTimer(*((HWND *)this + 41), 0x123u);
    DuiVoice::Off((HubPage *)((char *)this + 264));
  }
  else
  {
    v37 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v35, L"selfvoice", &v37) != 0;
    v38 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v35, L"selfscan", &v38) != 0;
    if ( v37 )
    {
      if ( Descendent )
      {
        DirectUI::Element::SetEnabled(Descendent, 1);
        DirectUI::Element::SetSelected(Descendent, 1);
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v39);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        &v39,
        v38 != 0 ? 6004 : 6016);
      v11 = (HubPage *)((char *)this + 264);
      if ( (int)DuiVoice::Speak((HubPage *)((char *)this + 264), &Data) < 0 )
      {
        ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
        v6 = -2147467259;
LABEL_11:
        ATL::CRegKey::Close((ATL::CRegKey *)v35);
        return v6;
      }
      v13 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v14 = StrToID(L"selfscan");
      v15 = DirectUI::Element::FindDescendent(v13, v14);
      v16 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v36[0] = v15;
      v17 = StrToID(L"selfvoice");
      v18 = DirectUI::Element::FindDescendent(v16, v17);
      v19 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v36[1] = v18;
      v20 = StrToID(L"Narrator");
      v21 = DirectUI::Element::FindDescendent(v19, v20);
      v22 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v36[2] = v21;
      v23 = StrToID(L"magnifierpane");
      v24 = DirectUI::Element::FindDescendent(v22, v23);
      v25 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v36[3] = v24;
      v26 = StrToID(L"osk");
      v27 = DirectUI::Element::FindDescendent(v25, v26);
      v28 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v36[4] = v27;
      v29 = StrToID(L"highcontrastlink");
      v36[5] = DirectUI::Element::FindDescendent(v28, v29);
      for ( i = 0; i < 6; ++i )
      {
        v31 = (DirectUI::Element *)v36[i];
        if ( v31 && DuiVoice::CreateVoice(v11) >= 0 && (int)DirectUI::Element::AddListener(v31, v11) >= 0 )
        {
          v32 = *((_QWORD *)v11 + 2);
          if ( v32 >= *((_QWORD *)v11 + 3)
            && !ATL::CAtlArray<ATL::CAutoPtr<ATData>,ATL::CAutoPtrElementTraits<ATData>>::GrowBuffer(
                  (__int64)v11 + 8,
                  v32 + 1) )
          {
            ATL::AtlThrowImpl(-2147024882);
          }
          *(_QWORD *)(*((_QWORD *)v11 + 1) + 8 * v32) = v31;
          ++*((_QWORD *)v11 + 2);
        }
      }
      Buffer = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v39);
      DuiVoice::Speak(v11, Buffer);
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v35);
  return 0;
}

```

## disassembly

```asm
0x18001d978  mov     [rsp-8+arg_0], rbx
0x18001d97d  push    rbp
0x18001d97e  push    rsi
0x18001d97f  push    rdi
0x18001d980  push    r14
0x18001d982  push    r15
0x18001d984  lea     rbp, [rsp-37h]
0x18001d989  sub     rsp, 90h
0x18001d990  mov     rsi, rcx
0x18001d993  mov     [rsp+0B0h+var_78], 0; unsigned int *
0x18001d99c  mov     [rsp+0B0h+var_88], 2001Fh; REGSAM
0x18001d9a4  lea     rcx, [rbp+57h+var_70]; this
0x18001d9a8  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x18001d9af  mov     [rsp+0B0h+var_90], 0; DWORD
0x18001d9b7  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001d9be  mov     [rbp+57h+var_70], 0
0x18001d9c6  mov     [rbp+57h+var_68], 0
0x18001d9ce  mov     [rbp+57h+var_60], 0
0x18001d9d6  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001d9db  test    eax, eax
0x18001d9dd  jz      short loc_18001D9FD
0x18001d9df  call    cs:__imp_GetLastError
0x18001d9e5  mov     ebx, eax
0x18001d9e7  test    eax, eax
0x18001d9e9  jle     loc_18001DB36
0x18001d9ef  movzx   ebx, ax
0x18001d9f2  or      ebx, 80070000h
0x18001d9f8  jmp     loc_18001DB36
0x18001d9fd  mov     rbx, [rsi+100h]
0x18001da04  lea     r14, aSelfvoice; "selfvoice"
0x18001da0b  mov     rcx, r14
0x18001da0e  call    cs:__imp_StrToID
0x18001da14  movzx   edx, ax
0x18001da17  mov     rcx, rbx
0x18001da1a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001da20  lea     rdx, aScreenreader; "screenreader"
0x18001da27  mov     rbx, rax
0x18001da2a  call    ?IsSimpleProfileConfiguredToRun@HubPage@@AEAAHPEAG@Z; HubPage::IsSimpleProfileConfiguredToRun(ushort *)
0x18001da2f  test    eax, eax
0x18001da31  jz      short loc_18001DA7B
0x18001da33  xor     edx, edx
0x18001da35  mov     rcx, rbx
0x18001da38  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001da3e  xor     edx, edx
0x18001da40  mov     rcx, rbx
0x18001da43  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18001da49  xor     r8d, r8d; unsigned int
0x18001da4c  lea     rcx, [rbp+57h+var_70]; this
0x18001da50  mov     rdx, r14; unsigned __int16 *
0x18001da53  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001da58  mov     rcx, [rsi+148h]; hWnd
0x18001da5f  mov     edx, 123h; uIDEvent
0x18001da64  call    cs:__imp_KillTimer
0x18001da6a  lea     rcx, [rsi+108h]; this
0x18001da71  call    ?Off@DuiVoice@@QEAAXXZ; DuiVoice::Off(void)
0x18001da76  jmp     loc_18001DC94
0x18001da7b  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x18001da7f  mov     [rbp+57h+arg_8], 0
0x18001da86  mov     rdx, r14; unsigned __int16 *
0x18001da89  lea     rcx, [rbp+57h+var_70]; this
0x18001da8d  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001da92  test    eax, eax
0x18001da94  jz      short loc_18001DA9D
0x18001da96  mov     [rbp+57h+arg_8], 1
0x18001da9d  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x18001daa1  mov     [rbp+57h+arg_10], 0
0x18001daa8  lea     rdx, aSelfscan; "selfscan"
0x18001daaf  lea     rcx, [rbp+57h+var_70]; this
0x18001dab3  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001dab8  test    eax, eax
0x18001daba  jz      short loc_18001DAC3
0x18001dabc  mov     [rbp+57h+arg_10], 1
0x18001dac3  cmp     [rbp+57h+arg_8], 0
0x18001dac7  jz      loc_18001DC94
0x18001dacd  test    rbx, rbx
0x18001dad0  jz      short loc_18001DAE8
0x18001dad2  mov     dl, 1
0x18001dad4  mov     rcx, rbx
0x18001dad7  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18001dadd  mov     dl, 1
0x18001dadf  mov     rcx, rbx
0x18001dae2  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001dae8  lea     rcx, [rbp+57h+arg_18]
0x18001daec  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001daf1  mov     eax, [rbp+57h+arg_10]
0x18001daf4  lea     rcx, [rbp+57h+arg_18]
0x18001daf8  neg     eax
0x18001dafa  sbb     edx, edx
0x18001dafc  and     edx, 0FFFFFFF4h
0x18001daff  add     edx, 1780h
0x18001db05  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18001db0a  lea     rdi, [rsi+108h]
0x18001db11  mov     rcx, rdi; this
0x18001db14  lea     rdx, Data; unsigned __int16 *
0x18001db1b  call    ?Speak@DuiVoice@@QEAAJPEBG@Z; DuiVoice::Speak(ushort const *)
0x18001db20  test    eax, eax
0x18001db22  jns     short loc_18001DB46
0x18001db24  mov     rcx, [rbp+57h+arg_18]
0x18001db28  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001db2c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001db31  mov     ebx, 80004005h
0x18001db36  lea     rcx, [rbp+57h+var_70]; this
0x18001db3a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001db3f  mov     eax, ebx
0x18001db41  jmp     loc_18001DC9F
0x18001db46  mov     rbx, [rsi+100h]
0x18001db4d  lea     rcx, aSelfscan; "selfscan"
0x18001db54  call    cs:__imp_StrToID
0x18001db5a  movzx   edx, ax
0x18001db5d  mov     rcx, rbx
0x18001db60  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001db66  mov     rbx, [rsi+100h]
0x18001db6d  mov     rcx, r14
0x18001db70  mov     [rbp+57h+var_58], rax
0x18001db74  call    cs:__imp_StrToID
0x18001db7a  movzx   edx, ax
0x18001db7d  mov     rcx, rbx
0x18001db80  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001db86  mov     rbx, [rsi+100h]
0x18001db8d  lea     rcx, aNarrator_0; "Narrator"
0x18001db94  mov     [rbp+57h+var_50], rax
0x18001db98  call    cs:__imp_StrToID
0x18001db9e  movzx   edx, ax
0x18001dba1  mov     rcx, rbx
0x18001dba4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001dbaa  mov     rbx, [rsi+100h]
0x18001dbb1  lea     rcx, aMagnifierpane; "magnifierpane"
0x18001dbb8  mov     [rbp+57h+var_48], rax
0x18001dbbc  call    cs:__imp_StrToID
0x18001dbc2  movzx   edx, ax
0x18001dbc5  mov     rcx, rbx
0x18001dbc8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001dbce  mov     rbx, [rsi+100h]
0x18001dbd5  lea     rcx, aOsk; "osk"
0x18001dbdc  mov     [rbp+57h+var_40], rax
0x18001dbe0  call    cs:__imp_StrToID
0x18001dbe6  movzx   edx, ax
0x18001dbe9  mov     rcx, rbx
0x18001dbec  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001dbf2  mov     rbx, [rsi+100h]
0x18001dbf9  lea     rcx, aHighcontrastli; "highcontrastlink"
0x18001dc00  mov     [rbp+57h+var_38], rax
0x18001dc04  call    cs:__imp_StrToID
0x18001dc0a  movzx   edx, ax
0x18001dc0d  mov     rcx, rbx
0x18001dc10  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001dc16  mov     [rbp+57h+var_30], rax
0x18001dc1a  xor     esi, esi
0x18001dc1c  movsxd  rax, esi
0x18001dc1f  mov     r14, [rbp+rax*8+57h+var_58]
0x18001dc24  test    r14, r14
0x18001dc27  jz      short loc_18001DC6C
0x18001dc29  mov     rcx, rdi; this
0x18001dc2c  call    ?CreateVoice@DuiVoice@@AEAAJXZ; DuiVoice::CreateVoice(void)
0x18001dc31  test    eax, eax
0x18001dc33  js      short loc_18001DC6C
0x18001dc35  mov     rdx, rdi
0x18001dc38  mov     rcx, r14
0x18001dc3b  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18001dc41  test    eax, eax
0x18001dc43  js      short loc_18001DC6C
0x18001dc45  mov     r15, [rdi+10h]
0x18001dc49  cmp     r15, [rdi+18h]
0x18001dc4d  jb      short loc_18001DC60
0x18001dc4f  lea     rdx, [r15+1]
0x18001dc53  lea     rcx, [rdi+8]
0x18001dc57  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VATData@@@ATL@@V?$CAutoPtrElementTraits@VATData@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATData>,ATL::CAutoPtrElementTraits<ATData>>::GrowBuffer(unsigned __int64)
0x18001dc5c  test    al, al
0x18001dc5e  jz      short loc_18001DCB6
0x18001dc60  mov     rax, [rdi+8]
0x18001dc64  mov     [rax+r15*8], r14
0x18001dc68  inc     qword ptr [rdi+10h]
0x18001dc6c  inc     esi
0x18001dc6e  cmp     esi, 6
0x18001dc71  jb      short loc_18001DC1C
0x18001dc73  lea     rcx, [rbp+57h+arg_18]
0x18001dc77  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18001dc7c  mov     rdx, rax; unsigned __int16 *
0x18001dc7f  mov     rcx, rdi; this
0x18001dc82  call    ?Speak@DuiVoice@@QEAAJPEBG@Z; DuiVoice::Speak(ushort const *)
0x18001dc87  mov     rcx, [rbp+57h+arg_18]
0x18001dc8b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001dc8f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dc94  lea     rcx, [rbp+57h+var_70]; this
0x18001dc98  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001dc9d  xor     eax, eax
0x18001dc9f  mov     rbx, [rsp+0B0h+arg_0]
0x18001dca7  add     rsp, 90h
0x18001dcae  pop     r15
0x18001dcb0  pop     r14
0x18001dcb2  pop     rdi
0x18001dcb3  pop     rsi
0x18001dcb4  pop     rbp
0x18001dcb5  retn
0x18001dcb6  mov     ecx, 8007000Eh; int
0x18001dcbb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
