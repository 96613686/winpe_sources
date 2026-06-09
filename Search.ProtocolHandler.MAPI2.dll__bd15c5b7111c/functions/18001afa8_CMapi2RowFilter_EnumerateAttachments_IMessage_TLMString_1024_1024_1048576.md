# CMapi2RowFilter::EnumerateAttachments(IMessage *,TLMString<1024,1024,1048576> *)

- ea: `0x18001afa8`
- end: `0x18001bd95`
- name: `?EnumerateAttachments@CMapi2RowFilter@@AEAAJPEAUIMessage@@PEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@Z`
- size: `3565`
- prototype: `__int64 __fastcall(CMapi2RowFilter *this, struct IMessage *, __int64)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f990`

## callees

- `0x180002300`
- `0x180002780`
- `0x18000e0d0`
- `0x18000e6e0`
- `0x18000e8ac`
- `0x18000ea18`
- `0x18000ebac`
- `0x18000ec8c`
- `0x18000fd58`
- `0x180011884`
- `0x1800122d8`
- `0x18001356c`
- `0x18001359c`
- `0x180013fe0`
- `0x180014014`
- `0x180014448`
- `0x180014f08`
- `0x1800166e4`
- `0x180017894`
- `0x180017bd4`
- `0x180017efc`
- `0x18001868c`
- `0x1800186cc`
- `0x180018970`
- `0x180018a20`
- `0x180018dcc`
- `0x180019f6c`
- `0x18001a05c`
- `0x18001a7f0`
- `0x18001afa8`
- `0x18001bd9c`
- `0x18001da9c`
- `0x18001f990`
- `0x180020808`
- `0x180020d2c`
- `0x180021ae4`
- `0x18002beb0`
- `0x180030580`
- `0x180036e7c`
- `0x180037388`
- `0x180037a68`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIA` at `0x18001b5ef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIA` at `0x18001b5ef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b5c2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18001b5c2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001b820`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001b820`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x18001b5e0`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x18001b5e0`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x18001bcd9`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x18001bcd9`

## string_xrefs

