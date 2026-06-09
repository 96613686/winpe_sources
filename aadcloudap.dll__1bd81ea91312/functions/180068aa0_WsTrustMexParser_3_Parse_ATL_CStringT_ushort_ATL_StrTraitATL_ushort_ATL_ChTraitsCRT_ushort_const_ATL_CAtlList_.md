# WsTrustMexParser<3>::Parse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<WsTrustUrl,ATL::CElementTraits<WsTrustUrl>> &)

- ea: `0x180068aa0`
- end: `0x180069406`
- name: `?Parse@?$WsTrustMexParser@$02@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@UWsTrustUrl@@V?$CElementTraits@UWsTrustUrl@@@ATL@@@3@@Z`
- size: `2406`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069410`

## callees

- `0x1800065e8`
- `0x1800067f4`
- `0x18000685c`
- `0x1800090d0`
- `0x18000c7ac`
- `0x18000c884`
- `0x18001a128`
- `0x1800300d0`
- `0x1800399b8`
- `0x180039a50`
- `0x180039e70`
- `0x18003a368`
- `0x18003ad60`
- `0x18004b898`
- `0x180050598`
- `0x1800666f8`
- `0x180066750`
- `0x180066774`
- `0x180066804`
- `0x180066838`
- `0x180066c4c`
- `0x180066e24`
- `0x180067054`
- `0x180067570`
- `0x180068aa0`
- `0x18006967c`
- `0x180069a08`
- `0x180071e14`
- `0x1800844ec`
- `0x1800a3520`
- `0x1800a8010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180068d3f`
- `XmlLite!CreateXmlReader` at `0x180068d3f`

## string_xrefs

- `0x180068f23`: `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
- `0x180068f0e`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue`
- `0x180069175`: `/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:SignedSupportingTokens/wsp:Policy/sp2005:UsernameToken/wsp:Policy/sp2005:WssUsernameToken10`
- `0x180069157`: `/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:SignedEncryptedSupportingTokens/wsp:Policy/sp:UsernameToken/wsp:Policy/sp:WssUsernameToken10`
- `0x1800691ac`: `/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:EndorsingSupportingTokens/wsp:Policy/sp2005:X509Token/wsp:Policy/sp2005:WssX509V3Token10`
- `0x18006918e`: `/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:EndorsingSupportingTokens/wsp:Policy/sp:X509Token/wsp:Policy/sp:WssX509V3Token10`
- `0x180068c5d`: `/wsdl:definitions/wsdl:service/wsdl:port`
- `0x180068fb2`: `/wsdl:definitions/wsdl:service/wsdl:port`
- `0x180068ef6`: `http://schemas.xmlsoap.org/soap/http`
- `0x18006908b`: `/wsdl:definitions/wsdl:service/wsdl:port/wsa10:EndpointReference/wsa10:Address`

## pseudocode

