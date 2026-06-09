# CMapi2RowFilter::InitRowFilter(CMapi2Accessor *,IMessage *)

- ea: `0x18001f990`
- end: `0x180020477`
- name: `?InitRowFilter@CMapi2RowFilter@@QEAAJPEAVCMapi2Accessor@@PEAUIMessage@@@Z`
- size: `2791`
- prototype: `__int64 __fastcall(CMapi2RowFilter *__hidden this, struct CMapi2Accessor *, struct IMessage *)`
- caller_count: `2`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016044`
- `0x18001afa8`

## callees

- `0x180002300`
- `0x180002780`
- `0x18000e684`
- `0x18000ec8c`
- `0x18000fd58`
- `0x180011884`
- `0x180012398`
- `0x18001269c`
- `0x180013fac`
- `0x180014448`
- `0x1800179d8`
- `0x180017a1c`
- `0x180017c68`
- `0x180017e28`
- `0x1800182dc`
- `0x1800183b0`
- `0x1800185d8`
- `0x180018664`
- `0x180018898`
- `0x18001947c`
- `0x18001981c`
- `0x180019c88`
- `0x18001a0d0`
- `0x18001afa8`
- `0x18001f990`
- `0x180020808`
- `0x180020e44`
- `0x1800212cc`
- `0x18002bc7c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800202b9`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800202b9`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x18001fae8`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x18001fae8`

## string_xrefs

- `0x18001fdbd`: `MAPI/IPM.Task`
- `0x18001ffb9`: `InitRowFilter could not create property processor`
- `0x1800200b6`: `InitRowFilter could not create property manager`
- `0x1800201b2`: `MAPI/IPM.Note.Read`
- `0x1800202d0`: `communication`
- `0x180020423`: `InitRowFilter could not open message`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapi2RowFilter::InitRowFilter(
        CMapi2RowFilter *this,
        struct CMapi2Accessor *a2,
        struct IMessage *a3)
{
  int v5; // r14d
  int v6; // ebx
  struct IMessage **v7; // r15
  struct IMessage *v8; // rcx
  HRESULT OneProp; // eax
  unsigned int v10; // esi
  __int64 v12; // rax
  char v13; // bl
  __int64 v14; // rax
  int v15; // ebx
  unsigned int i; // ebx
  bool v17; // zf
  __int64 v18; // rax
  int v19; // r14d
  CMapi2RowFilter::CBaseProps *v20; // rax
  __int64 v21; // rbx
  CMapi2RowFilter::CNoteProps *v22; // rax
  CMapi2RowFilter::CMessageProps *v23; // rax
  CMapi2RowFilter::CBaseProps *v24; // rax
  CMapi2RowFilter::CBaseProps *v25; // rax
  CMapi2RowFilter::CMessageProps *v26; // rax
  CMapi2RowFilter::CMessageProps *v27; // rax
  CMapi2RowFilter::CContactProps *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rsi
  struct IMessage *v31; // rdx
  _QWORD *v32; // rcx
  _QWORD *v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // esi
  int IsType; // eax
  struct IMessage *v38; // rdx
  int v39; // eax
  const wchar_t **v40; // rax
  __int64 v41; // [rsp+30h] [rbp-B18h] BYREF
  __int64 v42; // [rsp+38h] [rbp-B10h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-B08h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B00h]
  DWORD pdwType; // [rsp+50h] [rbp-AF8h] BYREF
  wchar_t *v46; // [rsp+58h] [rbp-AF0h] BYREF
  LPSPropValue v47; // [rsp+60h] [rbp-AE8h] BYREF
  LPSPropValue pProp; // [rsp+68h] [rbp-AE0h] BYREF
  wchar_t *v49[2]; // [rsp+70h] [rbp-AD8h] BYREF
  _BYTE v50[96]; // [rsp+80h] [rbp-AC8h] BYREF
  _BYTE v51[8]; // [rsp+E0h] [rbp-A68h] BYREF
  LPCWSTR pszValue; // [rsp+E8h] [rbp-A60h]
  int v53; // [rsp+F4h] [rbp-A54h]
  _BYTE pvData[528]; // [rsp+900h] [rbp-248h] BYREF