- `0x18001bc5f`: `Failed to open PR_ATTACH_DATA_OBJ: %s`
- `0x18001bc83`: `Failed to open OpenAttach: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapi2RowFilter::EnumerateAttachments(CMapi2RowFilter *this, struct IMessage *a2, __int64 a3)
{
  struct IMessage *v3; // r12
  CMapi2RowFilter *v5; // rcx
  unsigned int v6; // eax
  int AttachmentTable; // edi
  __int64 v8; // r8
  int v9; // ecx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // ebx
  CMapi2Property *v13; // rsi
  int IsType; // eax
  LPSRowSet v15; // rcx
  ULONG v16; // r9d
  __int64 v17; // rdx
  unsigned int v18; // r8d
  LPSPropValue lpProps; // r14
  BOOL v20; // r13d
  ULONG ulPropTag; // eax
  int v22; // r12d
  _QWORD *URL; // rax
  __int64 v24; // rbx
  CURRENCY cur; // rdx
  _QWORD *v26; // rcx
  const WCHAR *v27; // rcx
  int v28; // eax
  void *v29; // rax
  struct IMessage *v30; // rax
  CMapi2Property *v31; // rax
  CMapi2Accessor *v32; // rbx
  struct CMapiUrl *v33; // rax
  int v34; // r12d
  char v35; // bl
  HRESULT v36; // eax
  const struct _GUID *v37; // rdx
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // r14
  __int64 v41; // r8
  const wchar_t *v42; // rcx
  const wchar_t *v43; // rdx
  CMapi2RowFilter *v44; // rdi
  wchar_t *v45; // rbx
  wchar_t *v47; // [rsp+20h] [rbp-E0h]
  LPSTREAM ppstm; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v51; // [rsp+58h] [rbp-A8h] BYREF
  int v52; // [rsp+5Ch] [rbp-A4h]
  ULONG v53; // [rsp+60h] [rbp-A0h]
  wchar_t *v54; // [rsp+68h] [rbp-98h] BYREF
  struct IMessage *v55; // [rsp+70h] [rbp-90h] BYREF
  LPSRowSet lpRows; // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  CMapi2Property *v58; // [rsp+88h] [rbp-78h] BYREF
  __int64 v59; // [rsp+90h] [rbp-70h] BYREF
  struct IMAPITable *v60; // [rsp+98h] [rbp-68h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h] BYREF
  struct IMessage *v63; // [rsp+B0h] [rbp-50h]
  CMapi2RowFilter *v64; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  _DWORD v67[4]; // [rsp+D0h] [rbp-30h] BYREF
  void *v68; // [rsp+E0h] [rbp-20h]
  _BYTE v69[24]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v70[12]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v71[88]; // [rsp+160h] [rbp+60h] BYREF
  _DWORD v72[4]; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _SPropTagArray v73; // [rsp+1C8h] [rbp+C8h] BYREF
  int v74; // [rsp+1D0h] [rbp+D0h]
  int v75; // [rsp+1D4h] [rbp+D4h]
  int v76; // [rsp+1D8h] [rbp+D8h]
  int v77; // [rsp+1DCh] [rbp+DCh]
  int v78; // [rsp+1E0h] [rbp+E0h]
  int v79; // [rsp+1E4h] [rbp+E4h]
  int v80; // [rsp+1E8h] [rbp+E8h]
  int v81; // [rsp+1ECh] [rbp+ECh]
  int v82; // [rsp+1F0h] [rbp+F0h]
  int v83; // [rsp+1F4h] [rbp+F4h]
  int v84; // [rsp+1F8h] [rbp+F8h]
  __int64 v85; // [rsp+200h] [rbp+100h] BYREF
  wchar_t *v86; // [rsp+208h] [rbp+108h]
  unsigned int v87; // [rsp+214h] [rbp+114h]
  void **v88; // [rsp+3A0h] [rbp+2A0h] BYREF
  wchar_t *v89; // [rsp+3A8h] [rbp+2A8h]
  __int64 v90; // [rsp+3B0h] [rbp+2B0h]
  __int16 v91; // [rsp+3B8h] [rbp+2B8h] BYREF
  char v92[8]; // [rsp+540h] [rbp+440h] BYREF
  wchar_t *v93; // [rsp+548h] [rbp+448h]
  int v94; // [rsp+554h] [rbp+454h]
  _BYTE v95[16]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v66 = a3;
  v3 = a2;
  v63 = a2;
  v49 = 0;
  LODWORD(ppstm) = 0;
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_EnumerateAttachments_Start,
      a3,
      1,
      v95);
  v51 = 0;
  v62 = *(_QWORD *)((char *)this + 21684);
  v73.cValues = 12;
  v73.aulPropTag[0] = 237043715;
  v74 = 267976962;
  v75 = 923205663;
  v76 = 923205662;
  v77 = 923009055;
  v78 = 923009054;
  v79 = 923074563;
  v80 = 2147352587;
  v81 = 2147418123;
  v82 = 924057603;
  v83 = 805371935;
  v84 = 805371934;
  v5 = (CMapi2RowFilter *)*((_QWORD *)this + 2645);
  if ( *((_DWORD *)v5 + 449) >= 0x64u )
    return 0;
  v6 = *((_DWORD *)v5 + 448);
  if ( v6 >= 0xA )
    return 0;
  *((_DWORD *)v5 + 448) = v6 + 1;
  v60 = 0;
  AttachmentTable = CMapi2RowFilter::GetAttachmentTable(v5, v3, &v73, &v60, &v51);
  if ( AttachmentTable >= 0
    && ((unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document") || *((_DWORD *)this + 5956))
    && v51 != 1 )
  {
    AttachmentTable = -2147467259;
    v9 = -2147467259;
  }
  else
  {
    v9 = AttachmentTable;
  }
  v10 = *((_QWORD *)this + 2645);
  v11 = (*(_DWORD *)(v10 + 516) & 1) == 0;
  v12 = *(_DWORD *)(v10 + 516) & 1;
  v52 = v12;
  LODWORD(ppstm) = v12;
  if ( v11 && v9 >= 0 )
  {
    AttachmentTable = CMapiSupport::CheckPolicy(L"PreventIndexingEmailAttachments", (int *)&ppstm, 1, 0);
    v9 = AttachmentTable;
    v12 = (int)ppstm;
    v52 = (int)ppstm;
  }
  lpRows = 0;
  v13 = 0;
  v58 = 0;
  if ( v9 >= 0 )
  {
LABEL_15:
    if ( v51 )
    {
      AttachmentTable = ((__int64 (__fastcall *)(struct IMAPITable *, __int64, _QWORD, LPSRowSet *))v60->lpVtbl->QueryRows)(
                          v60,
                          10,
                          0,
                          &lpRows);
      LODWORD(ppstm) = AttachmentTable;
      if ( AttachmentTable >= 0 )
      {
        if ( lpRows->cRows )
        {
          IsType = CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document");
          v15 = lpRows;
          if ( !IsType && !*((_DWORD *)this + 5956) || lpRows->cRows == 1 )
          {
            v16 = 0;
            v53 = 0;
            while ( 1 )
            {
              if ( v16 >= v15->cRows || (v17 = *((_QWORD *)this + 2645), v18 = *(_DWORD *)(v17 + 1796), v18 >= 0x64) )
              {
                v51 -= v15->cRows;
                FreeProws(v15);
                lpRows = 0;
                goto LABEL_15;
              }
              lpProps = v15->aRow[v16].lpProps;
              *(_DWORD *)(v17 + 1796) = v18 + 1;
              v20 = 0;
              if ( (lpProps[7].ulPropTag != 2147352587 || !lpProps[7].Value.i)
                && (lpProps[8].ulPropTag != 2147418123 || !lpProps[8].Value.i)
                && (lpProps[9].ulPropTag != 924057603 || (LOBYTE(lpProps[9].Value.flt) & 4) == 0) )
              {
                break;
              }
LABEL_139:
              v53 = ++v16;
              v15 = lpRows;
            }
            ulPropTag = lpProps[6].ulPropTag;
            if ( ulPropTag == 923074563 && lpProps[6].Value.l == 1 )
            {
              v22 = 1;
              CMapiUrl::CMapiUrl((CMapiUrl *)v70, *((const wchar_t **)this + 2647));
              URL = CMapiUrl::GetURL(v70, &v65);
              TLMString<192,64,32767>::TLMString<192,64,32767>(&v85, *URL);
              ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
              TLMString<192,64,32767>::TLMString<192,64,32767>(v92, &byte_1800444C0);
              (*(void (__fastcall **)(__int64 *, const wchar_t *, _QWORD, __int64))(v85 + 32))(
                &v85,
                L"/AT=",
                v87,
                0xFFFFFFFFLL);
              if ( lpProps[1].ulPropTag != 267976962 )
              {
LABEL_47:
                v57 = 0;
                if ( AttachmentTable >= 0 )
                {
                  AttachmentTable = -2147467259;
                  if ( lpProps->ulPropTag == 237043715 )
                  {
                    AttachmentTable = ((__int64 (__fastcall *)(struct IMessage *, _QWORD, _QWORD, __int64, __int64 *))v63->lpVtbl->get_Keywords)(
                                        v63,
                                        lpProps->Value.ul,
                                        0,
                                        8,
                                        &v57);
                    if ( AttachmentTable >= 0 )
                    {
                      LODWORD(ppstm) = 0;
                      pv = 0;
                      v72[0] = 2;
                      v72[1] = 805830720;
                      v72[2] = 923664415;
                      AttachmentTable = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, LPSTREAM *, LPVOID *))(*(_QWORD *)v57 + 40LL))(
                                          v57,
                                          v72,
                                          0,
                                          &ppstm,
                                          &pv);
                      if ( AttachmentTable >= 0 )
                      {
                        v26 = pv;
                        if ( *((_DWORD *)this + 5956) && *((_DWORD *)pv + 6) == 923664415 )
                        {
                          v27 = (const WCHAR *)*((_QWORD *)pv + 4);
                          if ( v22 )
                            v28 = StrCmpNIW(v27, L"multipart/signed", 17);
                          else
                            v28 = StrCmpNIA((PCSTR)v27, "multipart/signed", 17);
                          v20 = v28 != 0;
                          v26 = pv;
                        }
                        if ( *(_DWORD *)v26 == 805830720 )
                          v62 = v26[1];
                        MAPIFreeBuffer(v26);
                      }
                    }
                  }
                }
                if ( !*((_DWORD *)this + 5951)
                  && !(unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document")
                  && !*((_DWORD *)this + 5956) )
                {
                  v29 = operator new(0x1A8u, (const struct std::nothrow_t *)&std::nothrow);
                  v68 = v29;
                  if ( v29 )
                    v30 = (struct IMessage *)CLinkWithTime::CLinkWithTime(v29, &v85, &v62);
                  else
                    v30 = 0;
                  v55 = v30;
                  if ( v30 )
                  {
                    CTPtrSList<CLinkWithTime>::Append((char *)this + 23912, v30);
                    v55 = 0;
                  }
                  TPointer<CLinkWithTime>::~TPointer<CLinkWithTime>(&v55);
                }
                if ( !(unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document")
                  && !*((_DWORD *)this + 5956)
                  && v94 )
                {
                  if ( !v13 )
                  {
                    v31 = (CMapi2Property *)operator new(0x868u, (const struct std::nothrow_t *)&std::nothrow);
                    v13 = v31;
                    v55 = (struct IMessage *)v31;
                    if ( v31 )
                    {
                      *((_QWORD *)v31 + 3) = (char *)v31 + 40;
                      *((_QWORD *)v31 + 4) = 1025;
                      *((_WORD *)v31 + 20) = 0;
                      *((_QWORD *)v31 + 2) = &TLMString<1024,1024,1048576>::`vftable';
                      *((_QWORD *)v31 + 266) = (char *)v31 + 2128;
                      *((_QWORD *)v31 + 265) = (char *)v31 + 2128;
                      *((_QWORD *)v31 + 267) = (char *)v31 + 2120;
                      *((_DWORD *)v31 + 536) = 0;
                      *((_QWORD *)v31 + 264) = &CTPtrSListContainer<TLMString<1024,1024,1048576>>::`vftable';
                      *(_QWORD *)v31 = g_mfpsCommunication_AttachmentNames;
                      *((_DWORD *)v31 + 2) = 0;
                      v58 = v31;
                    }
                    else
                    {
                      v13 = 0;
                      v58 = 0;
                      AttachmentTable = -2147024882;
                    }
                  }
                  if ( AttachmentTable < 0 )
                    goto LABEL_82;
                  AttachmentTable = CMapi2Property::AppendMultiValue(v13, v93);
                }
                if ( AttachmentTable >= 0 && !v52 )
                {
                  v32 = (CMapi2Accessor *)*((_QWORD *)this + 2645);
                  v33 = CMapiUrl::CMapiUrl((CMapiUrl *)v71, v86);
                  v34 = v49 | 1;
                  v49 = v34;
                  LODWORD(ppstm) = v34;
                  if ( (int)CMapi2Accessor::IsAttachmentOK(v32, v33) >= 0 )
                  {
                    v35 = 1;
LABEL_84:
                    if ( (v34 & 1) != 0 )
                    {
                      v49 = v34 & 0xFFFFFFFE;
                      CMapiUrl::~CMapiUrl((CMapiUrl *)v71);
                    }
                    if ( v35 )
                    {
                      ppstm = 0;
                      if ( AttachmentTable >= 0 )
                      {
                        LODWORD(v47) = 0;
                        v36 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _QWORD, wchar_t *, LPSTREAM *))(*(_QWORD *)v57 + 56LL))(
                                v57,
                                922812674,
                                &IID_IStream,
                                0,
                                v47,
                                &ppstm);
                        AttachmentTable = v36;
                        if ( v36 >= 0 )
                        {
                          if ( v20 )
                          {
                            pv = 0;
                            AttachmentTable = CBlobSignedFilterStreamWrapper::CreateInstanceWithStream(ppstm, v37, &pv);
                            if ( AttachmentTable >= 0 )
                              TComPointer<IFilter>::operator=(&ppstm, pv);
                            TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&pv);
                            v36 = AttachmentTable;
                          }
                        }
                        else
                        {
                          v36 = CreateStreamOnHGlobal(0, 1, &ppstm);
                          AttachmentTable = v36;
                        }
                        if ( v36 >= 0 )
                        {
                          v89 = (wchar_t *)&v91;
                          v90 = 129;
                          v91 = 0;
                          v88 = &TLMString<128,128,8192>::`vftable';
                          v38 = CLMString::ReverseFind((CLMString *)v92, (wchar_t)v37);
                          v39 = v38;
                          if ( v38 >= 0 )
                          {
                            CLMString::Mid(v92, v69, (unsigned int)(v38 + 1), (unsigned int)(v94 - (v38 + 1)));
                            CLMString::operator=(&v88, v69);
                          }
                          if ( ((unsigned int)CMapi2RowFilter::IsType(this, L"MAPI/IPM.Document")
                             || *((_DWORD *)this + 5956))
                            && !v53 )
                          {
                            if ( *((_DWORD *)this + 5956) && !HIDWORD(v90) )
                              CLMString::operator=(&v88, L"p7m");
                            CMapi2RowFilter::AddAttachmentChildFilter(
                              this,
                              0,
                              ppstm,
                              v89,
                              v86,
                              (const struct CMapi2FullPropSpec *)g_mfpsSearch_Contents);
                            v40 = v66;
                            if ( v66 )
                            {
                              CLMString::Mid(v92, v95, v39, v94 - v39);
                              CLMString::operator=(v40, v95);
                            }
                          }
                          else if ( !*((_DWORD *)this + 5952) || *(_DWORD *)(*((_QWORD *)this + 2645) + 1792LL) > 1u )
                          {
                            CMapi2RowFilter::AddAttachmentChildFilter(
                              this,
                              0,
                              ppstm,
                              v89,
                              v86,
                              (const struct CMapi2FullPropSpec *)g_mfpsMessage_AttachmentContents);
                          }
                          TLMString<128,128,8192>::~TLMString<128,128,8192>(&v88);
                        }
                      }
                      TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&ppstm);
                    }
                    if ( AttachmentTable < 0 )
                      CLogger::Error(AttachmentTable, L"Failed to index attachment: %s", v93);
                    TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v57);
                    TLMString<192,64,32767>::~TLMString<192,64,32767>(v92);
                    TLMString<192,64,32767>::~TLMString<192,64,32767>(&v85);
                    CMapiUrl::~CMapiUrl((CMapiUrl *)v70);
                    v16 = v53;
                    v12 = v52;
                    v3 = v63;
                    goto LABEL_138;
                  }