```c
__int64 __fastcall WsTrustMexParser<3>::Parse(_QWORD *a1, __int64 a2)
{
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  int v7; // xmm4_4
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // xmm4_4
  HRESULT AttrValue; // edi
  wchar_t *v13; // rbx
  int v14; // r15d
  char v15; // r13
  int v16; // r14d
  HRESULT v17; // eax
  int *v18; // rax
  wchar_t **v19; // rcx
  _QWORD *v20; // rbx
  _QWORD *v21; // rax
  _QWORD *v22; // r12
  int *v23; // rcx
  int *v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rbx
  int v27; // eax
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // r12
  _QWORD *v31; // rcx
  int *v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rbx
  _QWORD *StartPosition; // rdi
  __int64 v36; // r12
  __int64 Node; // rax
  __int64 v38; // rax
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rax
  __int64 v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+30h] [rbp-D0h]
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvObject; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v56; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v57[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v58; // [rsp+C0h] [rbp-40h]
  int v59; // [rsp+C4h] [rbp-3Ch]
  int v60; // [rsp+C8h] [rbp-38h]
  int v61; // [rsp+CCh] [rbp-34h]
  __int64 v62; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  int v64; // [rsp+E0h] [rbp-20h]
  int v65; // [rsp+E4h] [rbp-1Ch]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h]
  const wchar_t *v68; // [rsp+100h] [rbp+0h]
  const wchar_t *v69; // [rsp+108h] [rbp+8h]
  _QWORD v70[16]; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v72[80]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v73[144]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v74; // [rsp+290h] [rbp+190h] BYREF
  __int64 v75; // [rsp+298h] [rbp+198h]
  __int64 v76; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v77; // [rsp+2A8h] [rbp+1A8h] BYREF

  v75 = a2;
  ppvObject = 0;
  v54 = 0;
  v76 = 0;
  v74 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&String1);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  v57[0] = 0;
  v57[1] = 0;
  v58 = 17;
  v62 = 0xFFFFFFFFLL;
  v63 = 0;
  v64 = 0;
  v65 = 10;
  v66 = 0;
  v67 = 0;
  v59 = 1061158912;
  v60 = 1048576000;
  v61 = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAutoPtr<CJsonValue>,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CAutoPtrElementTraits<CJsonValue>>::UpdateRehashThresholds(v57);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>(
    (unsigned int)v73,
    v4,
    v5,
    v6,
    v7);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>(
    (unsigned int)v72,
    v8,
    v9,
    v10,
    v11);
  v68 = L"/wsdl:definitions/wsp:Policy";
  v69 = L"wsu:Id";
  v70[0] = &v53;
  v70[1] = L"/wsdl:definitions/wsdl:binding";
  v70[2] = L"name";
  v70[3] = &v50;
  v70[4] = L"/wsdl:definitions/wsdl:binding/wsp:PolicyReference";
  v70[5] = L"URI";
  v70[6] = &v49;
  v70[7] = L"/wsdl:definitions/wsdl:binding/soap12:binding";
  v70[8] = L"transport";
  v70[9] = &v52;
  v70[10] = L"/wsdl:definitions/wsdl:binding/wsdl:operation/soap12:operation";
  v70[11] = L"soapAction";
  v70[12] = &v48;
  v70[13] = L"/wsdl:definitions/wsdl:service/wsdl:port";
  v70[14] = L"binding";
  v70[15] = &v47;
  if ( !*(_DWORD *)(*a1 - 16LL) )
  {
    AttrValue = -2147024809;
    v44 = 73;
LABEL_3:
    LODWORD(v43) = AttrValue;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v43, "wstrustmexparser.inl", v44, "HRESULT", &base);
    v13 = String1;
    goto LABEL_83;
  }
  ATL::CAtlList<WsTrustUrl,ATL::CElementTraits<WsTrustUrl>>::RemoveAll(a2);
  AttrValue = SequentialStream::FromString(a1, &v76);
  if ( AttrValue < 0 )
  {
    v44 = 79;
    goto LABEL_3;
  }
  ATL::CComPtrBase<ISequentialStream>::Attach(&v54, v76);
  AttrValue = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( AttrValue < 0 )
  {
    v44 = 83;
    goto LABEL_3;
  }
  AttrValue = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v54);
  if ( AttrValue < 0 )
  {
    v44 = 84;
    goto LABEL_3;
  }
  AttrValue = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( AttrValue < 0 )
  {
    v44 = 86;
    goto LABEL_3;
  }
  v14 = 0;
  v15 = 0;
  v16 = 0;
LABEL_13:
  v13 = String1;
  while ( 1 )
  {
    v17 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v74);
    AttrValue = v17;
    if ( v17 )
      break;
    switch ( v74 )
    {
      case 1:
        WsTrustBaseParser<WsTrustMexParser<3>,3>::UpdateCurrentPath(ppvObject, &String1, 1);
        v34 = 0;
        while ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                                &String1,
                                (&v68)[3 * v34]) )
        {
          v34 = (unsigned int)(v34 + 1);
          if ( (unsigned int)v34 >= 6 )
            goto LABEL_57;
        }
        AttrValue = WsTrustBaseParser<WsTrustMexParser<3>,3>::GetAttrValue(ppvObject, v70[3 * v34 - 1], v70[3 * v34]);
        if ( AttrValue < 0 )
        {
          v44 = 99;
          goto LABEL_3;
        }
LABEL_57:
        v13 = String1;
        if ( !wcscmp_0(
                String1,
                L"/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:SignedEncryptedSupportingTokens/wsp:Policy/sp:Use"
                 "rnameToken/wsp:Policy/sp:WssUsernameToken10") )
        {
          v16 = 1;
          goto LABEL_63;
        }
        if ( !wcscmp_0(
                v13,
                L"/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:SignedSupportingTokens/wsp:Policy/sp2005:User"
                 "nameToken/wsp:Policy/sp2005:WssUsernameToken10") )
        {
          v16 = 1;
          goto LABEL_66;
        }
        if ( !wcscmp_0(
                v13,
                L"/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:EndorsingSupportingTokens/wsp:Policy/sp:X509Token"
                 "/wsp:Policy/sp:WssX509V3Token10") )
        {
          v16 = 2;
LABEL_63:
          v14 = 3;
        }
        else if ( !wcscmp_0(
                     v13,
                     L"/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:EndorsingSupportingTokens/wsp:Policy/sp2"
                      "005:X509Token/wsp:Policy/sp2005:WssX509V3Token10") )
        {
          v16 = 2;
LABEL_66:
          v14 = 2;
        }
        else if ( !wcscmp_0(v13, L"/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:TransportBinding")
               || !wcscmp_0(v13, L"/wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:TransportBinding") )
        {
          v15 = 1;
        }
        if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
          continue;
        goto LABEL_71;
      case 3:
        if ( !wcscmp_0(v13, L"/wsdl:definitions/wsdl:service/wsdl:port/wsa10:EndpointReference/wsa10:Address") )
        {
          AttrValue = WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(ppvObject, &v51);
          if ( AttrValue < 0 )
          {
            LODWORD(v43) = AttrValue;
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v43, "wstrustmexparser.inl", 188, "HRESULT", &base);
            goto LABEL_83;
          }
        }
        break;
      case 15:
        if ( !wcscmp_0(v13, L"/wsdl:definitions/wsp:Policy") )
        {
          if ( *(_DWORD *)(v53 - 16) && v15 && v16 )
          {
            v18 = (int *)__A__CAtlMap_V__CStringT_GV__StrTraitATL_GV__ChTraitsCRT_G_ATL___ATL___ATL__UWsTrustPolicyId__1__Parse___WsTrustMexParser__02__SAJAEBV12_AEAV__CAtlList_UWsTrustUrl__V__CElementTraits_UWsTrustUrl___ATL___2__Z_V__CElementTraits_V__CStringT_GV__StrTraitATL_GV__ChTraitsCRT_G_ATL___ATL___ATL___2_V__CElementTraits_UWsTrustPolicyId__1__Parse___WsTrustMexParser__02__SAJAEBV__CStringT_GV__StrTraitATL_GV__ChTraitsCRT_G_ATL___ATL___ATL__AEAV__CAtlList_UWsTrustUrl__V__CElementTraits_UWsTrustUrl___ATL___5__Z__2__ATL__QEAAAEAUWsTrustPolicyId__1__Parse___WsTrustMexParser__02__SAJAEBV__CStringT_GV__StrTraitATL_GV__ChTraitsCRT_G_ATL___ATL___1_AEAV__CAtlList_UWsTrustUrl__V__CElementTraits_UWsTrustUrl___ATL___1__Z_PEBG_Z(v57);
            *v18 = v16;
            v18[1] = v14;
          }
          ATL::CSimpleStringT<unsigned short,0>::Empty(&v53);
          v16 = 0;
          v15 = 0;
          v14 = 0;
          goto LABEL_71;
        }
        if ( !wcscmp_0(v13, L"/wsdl:definitions/wsdl:binding") )
        {
          ATL::CSimpleStringT<unsigned short,0>::Empty(&v50);
          ATL::CSimpleStringT<unsigned short,0>::Empty(&v49);
          v19 = &v52;
          goto LABEL_38;
        }
        if ( !wcscmp_0(v13, L"/wsdl:definitions/wsdl:binding/wsdl:operation") )
        {
          if ( *(_DWORD *)(v50 - 16)
            && *(_DWORD *)(v49 - 16)
            && !wcscmp_0(v52, L"http://schemas.xmlsoap.org/soap/http")
            && (!wcscmp_0(v48, L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue")
             || !wcscmp_0(v48, L"http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue")) )
          {
            v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(&v49);
            v21 = (_QWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                              v73,
                              v50);
            v22 = v21;
            v23 = (int *)(*v20 - 24LL);
            v24 = (int *)(*v21 - 24LL);
            if ( v23 != v24 )
            {
              if ( v24[4] >= 0 && *(_QWORD *)v23 == *(_QWORD *)v24 )
              {
                v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v23);
                ATL::CStringData::Release((ATL::CStringData *)v24);
                *v22 = v25 + 24;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(v21, *v20, *(unsigned int *)(*v20 - 16LL));
              }
            }
          }
          v19 = &v48;
          goto LABEL_38;
        }
        if ( !wcscmp_0(v13, L"/wsdl:definitions/wsdl:service/wsdl:port") )
        {
          if ( *(_DWORD *)(v47 - 16) )
          {
            v26 = v51;
            if ( *(_DWORD *)(v51 - 16) )
            {
              v27 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                      &v47,
                      58,
                      0);
              v28 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                                &v47,
                                &v76,
                                (unsigned int)(v27 + 1));
              v29 = (_QWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                                v72,
                                *v28);
              v30 = v29;
              v31 = (_QWORD *)(v26 - 24);
              v32 = (int *)(*v29 - 24LL);
              if ( (int *)(v26 - 24) != v32 )
              {
                if ( v32[4] >= 0 && *v31 == *(_QWORD *)v32 )
                {
                  v33 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v31);
                  ATL::CStringData::Release((ATL::CStringData *)v32);
                  *v30 = v33 + 24;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(v29, v26, *(unsigned int *)(v26 - 16));
                }
              }
              ATL::CStringData::Release((ATL::CStringData *)(v76 - 24));
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::Empty(&v47);
          v19 = (wchar_t **)&v51;
LABEL_38:
          ATL::CSimpleStringT<unsigned short,0>::Empty(v19);
        }
LABEL_71:
        WsTrustBaseParser<WsTrustMexParser<3>,3>::UpdateCurrentPath(ppvObject, &String1, 0);
        goto LABEL_13;
    }
  }
  if ( v17 == 1 )
  {
    StartPosition = (_QWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetStartPosition(v72);
    v56 = StartPosition;
    if ( StartPosition )
    {
      v36 = v75;
      do
      {
        v77 = 0;
        LODWORD(v76) = 0;
        v55 = 0;
        Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
                 (unsigned int)v73,
                 *StartPosition,
                 (unsigned int)&v77,
                 (unsigned int)&v76,
                 (__int64)&v55);
        if ( Node )
        {
          v77 = 0;
          LODWORD(v76) = 0;
          v55 = 0;
          v38 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
                  (unsigned int)v57,
                  *(_QWORD *)(Node + 8),
                  (unsigned int)&v77,
                  (unsigned int)&v76,
                  (__int64)&v55);
          if ( v38 )
          {
            v39 = *(_DWORD *)(v38 + 8);
            if ( v39 )
            {
              v40 = *(_DWORD *)(v38 + 12);
              if ( v40 )
              {
                v41 = WsTrustUrl::WsTrustUrl((__int64)&v71, (__int64)(StartPosition + 1), v39, v40);
                ATL::CAtlList<WsTrustUrl,ATL::CElementTraits<WsTrustUrl>>::AddHead(v36, v41);
                ATL::CStringData::Release((ATL::CStringData *)(v71 - 24));
              }
            }
          }
        }
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
          v72,
          &v56);
        StartPosition = v56;
      }
      while ( v56 );
    }
    AttrValue = 0;
  }
LABEL_83:
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(v72);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(v73);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::RemoveAll(v57);
  ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v47 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v48 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v49 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v53 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
  ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>(&v54);
  ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>((__int64 *)&ppvObject);
  return (unsigned int)AttrValue;
}

```