  v5 = 0;
  pcbData[0] = 0;
  *((_DWORD *)this + 5420) = 0;
  *((_QWORD *)this + 2645) = a2;
  *((_QWORD *)this + 2994) = (char *)this + 23912;
  *((_QWORD *)this + 2995) = (char *)this + 23920;
  *((_QWORD *)this + 2996) = 0;
  *((_QWORD *)this + 2986) = (char *)this + 23848;
  *((_QWORD *)this + 2987) = (char *)this + 23856;
  *((_QWORD *)this + 2988) = 0;
  TComPointer<IFilter>::operator=((char *)this + 24008, 0);
  *(_QWORD *)((char *)this + 21684) = 0;
  *((_DWORD *)this + 5418) = 0;
  CLMString::operator=((char *)this + 21168, *(_QWORD *)(*((_QWORD *)this + 2645) + 104LL));
  *(_QWORD *)((char *)this + 23812) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v46);
  v6 = CMapiUrl::SetURL((CMapi2RowFilter *)((char *)this + 21584), v46);
  if ( v6 < 0 )
    goto LABEL_97;
  v7 = (struct IMessage **)((char *)this + 23832);
  if ( a3 )
  {
    TComPointer<IFilter>::operator=((char *)this + 23832, a3);
  }
  else
  {
    v6 = CMapi2RowFilter::OpenMessage(
           this,
           *((struct CMapi2Accessor **)this + 2645),
           1,
           (struct IMessage **)this + 2979);
    if ( v6 < 0 )
    {
LABEL_96:
      CLogger::Error(v6, L"InitRowFilter could not open message");
      goto LABEL_97;
    }
  }
  if ( v6 == 266755 )
    goto LABEL_96;
  v8 = *v7;
  if ( !*v7 )
    goto LABEL_96;
  pProp = 0;
  OneProp = HrGetOneProp((LPMAPIPROP)v8, 0x1A001Eu, &pProp);
  v10 = OneProp;
  pdwType = OneProp;
  if ( OneProp < 0 )
  {
    CLogger::Error(OneProp, L"InitRowFilter could not get message class");
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return v10;
  }
  v47 = pProp;
  CLMString::operator=((char *)this + 21696, L"MAPI/");
  (*(void (__fastcall **)(char *, CURRENCY, _QWORD, __int64))(*((_QWORD *)this + 2712) + 24LL))(
    (char *)this + 21696,
    pProp->Value.cur,
    *((unsigned int *)this + 5429),
    0xFFFFFFFFLL);
  v12 = TLMString<32,32,256>::TLMString<32,32,256>(v50, L"MAPI/IPM.Document");
  pcbData[0] = 1;
  LODWORD(v41) = 0;
  HIDWORD(v41) = *(_DWORD *)(v12 + 20);
  v42 = v12;
  if ( !(unsigned int)CLMString::BeginsWith((CMapi2RowFilter *)((char *)this + 21696), (const struct CLMSubStr *)&v41)
    || (v13 = 1, *(int *)(*((_QWORD *)this + 2707) - 16LL) <= 0) )
  {
    v13 = 0;
  }
  TLMString<32,32,256>::~TLMString<32,32,256>(v50);
  if ( v13 )
  {
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return 2147750401LL;
  }
  CMapi2RowFilter::AddProperty(
    this,
    (const struct CMapi2FullPropSpec *)g_mfpsPKEY_Message_MessageClass,
    *((const wchar_t **)this + 2713));
  v14 = TLMString<32,32,256>::TLMString<32,32,256>(v50, L"MAPI/IPM.Note.SMIME");
  LODWORD(v41) = 0;
  HIDWORD(v41) = *(_DWORD *)(v14 + 20);
  v42 = v14;
  v15 = CLMString::BeginsWith((CMapi2RowFilter *)((char *)this + 21696), (const struct CLMSubStr *)&v41);
  TLMString<32,32,256>::~TLMString<32,32,256>(v50);
  if ( v15 )
    *((_DWORD *)this + 5956) = 1;
  for ( i = 0; ; ++i )
  {
    v17 = i == 12;
    if ( i >= 0xC )
      break;
    v18 = TLMString<32,32,256>::TLMString<32,32,256>(v50, off_1800412A0[i]);
    LODWORD(v41) = 0;
    HIDWORD(v41) = *(_DWORD *)(v18 + 20);
    v42 = v18;
    v19 = CLMString::BeginsWith((CMapi2RowFilter *)((char *)this + 21696), (const struct CLMSubStr *)&v41);
    TLMString<32,32,256>::~TLMString<32,32,256>(v50);
    if ( v19 )
    {
      CLMString::operator=((char *)this + 21696, off_1800412A0[i]);
      v5 = 0;
      v17 = i == 12;
      break;
    }
    v5 = 0;
  }
  if ( v17 )
    CLMString::operator=((char *)this + 21696, L"MAPI/IPM.Note");
  v41 = 0;
  if ( *(int *)(*((_QWORD *)this + 2707) - 16LL) <= 0 )
  {
    if ( (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Contact")
      || (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.DistList") )
    {
      v28 = (CMapi2RowFilter::CContactProps *)operator new(0x51A0u, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)pcbData = v28;
      if ( v28 )
        v21 = CMapi2RowFilter::CContactProps::CContactProps(v28, this, *v7);
      else
        v21 = 0;
    }
    else if ( (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Appointment")
           || (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Schedule.Meeting") )
    {
      v27 = (CMapi2RowFilter::CMessageProps *)operator new(0x51A8u, (const struct std::nothrow_t *)&std::nothrow);
      v21 = (__int64)v27;
      *(_QWORD *)pcbData = v27;
      if ( v27 )
      {
        CMapi2RowFilter::CMessageProps::CMessageProps(v27, this, *v7);
        *(_QWORD *)v21 = &CMapi2RowFilter::CMeetingProps::`vftable';
        *(_QWORD *)(v21 + 20896) = 0;
      }
      else
      {
        v21 = 0;
      }
    }
    else if ( (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.StickyNote") )
    {
      v22 = (CMapi2RowFilter::CNoteProps *)operator new(0x5198u, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)pcbData = v22;
      if ( v22 )
        v21 = CMapi2RowFilter::CNoteProps::CNoteProps(v22, this, *v7);
      else
        v21 = 0;
    }
    else if ( (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Task") )
    {
      v23 = (CMapi2RowFilter::CMessageProps *)operator new(0x59C8u, (const struct std::nothrow_t *)&std::nothrow);
      v21 = (__int64)v23;
      *(_QWORD *)pcbData = v23;
      if ( v23 )
      {
        CMapi2RowFilter::CMessageProps::CMessageProps(v23, this, *v7);
        *(_QWORD *)v21 = &CMapi2RowFilter::CTaskProps::`vftable';
        *(_QWORD *)(v21 + 20912) = v21 + 20928;
        *(_DWORD *)(v21 + 20920) = 1025;
        *(_WORD *)(v21 + 20928) = 0;
        *(_QWORD *)(v21 + 20904) = &TLMString<1024,1024,1048576>::`vftable';
        *(_DWORD *)(v21 + 20896) = 0;
        *(_DWORD *)(v21 + 20924) = 0;
        **(_WORD **)(v21 + 20912) = 0;
      }
      else
      {
        v21 = 0;
      }
    }
    else if ( (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Activity") )
    {
      v24 = (CMapi2RowFilter::CBaseProps *)operator new(0x3938u, (const struct std::nothrow_t *)&std::nothrow);
      v21 = (__int64)v24;
      *(_QWORD *)pcbData = v24;
      if ( v24 )
      {
        CMapi2RowFilter::CBaseProps::CBaseProps(v24, this, *v7);
        *(_QWORD *)v21 = &CMapi2RowFilter::CJournalProps::`vftable';
      }
      else
      {
        v21 = 0;
      }
    }
    else if ( (unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document") )
    {
      v25 = (CMapi2RowFilter::CBaseProps *)operator new(0x3938u, (const struct std::nothrow_t *)&std::nothrow);
      v21 = (__int64)v25;
      *(_QWORD *)pcbData = v25;
      if ( v25 )
      {
        CMapi2RowFilter::CBaseProps::CBaseProps(v25, this, *v7);
        *(_QWORD *)v21 = &CMapi2RowFilter::CDocumentProps::`vftable';
      }
      else
      {
        v21 = 0;
      }
    }
    else
    {
      v26 = (CMapi2RowFilter::CMessageProps *)operator new(0x51A0u, (const struct std::nothrow_t *)&std::nothrow);
      v21 = (__int64)v26;
      *(_QWORD *)pcbData = v26;
      if ( v26 )
      {
        CMapi2RowFilter::CMessageProps::CMessageProps(v26, this, *v7);
        *(_QWORD *)v21 = &CMapi2RowFilter::CEmailProps::`vftable';
      }
      else
      {
        v21 = 0;
      }
    }
  }
  else
  {
    v20 = (CMapi2RowFilter::CBaseProps *)operator new(0x3938u, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)pcbData = v20;
    if ( v20 )
      v21 = CMapi2RowFilter::CBaseProps::CBaseProps(v20, this, *v7);
    else
      v21 = 0;
  }
  v41 = v21;
  if ( !v21 )
  {
    CLogger::Error(-2147024882, L"InitRowFilter could not create property processor");
    TPointer<CMapi2RowFilter::CBaseProps>::~TPointer<CMapi2RowFilter::CBaseProps>(&v41);
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return pdwType;
  }
  if ( *(int *)(*((_QWORD *)this + 2707) - 16LL) <= 0
    && (!*((_DWORD *)this + 5949)
     || !(unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Note")
     && !(unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Post")) )
  {
    v5 = 1;
  }
  v29 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v30 = v29;
  *(_QWORD *)pcbData = v29;
  if ( v29 )
  {
    v31 = *v7;
    *v29 = 0;
    v32 = v29 + 7;
    v33 = v29 + 8;
    *v33 = v33;
    *v32 = v33;
    v32[2] = v32;
    *((_DWORD *)v32 + 6) = 0;
    v30[6] = &CTPtrSListContainer<CMapi2FullPropSpec>::`vftable';
    TComPointer<IFilter>::operator=(v30, v31);
    *((_DWORD *)v30 + 2) = v5;
    v30[2] = 0;
    v30[3] = 0;
    v30[4] = 0;
    v30[5] = 0;
  }
  else
  {
    v30 = 0;
  }
  *((_QWORD *)this + 2980) = v30;
  if ( !v30 )
  {
    CLogger::Error(-2147024882, L"InitRowFilter could not create property manager");
    TPointer<CMapi2RowFilter::CBaseProps>::~TPointer<CMapi2RowFilter::CBaseProps>(&v41);
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return pdwType;
  }
  v34 = CMapi2RowFilter::CBaseProps::Process((CMapi2RowFilter::CBaseProps *)v21, (struct CMapiPropertyManager *)v30);
  v6 = v34;
  if ( v34 < 0 )
  {
    CLogger::Error(v34, L"InitRowFilter failed to process properties");
    TPointer<CMapi2RowFilter::CBaseProps>::~TPointer<CMapi2RowFilter::CBaseProps>(&v41);
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return (unsigned int)v6;
  }
  if ( (*((_BYTE *)this + 21676) & 0x40) != 0 || *((_DWORD *)this + 5955) && *((_DWORD *)this + 5950) )
  {
    CLogger::Warning(
      v34,
      L"CMapi2RowFilter::InitRowFilter - Do not index if this item is a folder associated message or a private message on "
       "a delegate store");
    TPointer<CMapi2RowFilter::CBaseProps>::~TPointer<CMapi2RowFilter::CBaseProps>(&v41);
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return 2147750401LL;
  }
  v35 = TLMString<32,32,256>::TLMString<32,32,256>(v50, L"MAPI/IPM.Note");
  pcbData[0] = 0;
  pcbData[1] = *(_DWORD *)(v35 + 20);
  v44 = v35;
  v36 = CLMString::BeginsWith((CMapi2RowFilter *)((char *)this + 21696), (const struct CLMSubStr *)pcbData);
  TLMString<32,32,256>::~TLMString<32,32,256>(v50);
  if ( v36 && (*((_BYTE *)this + 21676) & 1) != 0 )
    CLMString::operator=((char *)this + 21696, L"MAPI/IPM.Note.Read");
  if ( *(int *)(*((_QWORD *)this + 2707) - 16LL) > 0 )
  {
    TPointer<CMapi2RowFilter::CBaseProps>::~TPointer<CMapi2RowFilter::CBaseProps>(&v41);
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
    ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
    return (unsigned int)v6;
  }
  TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v51, (char *)this + 21696);
  if ( (*((_BYTE *)this + 21676) & 0x10) != 0 && !*((_DWORD *)this + 5947) || *((_DWORD *)this + 5956) )
  {
    IsType = CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document");
    v38 = *v7;
    if ( IsType )
    {
      v6 = CMapi2RowFilter::EnumerateAttachments(this, v38);
      pcbData[0] = 520;
      pdwType = 1;
      if ( v53 )
      {
        CMapi2RowFilter::AddProperty(this, (const struct CMapi2FullPropSpec *)g_mfpsFileExtension, pszValue);
        if ( !SHGetValueW(
                HKEY_LOCAL_MACHINE,
                L"software\\microsoft\\windows\\currentversion\\explorer\\kindmap",
                pszValue,
                &pdwType,
                pvData,
                pcbData) )
        {
          v49[0] = (wchar_t *)pvData;
          v49[1] = L"communication";
          CMapi2RowFilter::AddMultiValueProperty(
            this,
            (const struct CMapi2FullPropSpec *)g_mfpsKind,
            2u,
            (const wchar_t **)v49);
        }
      }
      if ( *((_DWORD *)this + 2197) )
        CMapi2RowFilter::AddProperty(
          this,
          (const struct CMapi2FullPropSpec *)g_mfpsFileName,
          *((const wchar_t **)this + 1097));
    }
    else
    {
      v39 = CMapi2RowFilter::EnumerateAttachments(this, v38);
      v6 = v39;
      if ( v39 < 0 )
      {
        CLogger::Error(v39, L"InitRowFilter could not EnumerateAttachments");
        v6 = 0;
      }
    }
  }
  CMapi2RowFilter::AddProperty(this, (const struct CMapi2FullPropSpec *)g_mfpsItemType, pszValue);
  v40 = (const wchar_t **)CMapiUrl::ContainerHash((__int64)this + 21584, (__int64)pcbData);
  CMapi2RowFilter::AddProperty(this, (const struct CMapi2FullPropSpec *)g_mfpsContainerHash, *v40);
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)pcbData - 24LL));
  if ( *((_DWORD *)this + 3237) )
    CMapi2RowFilter::AddProperty(
      this,
      (const struct CMapi2FullPropSpec *)g_mfpsSearch_AutoSummary,
      *((const wchar_t **)this + 1617));
  if ( *((_DWORD *)this + 5951) || *((_DWORD *)this + 5952) )
    CMapi2RowFilter::AddProperty(this, (const struct CMapi2FullPropSpec *)g_mfpsGthrFullyContained, 1);
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v51);
  TPointer<CMapi2RowFilter::CBaseProps>::~TPointer<CMapi2RowFilter::CBaseProps>(&v41);
  CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v47);
LABEL_97:
  ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f990  mov     [rsp+arg_8], rbx
0x18001f995  mov     [rsp+arg_18], rsi
0x18001f99a  push    rdi
0x18001f99b  push    r12
0x18001f99d  push    r13
0x18001f99f  push    r14
0x18001f9a1  push    r15
0x18001f9a3  sub     rsp, 0B20h
0x18001f9aa  mov     rax, cs:__security_cookie
0x18001f9b1  xor     rax, rsp
0x18001f9b4  mov     [rsp+0B48h+var_38], rax
0x18001f9bc  mov     rsi, r8
0x18001f9bf  mov     rdi, rcx
0x18001f9c2  xor     r14d, r14d
0x18001f9c5  mov     [rsp+0B48h+var_B08], r14d
0x18001f9ca  mov     [rcx+54B0h], r14d
0x18001f9d1  mov     [rcx+52A8h], rdx
0x18001f9d8  lea     rax, [rcx+5D68h]
0x18001f9df  mov     [rcx+5D90h], rax
0x18001f9e6  add     rax, 8
0x18001f9ea  mov     [rcx+5D98h], rax
0x18001f9f1  mov     [rcx+5DA0h], r14
0x18001f9f8  lea     rax, [rcx+5D28h]
0x18001f9ff  mov     [rcx+5D50h], rax
0x18001fa06  add     rax, 8
0x18001fa0a  mov     [rcx+5D58h], rax
0x18001fa11  mov     [rcx+5D60h], r14
0x18001fa18  add     rcx, 5DC8h
0x18001fa1f  xor     edx, edx
0x18001fa21  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001fa26  mov     [rdi+54B4h], r14
0x18001fa2d  mov     [rdi+54A8h], r14d
0x18001fa34  mov     rdx, [rdi+52A8h]
0x18001fa3b  lea     rcx, [rdi+52B0h]
0x18001fa42  mov     rdx, [rdx+68h]
0x18001fa46  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001fa4b  mov     [rdi+5D04h], r14
0x18001fa52  mov     rdx, [rdi+52B8h]
0x18001fa59  lea     rcx, [rsp+0B48h+var_AF0]
0x18001fa5e  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18001fa63  nop
0x18001fa64  lea     rcx, [rdi+5450h]; this
0x18001fa6b  mov     rdx, [rsp+0B48h+var_AF0]; wchar_t *
0x18001fa70  call    ?SetURL@CMapiUrl@@QEAAJPEB_W@Z; CMapiUrl::SetURL(wchar_t const *)
0x18001fa75  mov     ebx, eax
0x18001fa77  test    eax, eax
0x18001fa79  js      loc_180020432
0x18001fa7f  lea     r15, [rdi+5D18h]
0x18001fa86  test    rsi, rsi
0x18001fa89  jz      short loc_18001FA9C
0x18001fa8b  mov     rdx, rsi
0x18001fa8e  mov     rcx, r15
0x18001fa91  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001fa96  lea     r13d, [r14+1]
0x18001fa9a  jmp     short loc_18001FAC1
0x18001fa9c  mov     r9, r15; struct IMessage **
0x18001fa9f  mov     r13d, 1
0x18001faa5  mov     r8d, r13d; int
0x18001faa8  mov     rdx, [rdi+52A8h]; struct CMapi2Accessor *
0x18001faaf  mov     rcx, rdi; this
0x18001fab2  call    ?OpenMessage@CMapi2RowFilter@@AEAAJPEAVCMapi2Accessor@@HPEAPEAUIMessage@@@Z; CMapi2RowFilter::OpenMessage(CMapi2Accessor *,int,IMessage * *)
0x18001fab7  mov     ebx, eax
0x18001fab9  test    eax, eax
0x18001fabb  js      loc_180020423
0x18001fac1  cmp     ebx, 41203h
0x18001fac7  jz      loc_180020423
0x18001facd  mov     rcx, [r15]; lpMapiProp
0x18001fad0  test    rcx, rcx
0x18001fad3  jz      loc_180020423
0x18001fad9  mov     [rsp+0B48h+pProp], r14
0x18001fade  lea     r8, [rsp+0B48h+pProp]; lppProp
0x18001fae3  mov     edx, 1A001Eh; ulPropTag
0x18001fae8  call    cs:__imp_HrGetOneProp
0x18001faee  mov     esi, eax
0x18001faf0  mov     [rsp+0B48h+pdwType], eax
0x18001faf4  test    eax, eax
0x18001faf6  jns     short loc_18001FB1C
0x18001faf8  lea     rdx, aInitrowfilterC_3; "InitRowFilter could not get message cla"...
0x18001faff  mov     ecx, eax; int
0x18001fb01  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18001fb06  nop
0x18001fb07  mov     rcx, [rsp+0B48h+var_AF0]
0x18001fb0c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fb10  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fb15  mov     eax, esi
0x18001fb17  jmp     loc_180020449
0x18001fb1c  mov     rax, [rsp+0B48h+pProp]
0x18001fb21  mov     [rsp+0B48h+var_AE8], rax
0x18001fb26  lea     r12, [rdi+54C0h]
0x18001fb2d  lea     rdx, aMapi_1; "MAPI/"
0x18001fb34  mov     rcx, r12
0x18001fb37  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001fb3c  mov     rax, [r12]
0x18001fb40  or      r9d, 0FFFFFFFFh
0x18001fb44  mov     r8d, [r12+14h]
0x18001fb49  mov     rdx, [rsp+0B48h+pProp]
0x18001fb4e  mov     rdx, [rdx+8]
0x18001fb52  mov     rcx, r12
0x18001fb55  mov     rax, [rax+18h]
0x18001fb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb5e  lea     rdx, aMapiIpmDocumen; "MAPI/IPM.Document"
0x18001fb65  lea     rcx, [rsp+0B48h+var_AC8]
0x18001fb6d  call    ??0?$TLMString@$0CA@$0CA@$0BAA@@@QEAA@PEB_W@Z; TLMString<32,32,256>::TLMString<32,32,256>(wchar_t const *)
0x18001fb72  nop
0x18001fb73  mov     [rsp+0B48h+var_B08], r13d
0x18001fb78  mov     dword ptr [rsp+0B48h+var_B18], r14d
0x18001fb7d  mov     ecx, [rax+14h]
0x18001fb80  mov     dword ptr [rsp+0B48h+var_B18+4], ecx
0x18001fb84  mov     [rsp+0B48h+var_B10], rax
0x18001fb89  lea     rdx, [rsp+0B48h+var_B18]; struct CLMSubStr *
0x18001fb8e  mov     rcx, r12; this
0x18001fb91  call    ?BeginsWith@CLMString@@QEBAHAEBVCLMSubStr@@@Z; CLMString::BeginsWith(CLMSubStr const &)
0x18001fb96  test    eax, eax
0x18001fb98  jz      short loc_18001FBAA
0x18001fb9a  mov     rax, [rdi+5498h]
0x18001fba1  cmp     [rax-10h], r14d
0x18001fba5  mov     bl, r13b
0x18001fba8  jg      short loc_18001FBAD
0x18001fbaa  mov     bl, r14b
0x18001fbad  lea     rcx, [rsp+0B48h+var_AC8]
0x18001fbb5  call    ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
0x18001fbba  test    bl, bl
0x18001fbbc  jz      short loc_18001FBE1
0x18001fbbe  lea     rcx, [rsp+0B48h+var_AE8]; this
0x18001fbc3  call    ??1CMapiBuffer@@QEAA@XZ; CMapiBuffer::~CMapiBuffer(void)
0x18001fbc8  nop
0x18001fbc9  mov     rcx, [rsp+0B48h+var_AF0]
0x18001fbce  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fbd2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fbd7  mov     eax, 80041201h
0x18001fbdc  jmp     loc_180020449
0x18001fbe1  mov     r8, [rdi+54C8h]; wchar_t *
0x18001fbe8  lea     rdx, ?g_mfpsPKEY_Message_MessageClass@@3VCMapi2FullPropSpec@@B; struct CMapi2FullPropSpec *
0x18001fbef  mov     rcx, rdi; this
0x18001fbf2  call    ?AddProperty@CMapi2RowFilter@@AEAAHPEBVCMapi2FullPropSpec@@PEB_W@Z; CMapi2RowFilter::AddProperty(CMapi2FullPropSpec const *,wchar_t const *)
0x18001fbf7  lea     rdx, aMapiIpmNoteSmi; "MAPI/IPM.Note.SMIME"
0x18001fbfe  lea     rcx, [rsp+0B48h+var_AC8]
0x18001fc06  call    ??0?$TLMString@$0CA@$0CA@$0BAA@@@QEAA@PEB_W@Z; TLMString<32,32,256>::TLMString<32,32,256>(wchar_t const *)
0x18001fc0b  nop
0x18001fc0c  mov     dword ptr [rsp+0B48h+var_B18], r14d
0x18001fc11  mov     ecx, [rax+14h]
0x18001fc14  mov     dword ptr [rsp+0B48h+var_B18+4], ecx
0x18001fc18  mov     [rsp+0B48h+var_B10], rax
0x18001fc1d  lea     rdx, [rsp+0B48h+var_B18]; struct CLMSubStr *
0x18001fc22  mov     rcx, r12; this
0x18001fc25  call    ?BeginsWith@CLMString@@QEBAHAEBVCLMSubStr@@@Z; CLMString::BeginsWith(CLMSubStr const &)
0x18001fc2a  mov     ebx, eax
0x18001fc2c  lea     rcx, [rsp+0B48h+var_AC8]
0x18001fc34  call    ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
0x18001fc39  test    ebx, ebx
0x18001fc3b  jz      short loc_18001FC44
0x18001fc3d  mov     [rdi+5D10h], r13d
0x18001fc44  mov     ebx, r14d
0x18001fc47  cmp     ebx, 0Ch
0x18001fc4a  jnb     short loc_18001FCB4
0x18001fc4c  movsxd  rsi, ebx
0x18001fc4f  lea     rax, off_1800412A0; "MAPI/IPM.Schedule.Meeting"
0x18001fc56  mov     rdx, [rax+rsi*8]
0x18001fc5a  lea     rcx, [rsp+0B48h+var_AC8]
0x18001fc62  call    ??0?$TLMString@$0CA@$0CA@$0BAA@@@QEAA@PEB_W@Z; TLMString<32,32,256>::TLMString<32,32,256>(wchar_t const *)
0x18001fc67  nop
0x18001fc68  mov     dword ptr [rsp+0B48h+var_B18], r14d
0x18001fc6d  mov     ecx, [rax+14h]
0x18001fc70  mov     dword ptr [rsp+0B48h+var_B18+4], ecx
0x18001fc74  mov     [rsp+0B48h+var_B10], rax
0x18001fc79  lea     rdx, [rsp+0B48h+var_B18]; struct CLMSubStr *
0x18001fc7e  mov     rcx, r12; this
0x18001fc81  call    ?BeginsWith@CLMString@@QEBAHAEBVCLMSubStr@@@Z; CLMString::BeginsWith(CLMSubStr const &)
0x18001fc86  mov     r14d, eax
0x18001fc89  lea     rcx, [rsp+0B48h+var_AC8]
0x18001fc91  call    ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
0x18001fc96  test    r14d, r14d
0x18001fc99  jz      short loc_18001FD05
0x18001fc9b  lea     rdx, off_1800412A0; "MAPI/IPM.Schedule.Meeting"
0x18001fca2  mov     rdx, [rdx+rsi*8]
0x18001fca6  mov     rcx, r12
0x18001fca9  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001fcae  xor     r14d, r14d
0x18001fcb1  cmp     ebx, 0Ch
0x18001fcb4  jnz     short loc_18001FCC5
0x18001fcb6  lea     rdx, aMapiIpmNote; "MAPI/IPM.Note"
0x18001fcbd  mov     rcx, r12
0x18001fcc0  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001fcc5  mov     [rsp+0B48h+var_B18], r14
0x18001fcca  mov     rax, [rdi+5498h]
0x18001fcd1  cmp     [rax-10h], r14d
0x18001fcd5  jle     short loc_18001FD18
0x18001fcd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fcde  mov     ecx, 3938h; unsigned __int64
0x18001fce3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fce8  mov     qword ptr [rsp+0B48h+var_B08], rax
0x18001fced  test    rax, rax
0x18001fcf0  jz      short loc_18001FD10
0x18001fcf2  mov     r8, [r15]; struct IMessage *
0x18001fcf5  mov     rdx, rdi; struct CMapi2RowFilter *
0x18001fcf8  mov     rcx, rax; this
0x18001fcfb  call    ??0CBaseProps@CMapi2RowFilter@@QEAA@PEAV1@PEAUIMessage@@@Z; CMapi2RowFilter::CBaseProps::CBaseProps(CMapi2RowFilter *,IMessage *)
0x18001fd00  mov     rbx, rax
0x18001fd03  jmp     short loc_18001FD13
0x18001fd05  add     ebx, r13d
0x18001fd08  xor     r14d, r14d
0x18001fd0b  jmp     loc_18001FC47
0x18001fd10  mov     rbx, r14
0x18001fd13  jmp     loc_18001FFAC
0x18001fd18  lea     rdx, aMapiIpmContact; "MAPI/IPM.Contact"
0x18001fd1f  mov     rcx, rdi; this
0x18001fd22  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fd27  test    eax, eax
0x18001fd29  jnz     loc_18001FF7B
0x18001fd2f  lea     rdx, aMapiIpmDistlis; "MAPI/IPM.DistList"
0x18001fd36  mov     rcx, rdi; this
0x18001fd39  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fd3e  test    eax, eax
0x18001fd40  jnz     loc_18001FF7B
0x18001fd46  lea     rdx, aMapiIpmAppoint; "MAPI/IPM.Appointment"
0x18001fd4d  mov     rcx, rdi; this
0x18001fd50  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fd55  test    eax, eax
0x18001fd57  jnz     loc_18001FF33
0x18001fd5d  lea     rdx, aMapiIpmSchedul; "MAPI/IPM.Schedule.Meeting"
0x18001fd64  mov     rcx, rdi; this
0x18001fd67  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fd6c  test    eax, eax
0x18001fd6e  jnz     loc_18001FF33
0x18001fd74  lea     rdx, aMapiIpmStickyn; "MAPI/IPM.StickyNote"
0x18001fd7b  mov     rcx, rdi; this
0x18001fd7e  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fd83  test    eax, eax
0x18001fd85  jz      short loc_18001FDBD
0x18001fd87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fd8e  mov     ecx, 5198h; unsigned __int64
0x18001fd93  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fd98  mov     qword ptr [rsp+0B48h+var_B08], rax
0x18001fd9d  test    rax, rax
0x18001fda0  jz      short loc_18001FDB5
0x18001fda2  mov     r8, [r15]; struct IMessage *
0x18001fda5  mov     rdx, rdi; struct CMapi2RowFilter *
0x18001fda8  mov     rcx, rax; this
0x18001fdab  call    ??0CNoteProps@CMapi2RowFilter@@QEAA@PEAV1@PEAUIMessage@@@Z; CMapi2RowFilter::CNoteProps::CNoteProps(CMapi2RowFilter *,IMessage *)
0x18001fdb0  mov     rbx, rax
0x18001fdb3  jmp     short loc_18001FDB8
0x18001fdb5  mov     rbx, r14
0x18001fdb8  jmp     loc_18001FFAC
0x18001fdbd  lea     rdx, aMapiIpmTask; "MAPI/IPM.Task"
0x18001fdc4  mov     rcx, rdi; this
0x18001fdc7  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fdcc  test    eax, eax
0x18001fdce  jz      loc_18001FE57
0x18001fdd4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fddb  mov     ecx, 59C8h; unsigned __int64
0x18001fde0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fde5  mov     rbx, rax
0x18001fde8  mov     qword ptr [rsp+0B48h+var_B08], rax
0x18001fded  test    rax, rax
0x18001fdf0  jz      short loc_18001FE4F
0x18001fdf2  mov     r8, [r15]; struct IMessage *
0x18001fdf5  mov     rdx, rdi; struct CMapi2RowFilter *
0x18001fdf8  mov     rcx, rax; this
0x18001fdfb  call    ??0CMessageProps@CMapi2RowFilter@@QEAA@PEAV1@PEAUIMessage@@@Z; CMapi2RowFilter::CMessageProps::CMessageProps(CMapi2RowFilter *,IMessage *)
0x18001fe00  lea     rax, ??_7CTaskProps@CMapi2RowFilter@@6B@; const CMapi2RowFilter::CTaskProps::`vftable'
0x18001fe07  mov     [rbx], rax
0x18001fe0a  lea     rcx, [rbx+51C0h]
0x18001fe11  mov     [rbx+51B0h], rcx
0x18001fe18  mov     dword ptr [rbx+51B8h], 401h
0x18001fe22  mov     [rcx], r14w
0x18001fe26  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x18001fe2d  mov     [rbx+51A8h], rax
0x18001fe34  mov     [rbx+51A0h], r14d
0x18001fe3b  mov     [rbx+51BCh], r14d
0x18001fe42  mov     rcx, [rbx+51B0h]
0x18001fe49  mov     [rcx], r14w
0x18001fe4d  jmp     short loc_18001FE52
0x18001fe4f  mov     rbx, r14
0x18001fe52  jmp     loc_18001FFAC
0x18001fe57  lea     rdx, aMapiIpmActivit; "MAPI/IPM.Activity"
0x18001fe5e  mov     rcx, rdi; this
0x18001fe61  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001fe66  test    eax, eax
0x18001fe68  jz      short loc_18001FEAA
0x18001fe6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fe71  mov     ecx, 3938h; unsigned __int64
0x18001fe76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fe7b  mov     rbx, rax
0x18001fe7e  mov     qword ptr [rsp+0B48h+var_B08], rax
0x18001fe83  test    rax, rax
0x18001fe86  jz      short loc_18001FEA2
0x18001fe88  mov     r8, [r15]; struct IMessage *
0x18001fe8b  mov     rdx, rdi; struct CMapi2RowFilter *
0x18001fe8e  mov     rcx, rax; this
0x18001fe91  call    ??0CBaseProps@CMapi2RowFilter@@QEAA@PEAV1@PEAUIMessage@@@Z; CMapi2RowFilter::CBaseProps::CBaseProps(CMapi2RowFilter *,IMessage *)
0x18001fe96  lea     rax, ??_7CJournalProps@CMapi2RowFilter@@6B@; const CMapi2RowFilter::CJournalProps::`vftable'
0x18001fe9d  mov     [rbx], rax
0x18001fea0  jmp     short loc_18001FEA5
0x18001fea2  mov     rbx, r14
0x18001fea5  jmp     loc_18001FFAC
0x18001feaa  lea     rdx, aMapiIpmDocumen; "MAPI/IPM.Document"
0x18001feb1  mov     rcx, rdi; this
0x18001feb4  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001feb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fec0  test    eax, eax
  ... truncated ...
```