LABEL_83:
                  v35 = 0;
                  goto LABEL_84;
                }
LABEL_82:
                v34 = v49;
                goto LABEL_83;
              }
              CEntryId::CEntryId((CEntryId *)v67, lpProps + 1, (int *)&ppstm);
              AttachmentTable = (int)ppstm;
              if ( (int)ppstm < 0 )
              {
LABEL_46:
                CEntryId::FreeBuffer((CEntryId *)v67);
                v67[0] = 0;
                goto LABEL_47;
              }
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v61);
              CEntryId::ToByte(v67, &v61);
              v24 = v61;
              (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64))(v85 + 32))(&v85, v61, v87, 0xFFFFFFFFLL);
              (*(void (__fastcall **)(__int64 *, const wchar_t *, _QWORD, __int64))(v85 + 32))(
                &v85,
                L":",
                v87,
                0xFFFFFFFFLL);
              if ( lpProps[2].ulPropTag == 923205663 )
              {
                (*(void (__fastcall **)(__int64 *, CURRENCY, _QWORD, __int64))(v85 + 32))(
                  &v85,
                  lpProps[2].Value.cur,
                  v87,
                  0xFFFFFFFFLL);
                cur = lpProps[2].Value.cur;
LABEL_40:
                ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(v92, (CURRENCY)cur.int64);
LABEL_45:
                ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
                goto LABEL_46;
              }
              if ( lpProps[3].ulPropTag == 923205662 )
              {
                (*(void (__fastcall **)(__int64 *, CURRENCY, _QWORD, __int64))(v85 + 24))(
                  &v85,
                  lpProps[3].Value.cur,
                  v87,
                  0xFFFFFFFFLL);
                ((void (__fastcall *)(_QWORD, _QWORD))TLMString<192,64,32767>::TLMString<192,64,32767>)(
                  &v88,
                  (CURRENCY)lpProps[3].Value.cur.int64);
                CLMString::operator=(v92, v89);
              }
              else
              {
                if ( lpProps[4].ulPropTag == 923009055 )
                {
                  (*(void (__fastcall **)(__int64 *, CURRENCY, _QWORD, __int64))(v85 + 32))(
                    &v85,
                    lpProps[4].Value.cur,
                    v87,
                    0xFFFFFFFFLL);
                  cur = lpProps[4].Value.cur;
                  goto LABEL_40;
                }
                if ( lpProps[5].ulPropTag != 923009054 )
                {
                  (*(void (__fastcall **)(__int64 *, const wchar_t *, _QWORD, __int64))(v85 + 32))(
                    &v85,
                    L"(no filename)",
                    v87,
                    0xFFFFFFFFLL);
                  goto LABEL_45;
                }
                (*(void (__fastcall **)(__int64 *, CURRENCY, _QWORD, __int64))(v85 + 24))(
                  &v85,
                  lpProps[5].Value.cur,
                  v87,
                  0xFFFFFFFFLL);
                ((void (__fastcall *)(_QWORD, _QWORD))TLMString<192,64,32767>::TLMString<192,64,32767>)(
                  &v88,
                  (CURRENCY)lpProps[5].Value.cur.int64);
                CLMString::operator=(v92, v89);
              }
              TLMString<192,64,32767>::~TLMString<192,64,32767>(&v88);
              v22 = 0;
              goto LABEL_45;
            }
            if ( v12 || ulPropTag != 923074563 || lpProps[6].Value.l != 5 )
            {
LABEL_138:
              AttachmentTable = 0;
              LODWORD(ppstm) = 0;
              goto LABEL_139;
            }
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v54);
            if ( CLogger::m_fLoggingEnabled )
            {
              if ( lpProps[10].ulPropTag == 805371935 )
              {
                v41 = (unsigned int)ocslen(lpProps[10].Value.lpszW);
                v43 = v42;
              }
              else
              {
                if ( lpProps[11].ulPropTag == 805371934 )
                {
                  ((void (__fastcall *)(_QWORD, _QWORD))ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=)(
                    &v54,
                    (CURRENCY)lpProps[11].Value.cur.int64);
                  goto LABEL_123;
                }
                v41 = 8;
                v43 = L"Untitled";
              }
              ATL::CSimpleStringT<wchar_t,0>::SetString(&v54, v43, v41);
            }