## disassembly

```asm
0x180068aa0  mov     [rsp-8+arg_8], rdx
0x180068aa5  push    rbp
0x180068aa6  push    rbx
0x180068aa7  push    rsi
0x180068aa8  push    rdi
0x180068aa9  push    r12
0x180068aab  push    r13
0x180068aad  push    r14
0x180068aaf  push    r15
0x180068ab1  lea     rbp, [rsp-148h]
0x180068ab9  sub     rsp, 248h
0x180068ac0  mov     r12, rdx
0x180068ac3  mov     rbx, rcx
0x180068ac6  xor     edi, edi
0x180068ac8  mov     [rsp+280h+ppvObject], rdi
0x180068acd  mov     [rbp+180h+var_1E8], rdi
0x180068ad1  mov     [rbp+180h+arg_10], rdi
0x180068ad8  mov     [rbp+180h+arg_0], edi
0x180068ade  lea     rcx, [rsp+280h+String1]; void *
0x180068ae3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068ae8  nop
0x180068ae9  lea     rcx, [rbp+180h+var_1F0]; void *
0x180068aed  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068af2  nop
0x180068af3  lea     rcx, [rsp+280h+var_208]; void *
0x180068af8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068afd  nop
0x180068afe  lea     rcx, [rsp+280h+var_210]; void *
0x180068b03  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068b08  nop
0x180068b09  lea     rcx, [rbp+180h+var_1F8]; void *
0x180068b0d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068b12  nop
0x180068b13  lea     rcx, [rsp+280h+var_218]; void *
0x180068b18  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068b1d  nop
0x180068b1e  lea     rcx, [rsp+280h+var_220]; void *
0x180068b23  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068b28  nop
0x180068b29  lea     rcx, [rbp+180h+var_200]; void *
0x180068b2d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068b32  nop
0x180068b33  mov     [rbp+180h+var_1D0], rdi
0x180068b37  mov     [rbp+180h+var_1C8], rdi
0x180068b3b  mov     [rbp+180h+var_1C0], 11h
0x180068b42  mov     eax, 0FFFFFFFFh
0x180068b47  mov     [rbp+180h+var_1B0], rax
0x180068b4b  mov     [rbp+180h+var_1A8], rdi
0x180068b4f  mov     [rbp+180h+var_1A0], edi
0x180068b52  mov     [rbp+180h+var_19C], 0Ah
0x180068b59  mov     [rbp+180h+var_198], rdi
0x180068b5d  mov     [rbp+180h+var_190], rdi
0x180068b61  movss   xmm5, cs:__real@3f400000
0x180068b69  mov     [rbp+180h+var_1BC], 3F400000h
0x180068b70  movss   xmm3, cs:__real@3e800000
0x180068b78  mov     [rbp+180h+var_1B8], 3E800000h
0x180068b7f  movss   xmm4, cs:__real@40100000
0x180068b87  mov     [rbp+180h+var_1B4], 40100000h
0x180068b8e  lea     rcx, [rbp+180h+var_1D0]
0x180068b92  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoPtr@VCJsonValue@@@2@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAutoPtr<CJsonValue>,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CAutoPtrElementTraits<CJsonValue>>::UpdateRehashThresholds(void)
0x180068b97  nop
0x180068b98  movss   dword ptr [rsp+280h+var_260], xmm4
0x180068b9e  movaps  xmm2, xmm5
0x180068ba1  lea     rcx, [rbp+180h+var_90]
0x180068ba8  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>(uint,float,float,float,uint)
0x180068bad  nop
0x180068bae  movss   dword ptr [rsp+280h+var_260], xmm4
0x180068bb4  movaps  xmm2, xmm5
0x180068bb7  lea     rcx, [rbp+180h+var_E0]
0x180068bbe  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>>>(uint,float,float,float,uint)
0x180068bc3  nop
0x180068bc4  lea     rax, aWsdlDefinition_10; "/wsdl:definitions/wsp:Policy"
0x180068bcb  mov     [rbp+180h+var_180], rax
0x180068bcf  lea     rax, aWsuId; "wsu:Id"
0x180068bd6  mov     [rbp+180h+var_178], rax
0x180068bda  lea     rax, [rbp+180h+var_1F0]
0x180068bde  mov     [rbp+180h+var_170], rax
0x180068be2  lea     rax, aWsdlDefinition_12; "/wsdl:definitions/wsdl:binding"
0x180068be9  mov     [rbp+180h+var_168], rax
0x180068bed  lea     rax, aName_1; "name"
0x180068bf4  mov     [rbp+180h+var_160], rax
0x180068bf8  lea     rax, [rsp+280h+var_208]
0x180068bfd  mov     [rbp+180h+var_158], rax
0x180068c01  lea     rax, aWsdlDefinition_9; "/wsdl:definitions/wsdl:binding/wsp:Poli"...
0x180068c08  mov     [rbp+180h+var_150], rax
0x180068c0c  lea     rax, aUri; "URI"
0x180068c13  mov     [rbp+180h+var_148], rax
0x180068c17  lea     rax, [rsp+280h+var_210]
0x180068c1c  mov     [rbp+180h+var_140], rax
0x180068c20  lea     rax, aWsdlDefinition_8; "/wsdl:definitions/wsdl:binding/soap12:b"...
0x180068c27  mov     [rbp+180h+var_138], rax
0x180068c2b  lea     rax, aTransport; "transport"
0x180068c32  mov     [rbp+180h+var_130], rax
0x180068c36  lea     rax, [rbp+180h+var_1F8]
0x180068c3a  mov     [rbp+180h+var_128], rax
0x180068c3e  lea     rax, aWsdlDefinition_11; "/wsdl:definitions/wsdl:binding/wsdl:ope"...
0x180068c45  mov     [rbp+180h+var_120], rax
0x180068c49  lea     rax, aSoapaction_0; "soapAction"
0x180068c50  mov     [rbp+180h+var_118], rax
0x180068c54  lea     rax, [rsp+280h+var_218]
0x180068c59  mov     [rbp+180h+var_110], rax
0x180068c5d  lea     rax, aWsdlDefinition_1; "/wsdl:definitions/wsdl:service/wsdl:por"...
0x180068c64  mov     [rbp+180h+var_108], rax
0x180068c68  lea     rax, aBinding; "binding"
0x180068c6f  mov     [rbp+180h+var_100], rax
0x180068c76  lea     rax, [rsp+280h+var_220]
0x180068c7b  mov     [rbp+180h+var_F8], rax
0x180068c82  mov     rax, [rbx]
0x180068c85  cmp     [rax-10h], edi
0x180068c88  jnz     short loc_180068CE1
0x180068c8a  mov     edi, 80070057h
0x180068c8f  lea     rax, base
0x180068c96  mov     [rsp+280h+var_240], rax
0x180068c9b  lea     rax, aHresult; "HRESULT"
0x180068ca2  mov     [rsp+280h+var_248], rax
0x180068ca7  mov     [rsp+280h+var_250], 49h ; 'I'
0x180068caf  mov     esi, 2
0x180068cb4  lea     rax, aOnecoreuapDsEx_64+25h; "wstrustmexparser.inl"
0x180068cbb  mov     [rsp+280h+var_258], rax
0x180068cc0  mov     dword ptr [rsp+280h+var_260], edi
0x180068cc4  mov     r9d, esi
0x180068cc7  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180068cce  xor     edx, edx
0x180068cd0  mov     ecx, esi
0x180068cd2  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180068cd7  mov     rbx, [rsp+280h+String1]
0x180068cdc  jmp     loc_180069348
0x180068ce1  mov     rcx, r12
0x180068ce4  call    ?RemoveAll@?$CAtlList@UWsTrustUrl@@V?$CElementTraits@UWsTrustUrl@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<WsTrustUrl,ATL::CElementTraits<WsTrustUrl>>::RemoveAll(void)
0x180068ce9  lea     rdx, [rbp+180h+arg_10]
0x180068cf0  mov     rcx, rbx
0x180068cf3  call    ?FromString@SequentialStream@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAUISequentialStream@@H@Z; SequentialStream::FromString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ISequentialStream * *,int)
0x180068cf8  mov     edi, eax
0x180068cfa  test    eax, eax
0x180068cfc  jns     short loc_180068D20
0x180068cfe  lea     rax, base
0x180068d05  mov     [rsp+280h+var_240], rax
0x180068d0a  lea     rax, aHresult; "HRESULT"
0x180068d11  mov     [rsp+280h+var_248], rax
0x180068d16  mov     [rsp+280h+var_250], 4Fh ; 'O'
0x180068d1e  jmp     short loc_180068CAF
0x180068d20  mov     rdx, [rbp+180h+arg_10]
0x180068d27  lea     rcx, [rbp+180h+var_1E8]
0x180068d2b  call    ?Attach@?$CComPtrBase@UISequentialStream@@@ATL@@QEAAXPEAUISequentialStream@@@Z; ATL::CComPtrBase<ISequentialStream>::Attach(ISequentialStream *)
0x180068d30  xor     r8d, r8d; pMalloc
0x180068d33  lea     rdx, [rsp+280h+ppvObject]; ppvObject
0x180068d38  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180068d3f  call    cs:__imp_CreateXmlReader
0x180068d45  mov     edi, eax
0x180068d47  test    eax, eax
0x180068d49  jns     short loc_180068D70
0x180068d4b  lea     rax, base
0x180068d52  mov     [rsp+280h+var_240], rax
0x180068d57  lea     rax, aHresult; "HRESULT"
0x180068d5e  mov     [rsp+280h+var_248], rax
0x180068d63  mov     [rsp+280h+var_250], 53h ; 'S'
0x180068d6b  jmp     loc_180068CAF
0x180068d70  mov     rcx, [rsp+280h+ppvObject]
0x180068d75  mov     rax, [rcx]
0x180068d78  mov     rdx, [rbp+180h+var_1E8]
0x180068d7c  mov     rax, [rax+18h]
0x180068d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d85  mov     edi, eax
0x180068d87  test    eax, eax
0x180068d89  jns     short loc_180068DB0
0x180068d8b  lea     rax, base
0x180068d92  mov     [rsp+280h+var_240], rax
0x180068d97  lea     rax, aHresult; "HRESULT"
0x180068d9e  mov     [rsp+280h+var_248], rax
0x180068da3  mov     [rsp+280h+var_250], 54h ; 'T'
0x180068dab  jmp     loc_180068CAF
0x180068db0  mov     rcx, [rsp+280h+ppvObject]
0x180068db5  mov     rax, [rcx]
0x180068db8  xor     r8d, r8d
0x180068dbb  lea     edx, [r8+4]
0x180068dbf  mov     rax, [rax+28h]
0x180068dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068dc8  mov     edi, eax
0x180068dca  mov     esi, 2
0x180068dcf  test    eax, eax
0x180068dd1  jns     short loc_180068DF8
0x180068dd3  lea     rax, base
0x180068dda  mov     [rsp+280h+var_240], rax
0x180068ddf  lea     rax, aHresult; "HRESULT"
0x180068de6  mov     [rsp+280h+var_248], rax
0x180068deb  mov     [rsp+280h+var_250], 56h ; 'V'
0x180068df3  jmp     loc_180068CB4
0x180068df8  xor     r15d, r15d
0x180068dfb  xor     r13b, r13b
0x180068dfe  xor     r14d, r14d
0x180068e01  mov     rbx, [rsp+280h+String1]
0x180068e06  mov     rcx, [rsp+280h+ppvObject]
0x180068e0b  mov     rax, [rcx]
0x180068e0e  lea     rdx, [rbp+180h+arg_0]
0x180068e15  mov     rax, [rax+30h]
0x180068e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e1e  mov     edi, eax
0x180068e20  test    eax, eax
0x180068e22  jnz     loc_180069248
0x180068e28  mov     ecx, [rbp+180h+arg_0]
0x180068e2e  sub     ecx, 1
0x180068e31  jz      loc_180069102
0x180068e37  sub     ecx, esi
0x180068e39  jz      loc_18006908B
0x180068e3f  cmp     ecx, 0Ch
0x180068e42  jnz     short loc_180068E06
0x180068e44  lea     rdx, aWsdlDefinition_10; "/wsdl:definitions/wsp:Policy"
0x180068e4b  mov     rcx, rbx; String1
0x180068e4e  call    wcscmp_0
0x180068e53  test    eax, eax
0x180068e55  jnz     short loc_180068E91
0x180068e57  mov     rdx, [rbp+180h+var_1F0]
0x180068e5b  cmp     [rdx-10h], eax
0x180068e5e  jz      short loc_180068E7A
0x180068e60  test    r13b, r13b
0x180068e63  jz      short loc_180068E7A
0x180068e65  test    r14d, r14d
0x180068e68  jz      short loc_180068E7A
0x180068e6a  lea     rcx, [rbp+180h+var_1D0]
0x180068e6e  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UWsTrustPolicyId@?1??Parse@?$WsTrustMexParser@$02@@SAJAEBV12@AEAV?$CAtlList@UWsTrustUrl@@V?$CElementTraits@UWsTrustUrl@@@ATL@@@2@@Z@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UWsTrustPolicyId@?1??Parse@?$WsTrustMexParser@$02@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@UWsTrustUrl@@V?$CElementTraits@UWsTrustUrl@@@ATL@@@5@@Z@@2@@ATL@@QEAAAEAUWsTrustPolicyId@?1??Parse@?$WsTrustMexParser@$02@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@AEAV?$CAtlList@UWsTrustUrl@@V?$CElementTraits@UWsTrustUrl@@@ATL@@@1@@Z@PEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,`WsTrustMexParser<3>::Parse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<WsTrustUrl,ATL::CElementTraits<WsTrustUrl>> &)'::`2'::WsTrustPolicyId,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<`WsTrustMexParser<3>::Parse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<WsTrustUrl,ATL::CElementTraits<WsTrustUrl>> &)'::`2'::WsTrustPolicyId>>::operator[](ushort const *)
0x180068e73  mov     [rax], r14d
0x180068e76  mov     [rax+4], r15d
0x180068e7a  lea     rcx, [rbp+180h+var_1F0]
0x180068e7e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180068e83  xor     r14d, r14d
0x180068e86  xor     r13b, r13b
0x180068e89  xor     r15d, r15d
0x180068e8c  jmp     loc_18006920C
0x180068e91  lea     rdx, aWsdlDefinition_12; "/wsdl:definitions/wsdl:binding"
0x180068e98  mov     rcx, rbx; String1
0x180068e9b  call    wcscmp_0
0x180068ea0  test    eax, eax
0x180068ea2  jnz     short loc_180068EC1
0x180068ea4  lea     rcx, [rsp+280h+var_208]
0x180068ea9  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180068eae  lea     rcx, [rsp+280h+var_210]
0x180068eb3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180068eb8  lea     rcx, [rbp+180h+var_1F8]
0x180068ebc  jmp     loc_180068FA8
0x180068ec1  lea     rdx, aWsdlDefinition_2; "/wsdl:definitions/wsdl:binding/wsdl:ope"...
0x180068ec8  mov     rcx, rbx; String1
0x180068ecb  call    wcscmp_0
0x180068ed0  test    eax, eax
0x180068ed2  jnz     loc_180068FB2
0x180068ed8  mov     rax, [rsp+280h+var_208]
0x180068edd  cmp     dword ptr [rax-10h], 0
0x180068ee1  jz      loc_180068FA3
0x180068ee7  mov     rax, [rsp+280h+var_210]
0x180068eec  cmp     dword ptr [rax-10h], 0
0x180068ef0  jz      loc_180068FA3
0x180068ef6  lea     rdx, aHttpSchemasXml_3; "http://schemas.xmlsoap.org/soap/http"
0x180068efd  mov     rcx, [rbp+180h+var_1F8]; String1
0x180068f01  call    wcscmp_0
0x180068f06  test    eax, eax
0x180068f08  jnz     loc_180068FA3
0x180068f0e  lea     rdx, aHttpDocsOasisO_0; "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x180068f15  mov     rcx, [rsp+280h+var_218]; String1
0x180068f1a  call    wcscmp_0
0x180068f1f  test    eax, eax
0x180068f21  jz      short loc_180068F38
0x180068f23  lea     rdx, aHttpSchemasXml_5; "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x180068f2a  mov     rcx, [rsp+280h+var_218]; String1
0x180068f2f  call    wcscmp_0
0x180068f34  test    eax, eax
0x180068f36  jnz     short loc_180068FA3
0x180068f38  lea     rcx, [rsp+280h+var_210]
0x180068f3d  call    ?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@G@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort)
0x180068f42  mov     rbx, rax
0x180068f45  mov     rdx, [rsp+280h+var_208]
0x180068f4a  lea     rcx, [rbp+180h+var_90]
0x180068f51  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@PEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](ushort const *)
0x180068f56  mov     r12, rax
0x180068f59  mov     r9, [rbx]
0x180068f5c  lea     rcx, [r9-18h]
0x180068f60  mov     rdi, [rax]
0x180068f63  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180068f67  cmp     rcx, rdi
0x180068f6a  jz      short loc_180068FA3
0x180068f6c  cmp     dword ptr [rdi+10h], 0
0x180068f70  jl      short loc_180068F94
0x180068f72  mov     rdx, [rdi]
0x180068f75  cmp     [rcx], rdx
0x180068f78  jnz     short loc_180068F94
0x180068f7a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180068f7f  mov     rbx, rax
0x180068f82  mov     rcx, rdi; this
0x180068f85  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180068f8a  lea     rax, [rbx+18h]
0x180068f8e  mov     [r12], rax
0x180068f92  jmp     short loc_180068FA3
0x180068f94  mov     r8d, [r9-10h]
0x180068f98  mov     rdx, r9
0x180068f9b  mov     rcx, r12
0x180068f9e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180068fa3  lea     rcx, [rsp+280h+var_218]
0x180068fa8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180068fad  jmp     loc_18006920C
0x180068fb2  lea     rdx, aWsdlDefinition_1; "/wsdl:definitions/wsdl:service/wsdl:por"...
0x180068fb9  mov     rcx, rbx; String1
0x180068fbc  call    wcscmp_0
  ... truncated ...
```