LABEL_123:
            v59 = 0;
            if ( lpProps->ulPropTag == 237043715
              && ((int (__fastcall *)(struct IMessage *, _QWORD, _QWORD, __int64, __int64 *))v3->lpVtbl->get_Keywords)(
                   v3,
                   lpProps->Value.ul,
                   0,
                   24,
                   &v59) >= 0 )
            {
              v55 = 0;
              LODWORD(v47) = 8;
              if ( (*(int (__fastcall **)(__int64, __int64, GUID *, _QWORD, wchar_t *, struct IMessage **))(*(_QWORD *)v59 + 56LL))(
                     v59,
                     922812429,
                     &IID_IMessage,
                     0,
                     v47,
                     &v55) < 0 )
              {
                v45 = v54;
                CLogger::Error(L"Failed to open PR_ATTACH_DATA_OBJ: %s", v54);
              }
              else
              {
                pv = 0;
                ppstm = 0;
                if ( (int)ATL::CComObject<CMapi2RowFilter>::CreateInstance(&pv) < 0 )
                {
                  v45 = v54;
                  CLogger::Error(pv != 0 ? -2147467259 : -2147024882, L"Failed to index attachment: %s", v54);
                }
                else
                {
                  TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(&v64, pv);
                  v44 = v64;
                  if ( (int)CMapi2RowFilter::InitRowFilter(v64, *((struct CMapi2Accessor **)this + 2645), v55) < 0
                    || (**(int (__fastcall ***)(CMapi2RowFilter *, GUID *, LPSTREAM *))v44)(v44, &IID_IFilter, &ppstm) < 0 )
                  {
                    v45 = v54;
                    CLogger::Error(v44 != 0 ? -2147467259 : -2147024882, L"Failed to index attachment: %s", v54);
                  }
                  else
                  {
                    v45 = v54;
                    CMapi2RowFilter::AddAttachmentChildFilter(
                      this,
                      (struct IFilter *)ppstm,
                      0,
                      0,
                      v54,
                      (const struct CMapi2FullPropSpec *)g_mfpsMessage_AttachmentContents);
                  }
                  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v64);
                }
                TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&ppstm);
              }
              TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v55);
            }
            else
            {
              v45 = v54;
              CLogger::Error(L"Failed to open OpenAttach: %s", v54);
            }
            TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v59);
            ATL::CStringData::Release((ATL::CStringData *)(v45 - 12));
            v16 = v53;
            v12 = v52;
            goto LABEL_138;
          }
          AttachmentTable = -2147467259;
          goto LABEL_146;
        }
        AttachmentTable = -2147216895;
      }
    }
  }
  if ( AttachmentTable >= 0 && v13 )
  {
    CTPtrSList<CLinkWithTime>::Append((char *)this + 23848, v13);
    v58 = 0;
  }
LABEL_146:
  --*(_DWORD *)(*((_QWORD *)this + 2645) + 1792LL);
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_EnumerateAttachments_Stop,
      v8,
      1,
      v95);
  TPointer<CMapi2Property>::~TPointer<CMapi2Property>(&v58);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v60);
  return (unsigned int)AttachmentTable;
}

```

## disassembly

```asm
0x18001afa8  mov     [rsp-8+arg_18], rbx
0x18001afad  push    rbp
0x18001afae  push    rsi
0x18001afaf  push    rdi
0x18001afb0  push    r12
0x18001afb2  push    r13
0x18001afb4  push    r14
0x18001afb6  push    r15
0x18001afb8  lea     rbp, [rsp-600h]
0x18001afc0  sub     rsp, 700h
0x18001afc7  mov     rax, cs:__security_cookie
0x18001afce  xor     rax, rsp
0x18001afd1  mov     [rbp+630h+var_40], rax
0x18001afd8  mov     [rbp+630h+var_668], r8
0x18001afdc  mov     r12, rdx
0x18001afdf  mov     [rbp+630h+var_680], rdx
0x18001afe3  mov     r15, rcx
0x18001afe6  xor     r14d, r14d
0x18001afe9  mov     eax, r14d
0x18001afec  mov     [rsp+730h+var_6E8], eax
0x18001aff0  mov     dword ptr [rsp+730h+ppstm], eax
0x18001aff4  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 4
0x18001affb  jz      short loc_18001B020
0x18001affd  lea     rax, [rbp+630h+var_50]
0x18001b004  mov     [rsp+730h+var_710], rax
0x18001b009  lea     r9d, [r14+1]
0x18001b00d  lea     rdx, MSSearchTraceId_EnumerateAttachments_Start
0x18001b014  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18001b01b  call    McGenEventWrite_EventWriteTransfer
0x18001b020  mov     [rsp+730h+var_6D8], r14d
0x18001b025  mov     rax, [r15+54B4h]
0x18001b02c  mov     [rbp+630h+var_688], rax
0x18001b030  mov     [rbp+630h+var_568.cValues], 0Ch
0x18001b03a  mov     [rbp+630h+var_568.aulPropTag], 0E210003h
0x18001b044  mov     [rbp+630h+var_560], 0FF90102h
0x18001b04e  mov     [rbp+630h+var_55C], 3707001Fh
0x18001b058  mov     [rbp+630h+var_558], 3707001Eh
0x18001b062  mov     [rbp+630h+var_554], 3704001Fh
0x18001b06c  mov     [rbp+630h+var_550], 3704001Eh
0x18001b076  mov     [rbp+630h+var_54C], 37050003h
0x18001b080  mov     [rbp+630h+var_548], 7FFE000Bh
0x18001b08a  mov     [rbp+630h+var_544], 7FFF000Bh
0x18001b094  mov     [rbp+630h+var_540], 37140003h
0x18001b09e  mov     [rbp+630h+var_53C], 3001001Fh
0x18001b0a8  mov     [rbp+630h+var_538], 3001001Eh
0x18001b0b2  mov     rcx, [r15+52A8h]; this
0x18001b0b9  cmp     dword ptr [rcx+704h], 64h ; 'd'
0x18001b0c0  jnb     loc_18001BD69
0x18001b0c6  mov     eax, [rcx+700h]
0x18001b0cc  cmp     eax, 0Ah
0x18001b0cf  jnb     loc_18001BD69
0x18001b0d5  inc     eax
0x18001b0d7  mov     [rcx+700h], eax
0x18001b0dd  mov     [rbp+630h+var_698], r14
0x18001b0e1  lea     rax, [rsp+730h+var_6D8]
0x18001b0e6  mov     [rsp+730h+var_710], rax; unsigned int *
0x18001b0eb  lea     r9, [rbp+630h+var_698]; struct IMAPITable **
0x18001b0ef  lea     r8, [rbp+630h+var_568]; struct _SPropTagArray *
0x18001b0f6  mov     rdx, r12; struct IMessage *
0x18001b0f9  call    ?GetAttachmentTable@CMapi2RowFilter@@AEAAJPEAUIMessage@@PEAU_SPropTagArray@@PEAPEAUIMAPITable@@PEAK@Z; CMapi2RowFilter::GetAttachmentTable(IMessage *,_SPropTagArray *,IMAPITable * *,ulong *)
0x18001b0fe  mov     edi, eax
0x18001b100  mov     r13d, 80004005h
0x18001b106  test    eax, eax
0x18001b108  js      short loc_18001B135
0x18001b10a  lea     rdx, aMapiIpmDocumen; "MAPI/IPM.Document"
0x18001b111  mov     rcx, r15; this
0x18001b114  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001b119  test    eax, eax
0x18001b11b  jnz     short loc_18001B126
0x18001b11d  cmp     [r15+5D10h], r14d
0x18001b124  jz      short loc_18001B135
0x18001b126  cmp     [rsp+730h+var_6D8], 1
0x18001b12b  jz      short loc_18001B135
0x18001b12d  mov     edi, r13d
0x18001b130  mov     ecx, r13d
0x18001b133  jmp     short loc_18001B137
0x18001b135  mov     ecx, edi
0x18001b137  mov     rax, [r15+52A8h]
0x18001b13e  mov     ebx, [rax+204h]
0x18001b144  and     ebx, 1
0x18001b147  mov     [rsp+730h+var_6D4], ebx
0x18001b14b  mov     dword ptr [rsp+730h+ppstm], ebx
0x18001b14f  jnz     short loc_18001B179
0x18001b151  test    ecx, ecx
0x18001b153  js      short loc_18001B179
0x18001b155  xor     r9d, r9d; int
0x18001b158  lea     r8d, [r9+1]; int
0x18001b15c  lea     rdx, [rsp+730h+ppstm]; int *
0x18001b161  lea     rcx, aPreventindexin_0; "PreventIndexingEmailAttachments"
0x18001b168  call    ?CheckPolicy@CMapiSupport@@SAJPEB_WPEAHHH@Z; CMapiSupport::CheckPolicy(wchar_t const *,int *,int,int)
0x18001b16d  mov     edi, eax
0x18001b16f  mov     ecx, eax
0x18001b171  mov     ebx, dword ptr [rsp+730h+ppstm]
0x18001b175  mov     [rsp+730h+var_6D4], ebx
0x18001b179  mov     [rsp+730h+lpRows], r14
0x18001b17e  mov     rsi, r14
0x18001b181  mov     [rbp+630h+var_6A8], r14
0x18001b185  test    ecx, ecx
0x18001b187  js      loc_18001BCFA
0x18001b18d  cmp     [rsp+730h+var_6D8], r14d
0x18001b192  jbe     loc_18001BCFA
0x18001b198  mov     rcx, [rbp+630h+var_698]
0x18001b19c  mov     rax, [rcx]
0x18001b19f  lea     r9, [rsp+730h+lpRows]
0x18001b1a4  xor     r8d, r8d
0x18001b1a7  lea     edx, [r8+0Ah]
0x18001b1ab  mov     rax, [rax+98h]
0x18001b1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1b7  mov     edi, eax
0x18001b1b9  mov     dword ptr [rsp+730h+ppstm], eax
0x18001b1bd  test    eax, eax
0x18001b1bf  js      loc_18001BCFA
0x18001b1c5  mov     rax, [rsp+730h+lpRows]
0x18001b1ca  cmp     [rax], r14d
0x18001b1cd  jz      loc_18001BCF5
0x18001b1d3  lea     rdx, aMapiIpmDocumen; "MAPI/IPM.Document"
0x18001b1da  mov     rcx, r15; this
0x18001b1dd  call    ?IsType@CMapi2RowFilter@@AEAAHPEB_W@Z; CMapi2RowFilter::IsType(wchar_t const *)
0x18001b1e2  mov     rcx, [rsp+730h+lpRows]
0x18001b1e7  test    eax, eax
0x18001b1e9  jnz     short loc_18001B1F4
0x18001b1eb  cmp     [r15+5D10h], r14d
0x18001b1f2  jz      short loc_18001B1FD
0x18001b1f4  cmp     dword ptr [rcx], 1
0x18001b1f7  jnz     loc_18001BCEE
0x18001b1fd  mov     r9d, r14d
0x18001b200  mov     [rsp+730h+var_6D0], r14d
0x18001b205  cmp     r9d, [rcx]
0x18001b208  jnb     loc_18001BCD3
0x18001b20e  mov     rdx, [r15+52A8h]
0x18001b215  mov     r8d, [rdx+704h]
0x18001b21c  cmp     r8d, 64h ; 'd'
0x18001b220  jnb     loc_18001BCD3
0x18001b226  mov     eax, r9d
0x18001b229  inc     rax
0x18001b22c  add     rax, rax
0x18001b22f  mov     r14, [rcx+rax*8]
0x18001b233  lea     eax, [r8+1]
0x18001b237  mov     [rdx+704h], eax
0x18001b23d  xor     r13d, r13d
0x18001b240  cmp     dword ptr [r14+0A8h], 7FFE000Bh
0x18001b24b  jnz     short loc_18001B25B
0x18001b24d  cmp     [r14+0B0h], r13w
0x18001b255  jnz     loc_18001BCBB
0x18001b25b  cmp     dword ptr [r14+0C0h], 7FFF000Bh
0x18001b266  jnz     short loc_18001B276
0x18001b268  cmp     [r14+0C8h], r13w
0x18001b270  jnz     loc_18001BCBB
0x18001b276  cmp     dword ptr [r14+0D8h], 37140003h
0x18001b281  jnz     short loc_18001B291
0x18001b283  test    byte ptr [r14+0E0h], 4
0x18001b28b  jnz     loc_18001BCBB
0x18001b291  mov     eax, [r14+90h]
0x18001b298  mov     ecx, 37050003h
0x18001b29d  cmp     eax, ecx
0x18001b29f  jnz     loc_18001BA55
0x18001b2a5  cmp     dword ptr [r14+98h], 1
0x18001b2ad  jnz     loc_18001BA55
0x18001b2b3  mov     r12d, 1
0x18001b2b9  mov     rdx, [r15+52B8h]; wchar_t *
0x18001b2c0  lea     rcx, [rbp+630h+var_630]; this
0x18001b2c4  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x18001b2c9  nop
0x18001b2ca  lea     rdx, [rbp+630h+var_670]
0x18001b2ce  lea     rcx, [rbp+630h+var_630]
0x18001b2d2  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x18001b2d7  nop
0x18001b2d8  mov     rdx, [rax]
0x18001b2db  lea     rcx, [rbp+630h+var_530]
0x18001b2e2  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(wchar_t const *)
0x18001b2e7  nop
0x18001b2e8  mov     rcx, [rbp+630h+var_670]
0x18001b2ec  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b2f0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b2f5  lea     rdx, byte_1800444C0
0x18001b2fc  lea     rcx, [rbp+630h+var_1F0]
0x18001b303  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEBD@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(char const *)
0x18001b308  nop
0x18001b309  mov     rax, [rbp+630h+var_530]
0x18001b310  or      ebx, 0FFFFFFFFh
0x18001b313  mov     r9d, ebx
0x18001b316  mov     r8d, [rbp+630h+var_51C]
0x18001b31d  lea     rdx, aAt; "/AT="
0x18001b324  lea     rcx, [rbp+630h+var_530]
0x18001b32b  mov     rax, [rax+20h]
0x18001b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b334  test    edi, edi
0x18001b336  js      loc_18001B4EA
0x18001b33c  lea     rdx, [r14+18h]; struct _SPropValue *
0x18001b340  cmp     dword ptr [rdx], 0FF90102h
0x18001b346  jnz     loc_18001B4EA
0x18001b34c  lea     r8, [rsp+730h+ppstm]; int *
0x18001b351  lea     rcx, [rbp+630h+var_660]; this
0x18001b355  call    ??0CEntryId@@QEAA@PEAU_SPropValue@@PEAJ@Z; CEntryId::CEntryId(_SPropValue *,long *)
0x18001b35a  nop
0x18001b35b  mov     edi, dword ptr [rsp+730h+ppstm]
0x18001b35f  test    edi, edi
0x18001b361  js      loc_18001B4DA
0x18001b367  lea     rcx, [rbp+630h+var_690]
0x18001b36b  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18001b370  nop
0x18001b371  lea     rdx, [rbp+630h+var_690]
0x18001b375  lea     rcx, [rbp+630h+var_660]
0x18001b379  call    ?ToByte@CEntryId@@QEAAXAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CEntryId::ToByte(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18001b37e  mov     rax, [rbp+630h+var_530]
0x18001b385  mov     r9d, ebx
0x18001b388  mov     r8d, [rbp+630h+var_51C]
0x18001b38f  mov     rbx, [rbp+630h+var_690]
0x18001b393  mov     rdx, rbx
0x18001b396  lea     rcx, [rbp+630h+var_530]
0x18001b39d  mov     rax, [rax+20h]
0x18001b3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3a6  mov     rax, [rbp+630h+var_530]
0x18001b3ad  or      r9d, 0FFFFFFFFh
0x18001b3b1  mov     r8d, [rbp+630h+var_51C]
0x18001b3b8  lea     rdx, asc_180047DF8; ":"
0x18001b3bf  lea     rcx, [rbp+630h+var_530]
0x18001b3c6  mov     rax, [rax+20h]
0x18001b3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3cf  mov     rax, [rbp+630h+var_530]
0x18001b3d6  or      r9d, 0FFFFFFFFh
0x18001b3da  mov     r8d, [rbp+630h+var_51C]
0x18001b3e1  lea     rcx, [rbp+630h+var_530]
0x18001b3e8  cmp     dword ptr [r14+30h], 3707001Fh
0x18001b3f0  jnz     short loc_18001B405
0x18001b3f2  mov     rdx, [r14+38h]
0x18001b3f6  mov     rax, [rax+20h]
0x18001b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3ff  mov     rdx, [r14+38h]
0x18001b403  jmp     short loc_18001B45E
0x18001b405  cmp     dword ptr [r14+48h], 3707001Eh
0x18001b40d  jnz     short loc_18001B443
0x18001b40f  mov     rdx, [r14+50h]
0x18001b413  mov     rax, [rax+18h]
0x18001b417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b41c  mov     rdx, [r14+50h]
0x18001b420  lea     rcx, [rbp+630h+var_390]
0x18001b427  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEBD@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(char const *)
0x18001b42c  nop
0x18001b42d  mov     rdx, [rbp+630h+var_388]
0x18001b434  lea     rcx, [rbp+630h+var_1F0]
0x18001b43b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001b440  nop
0x18001b441  jmp     short loc_18001B4AE
0x18001b443  cmp     dword ptr [r14+60h], 3704001Fh
0x18001b44b  jnz     short loc_18001B46C
0x18001b44d  mov     rdx, [r14+68h]
0x18001b451  mov     rax, [rax+20h]
0x18001b455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b45a  mov     rdx, [r14+68h]
0x18001b45e  lea     rcx, [rbp+630h+var_1F0]
0x18001b465  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001b46a  jmp     short loc_18001B4D0
0x18001b46c  cmp     dword ptr [r14+78h], 3704001Eh
0x18001b474  jnz     short loc_18001B4BF
0x18001b476  mov     rdx, [r14+80h]
0x18001b47d  mov     rax, [rax+18h]
0x18001b481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b486  mov     rdx, [r14+80h]
0x18001b48d  lea     rcx, [rbp+630h+var_390]
0x18001b494  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@PEBD@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(char const *)
0x18001b499  nop
0x18001b49a  mov     rdx, [rbp+630h+var_388]
0x18001b4a1  lea     rcx, [rbp+630h+var_1F0]
0x18001b4a8  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001b4ad  nop
0x18001b4ae  lea     rcx, [rbp+630h+var_390]
0x18001b4b5  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x18001b4ba  xor     r12d, r12d
0x18001b4bd  jmp     short loc_18001B4D0
0x18001b4bf  lea     rdx, aNoFilename; "(no filename)"
0x18001b4c6  mov     rax, [rax+20h]
0x18001b4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4cf  nop
0x18001b4d0  lea     rcx, [rbx-18h]; this
0x18001b4d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b4d9  nop
0x18001b4da  lea     rcx, [rbp+630h+var_660]; this
0x18001b4de  call    ?FreeBuffer@CEntryId@@AEAAXXZ; CEntryId::FreeBuffer(void)
0x18001b4e3  mov     [rbp+630h+var_660], 0
0x18001b4ea  mov     [rbp+630h+var_6B0], 0
0x18001b4f2  test    edi, edi
0x18001b4f4  js      loc_18001B5FF
0x18001b4fa  mov     edi, 80004005h
0x18001b4ff  cmp     dword ptr [r14], 0E210003h
0x18001b506  jnz     loc_18001B5FF
0x18001b50c  mov     rcx, [rbp+630h+var_680]
0x18001b510  mov     rax, [rcx]
0x18001b513  lea     rdx, [rbp+630h+var_6B0]
0x18001b517  mov     [rsp+730h+var_710], rdx
0x18001b51c  mov     r9d, 8
0x18001b522  xor     r8d, r8d
0x18001b525  mov     edx, [r14+8]
0x18001b529  mov     rax, [rax+78h]
0x18001b52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b532  mov     edi, eax
0x18001b534  xor     r14d, r14d
0x18001b537  test    eax, eax
0x18001b539  js      loc_18001B602
0x18001b53f  mov     dword ptr [rsp+730h+ppstm], r14d
  ... truncated ...
```
