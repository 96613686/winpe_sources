# _lambda_5f78d3a87c0e72b8ee7fd5fad8cbb888_::operator()

- ea: `0x18006e554`
- end: `0x18006f579`
- name: `_lambda_5f78d3a87c0e72b8ee7fd5fad8cbb888_::operator()`
- size: `4133`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006c4fc`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180010a94`
- `0x180011550`
- `0x180011810`
- `0x180011c04`
- `0x180012260`
- `0x180013950`
- `0x180021950`
- `0x180022510`
- `0x180028420`
- `0x180028d18`
- `0x180029dd0`
- `0x18002c9d8`
- `0x18002e9d0`
- `0x180034cf8`
- `0x180046d90`
- `0x180048394`
- `0x180059df4`
- `0x18006c8d0`
- `0x18006caa4`
- `0x18006e554`
- `0x180071fcc`
- `0x1800726a0`
- `0x1800818c8`
- `0x180085048`
- `0x180088580`
- `0x180088740`
- `0x1800890bc`
- `0x1800a962c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f43b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f43b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ed0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ed0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f3f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006eb48`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006eb48`

## string_xrefs

- `0x18006e5ba`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006e654`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006e732`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006e869`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006ea99`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006ed8c`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006efe9`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f1fd`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f373`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f45d`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f4d6`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall lambda_5f78d3a87c0e72b8ee7fd5fad8cbb888_::operator()(__int64 a1)
{
  char IsEnabled; // al
  const WCHAR *v3; // r9
  void *v4; // rcx
  int v5; // r15d
  int v6; // eax
  signed int ContainerMetadata; // ebx
  int v8; // eax
  int LocalContainer; // eax
  int v10; // eax
  struct NgcKspServer::TransportManager *v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  struct NgcKspServer::TransportManager *v15; // rax
  _QWORD *v16; // rax
  char *v17; // rdx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  int v21; // ebx
  int v22; // r13d
  __int64 v23; // rax
  struct NgcKspServer::TransportManager *v24; // rax
  _QWORD *v25; // rax
  struct NgcKspServer::TransportManager *v26; // rax
  _QWORD *v27; // rax
  _DWORD *v28; // r14
  _DWORD *v29; // rsi
  unsigned int v30; // eax
  struct NgcKspServer::TransportManager *v31; // rax
  _QWORD *v32; // rax
  struct NgcKspServer::TransportManager *v33; // rax
  _QWORD *v34; // rax
  BOOL v35; // ebx
  __int64 v36; // r8
  struct NgcKspServer::TransportManager *v37; // rax
  NgcLocalTransport::LocalTransport **v38; // rax
  HLOCAL v39; // rcx
  struct NgcKspServer::TransportManager *v40; // rax
  _QWORD *v41; // rax
  unsigned __int64 v42; // r9
  __int64 v43; // rdx
  struct NgcKspServer::TransportManager *v44; // rax
  _QWORD *v45; // rax
  unsigned __int8 *v46; // rdx
  int v47; // eax
  int v48; // eax
  struct NgcKspServer::TransportManager *v49; // rax
  _QWORD *v50; // rax
  __int64 v51; // rdx
  struct NgcKspServer::TransportManager *v52; // rax
  _QWORD *v53; // rax
  unsigned __int8 *v54; // rdx
  struct NgcKspServer::TransportManager *v55; // rax
  _QWORD *v56; // rax
  struct NgcKspServer::TransportManager *v57; // rax
  _QWORD *v58; // rax
  struct NgcKspServer::TransportManager *v59; // rax
  NgcLocalTransport::LocalTransport **v60; // rax
  struct NgcKspServer::TransportManager *v61; // rax
  NgcLocalTransport::LocalTransport **v62; // rax
  HLOCAL v63; // rcx
  struct NgcKspServer::TransportManager *v64; // rax
  NgcLocalTransport::LocalTransport **v65; // rax
  void *v66; // rdx
  int updated; // eax
  HLOCAL v68; // rcx
  char *v69; // rdx
  unsigned int v71; // [rsp+20h] [rbp-100h]
  int v72; // [rsp+40h] [rbp-E0h]
  HLOCAL hMem; // [rsp+A0h] [rbp-80h] BYREF
  struct _GUID *v74; // [rsp+A8h] [rbp-78h] BYREF
  __int64 v75; // [rsp+B0h] [rbp-70h] BYREF
  struct _NGC_RPC_GESTURE_INFO *v76; // [rsp+B8h] [rbp-68h]
  __int128 v77; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-50h]
  void **v79; // [rsp+D8h] [rbp-48h] BYREF
  std::_Ref_count_base *v80; // [rsp+E0h] [rbp-40h]
  _BYTE v81[8]; // [rsp+E8h] [rbp-38h] BYREF
  std::_Ref_count_base *v82; // [rsp+F0h] [rbp-30h]
  unsigned __int64 v83; // [rsp+F8h] [rbp-28h] BYREF
  unsigned __int64 v84; // [rsp+100h] [rbp-20h] BYREF
  __int64 v85[2]; // [rsp+108h] [rbp-18h] BYREF
  __int64 v86; // [rsp+118h] [rbp-8h]
  __int64 v87[2]; // [rsp+120h] [rbp+0h] BYREF
  __int64 v88; // [rsp+130h] [rbp+10h]
  unsigned __int64 *v89; // [rsp+138h] [rbp+18h] BYREF
  __int64 v90; // [rsp+140h] [rbp+20h]
  unsigned __int64 *v91; // [rsp+148h] [rbp+28h]
  int v92; // [rsp+150h] [rbp+30h]
  __int128 v93; // [rsp+154h] [rbp+34h]
  int v94; // [rsp+164h] [rbp+44h]
  __int64 v95; // [rsp+168h] [rbp+48h]
  int v96; // [rsp+170h] [rbp+50h]
  HLOCAL *p_hMem; // [rsp+178h] [rbp+58h] BYREF
  PSID Sid; // [rsp+180h] [rbp+60h] BYREF
  char v99; // [rsp+188h] [rbp+68h]
  _BYTE v100[8]; // [rsp+190h] [rbp+70h] BYREF
  std::_Ref_count_base *v101; // [rsp+198h] [rbp+78h]
  _BYTE v102[4]; // [rsp+1A8h] [rbp+88h] BYREF
  int v103; // [rsp+1ACh] [rbp+8Ch]
  __int64 v104; // [rsp+1B0h] [rbp+90h]
  char v105; // [rsp+1B8h] [rbp+98h]
  int v106; // [rsp+1BCh] [rbp+9Ch]
  int v107; // [rsp+1C0h] [rbp+A0h]
  __int128 v108; // [rsp+1C4h] [rbp+A4h]
  int v109; // [rsp+1D4h] [rbp+B4h]
  __int64 v110; // [rsp+1D8h] [rbp+B8h]
  int v111; // [rsp+1E0h] [rbp+C0h]
  __int64 v112[10]; // [rsp+1F0h] [rbp+D0h] BYREF
  int v113; // [rsp+244h] [rbp+124h]
  int v114; // [rsp+248h] [rbp+128h]
  int v115[36]; // [rsp+250h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1C8h]
  int v117; // [rsp+2F8h] [rbp+1D8h] BYREF
  unsigned int v118; // [rsp+300h] [rbp+1E0h]
  int v119; // [rsp+308h] [rbp+1E8h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v3 = **(const WCHAR ***)(a1 + 8);
  v4 = **(void ***)a1;
  v5 = 0;
  if ( IsEnabled )
  {
    v6 = I_CheckNgcApiAccessRight(v4, 0, 0, v3, 0);
    ContainerMetadata = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E0,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)v6,
        v71);
      return (unsigned int)ContainerMetadata;
    }
  }
  else
  {
    v8 = I_CheckNgcApiAccessRight(v4, 0, 0, v3, 0);
    ContainerMetadata = v8;
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v117 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)word_1800FF202,
          0,
          0,
          (__int64)&v117);
      }
      return (unsigned int)ContainerMetadata;
    }
  }
  v74 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    NgcKspServer::TransportManager::Instance();
    LocalContainer = NgcKspServer::TransportManager::FindLocalContainer(**(_QWORD **)(a1 + 8), &v74);
    ContainerMetadata = LocalContainer;
    if ( LocalContainer < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F7,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)LocalContainer,
        v71);
      goto LABEL_177;
    }
  }
  else
  {
    NgcKspServer::TransportManager::Instance();
    v10 = NgcKspServer::TransportManager::FindLocalContainer(**(_QWORD **)(a1 + 8), &v74);
    ContainerMetadata = v10;
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v117 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)word_1800FF1D2,
          0,
          0,
          (__int64)&v117);
      }
      goto LABEL_177;
    }
  }
  v77 = 0;
  v78 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    v11 = NgcKspServer::TransportManager::Instance();
    v12 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v11, &v79);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v12, v74, 2, &v77);
    if ( v80 )
      std::_Ref_count_base::_Decref(v80);
    if ( ContainerMetadata < 0 )
    {
      v13 = 2062;
LABEL_18:
      v14 = (unsigned int)ContainerMetadata;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)v14,
        v71);
LABEL_176:
      std::vector<unsigned char>::_Tidy(&v77);
      goto LABEL_177;
    }
  }
  else
  {
    v15 = NgcKspServer::TransportManager::Instance();
    v16 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v15, &v79);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v16, v74, 2, &v77);
    if ( v80 )
      std::_Ref_count_base::_Decref(v80);
    if ( ContainerMetadata < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_176;
      v17 = (char *)word_1800FF19A;
      goto LABEL_25;
    }
  }
  LOBYTE(v89) = 0;
  HIDWORD(v89) = 1;
  v90 = 1;
  LOBYTE(v91) = 0;
  HIDWORD(v91) = 8;
  v92 = 127;
  v93 = 0;
  v94 = 2;
  v95 = 1;
  v96 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    v18 = NgcPolicy::NgcPolicy::Initialize(&v89, &v77);
    ContainerMetadata = v18;
    if ( v18 < 0 )
    {
      v14 = (unsigned int)v18;
      v13 = 2083;
      goto LABEL_19;
    }
  }
  else
  {
    v19 = NgcPolicy::NgcPolicy::Initialize(&v89, &v77);
    ContainerMetadata = v19;
    if ( v19 < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_176;
      v117 = v19;
      v17 = byte_1800FF169;
      goto LABEL_26;
    }
  }
  if ( !HIDWORD(v89) )
  {
    ContainerMetadata = -2146893783;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v20 = 2103;
LABEL_36:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)ContainerMetadata,
        v71);
      goto LABEL_176;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_176;
    v117 = -2146893783;
    v17 = byte_1800FF13D;
    goto LABEL_26;
  }
  LOBYTE(v117) = 0;
  LOBYTE(v118) = 0;
  v119 = 0;
  v21 = *(_DWORD *)v74[2].Data4;
  v22 = v21
      & ((((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl)
         ^ 1) << 6)
       - 75);
  if ( (v22 & 1) != 0 )
  {
    v23 = *((_QWORD *)&v77 + 1);
    if ( (_QWORD)v77 != *((_QWORD *)&v77 + 1) )
      v23 = v77;
    *((_QWORD *)&v77 + 1) = v23;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v24 = NgcKspServer::TransportManager::Instance();
      v25 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v24, &v79);
      ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v25, v74, 3, &v77);
      if ( v80 )
        std::_Ref_count_base::_Decref(v80);
      if ( ContainerMetadata < 0 )
      {
        v13 = 2138;
        goto LABEL_18;
      }
      goto LABEL_52;
    }
    v26 = NgcKspServer::TransportManager::Instance();
    v27 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v26, &v79);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v27, v74, 3, &v77);
    if ( v80 )
      std::_Ref_count_base::_Decref(v80);
    if ( ContainerMetadata >= 0 )
    {
LABEL_52:
      v28 = (_DWORD *)*((_QWORD *)&v77 + 1);
      v29 = (_DWORD *)v77;
      if ( *((_QWORD *)&v77 + 1) - (_QWORD)v77 != 4 )
      {
        ContainerMetadata = -2146893792;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v20 = 2162;
          goto LABEL_36;
        }
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_176;
        v117 = -2146893792;
        v17 = (char *)&dword_1800FF0BC;
LABEL_26:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)v17,
          0,
          0,
          (__int64)&v117);
        goto LABEL_176;
      }
      v30 = *(_DWORD *)v77;
      v119 = HIWORD(*(_DWORD *)v77);
      LOBYTE(v117) = v30 & 1;
      v30 >>= 1;
      LOBYTE(v30) = v30 & 1;
      v118 = v30;
      goto LABEL_59;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_176;
    v17 = byte_1800FF0F5;
LABEL_25:
    v117 = ContainerMetadata;
    goto LABEL_26;
  }
  v28 = (_DWORD *)*((_QWORD *)&v77 + 1);
  v29 = (_DWORD *)v77;
LABEL_59:
  NgcKspServer::CredUIStringsContext::CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v112, 0, 0);
  while ( 1 )
  {
    if ( v29 != v28 )
      v28 = v29;
    *((_QWORD *)&v77 + 1) = v28;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v31 = NgcKspServer::TransportManager::Instance();
      v32 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v31, &v79);
      ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v32, v74, 8, &v77);
      if ( v80 )
        std::_Ref_count_base::_Decref(v80);
      if ( ContainerMetadata < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x892,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)(unsigned int)ContainerMetadata,
          v71);
        goto LABEL_175;
      }
    }
    else
    {
      v33 = NgcKspServer::TransportManager::Instance();
      v34 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v33, v100);
      ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v34, v74, 8, &v77);
      if ( v101 )
        std::_Ref_count_base::_Decref(v101);
      if ( ContainerMetadata < 0 )
      {
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_175;
        v117 = ContainerMetadata;
        v69 = byte_1800FF07B;
        goto LABEL_174;
      }
    }
    v28 = (_DWORD *)*((_QWORD *)&v77 + 1);
    v29 = (_DWORD *)v77;
    if ( *((_QWORD *)&v77 + 1) - (_QWORD)v77 != 20 )
    {
      ContainerMetadata = -2146893792;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x8AA,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)0x80090020LL,
          v71);
        goto LABEL_175;
      }
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_175;
      v117 = -2146893792;
      v69 = byte_1800FF049;
LABEL_174:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)v69,
        0,
        0,
        (__int64)&v117);
      goto LABEL_175;
    }
    if ( *(_DWORD *)v77 || !*(_DWORD *)(v77 + 12) )
    {
      v5 = -2146893775;
      v113 = -2146893775;
    }
    hMem = 0;
    p_hMem = &hMem;
    Sid = 0;
    v99 = 1;
    v35 = ConvertStringSidToSidW(**(LPCWSTR **)(a1 + 8), &Sid);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
    if ( !v35 )
    {
      ContainerMetadata = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x8C7,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)(unsigned int)ContainerMetadata,
          v71);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v117 = ContainerMetadata;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&word_1800FF016,
          0,
          0,
          (__int64)&v117);
      }
      if ( ContainerMetadata > 0 )
        ContainerMetadata = (unsigned __int16)ContainerMetadata | 0x80070000;
      goto LABEL_161;
    }
    v75 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
    v76 = 0;
    *(_OWORD *)v87 = 0;
    v88 = 0;
    *(_OWORD *)v85 = 0;
    v86 = 0;
    v36 = (__int64)(v29 + 2);
    if ( !*v29 )
      v36 = 0;
    ContainerMetadata = NgcKspServer::PromptForGesture(
                          **(_QWORD **)a1,
                          **(_QWORD **)(a1 + 16),
                          v5,
                          v22,
                          0,
                          v117,
                          v119,
                          v118,
                          v72,
                          hMem,
                          0,
                          0,
                          (__int64)v87,
                          (__int64)v85,
                          0,
                          v36,
                          **(_QWORD **)(a1 + 24),
                          (__int64)v112,
                          (__int64)&v75);
    if ( ContainerMetadata < 0 )
    {
      std::vector<unsigned char>::_Tidy(v85);
      std::vector<unsigned char>::_Tidy(v87);
      v75 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v75);
LABEL_161:
      v68 = hMem;
      hMem = 0;
      goto LABEL_158;
    }
    v84 = 0;
    v83 = 0;
    v89 = &v84;
    v90 = (__int64)&v74;
    v91 = &v83;
    LOWORD(v92) = 256;
    v37 = NgcKspServer::TransportManager::Instance();
    v38 = (NgcLocalTransport::LocalTransport **)NgcKspServer::TransportManager::LocalTransport(v37, v81);
    v5 = NgcLocalTransport::LocalTransport::AuthenticateGesture(*v38, v74, v76, &v84, &v83);
    if ( v82 )
      std::_Ref_count_base::_Decref(v82);
    if ( v5 >= 0 )
      goto LABEL_144;
    if ( ((v5 + 2146893775) & 0xFFFFFFFD) != 0 )
      break;
    v113 = v5;
    v114 = *(_DWORD *)v76;
    wil::details::ScopeExitFnGuard__lambda_a5b86125696fcb6abfc57332ce38a4f2___::operator()(&v89);
    std::vector<unsigned char>::_Tidy(v85);
    std::vector<unsigned char>::_Tidy(v87);
    v75 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v75);
    v39 = hMem;
    hMem = 0;
    if ( v39 )
      LocalFree(v39);
  }
  if ( v5 == -2146893769 )
  {
    if ( v29 != v28 )
      v28 = v29;
    *((_QWORD *)&v77 + 1) = v28;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v40 = NgcKspServer::TransportManager::Instance();
      v41 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v40, v81);
      ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v41, v74, 2, &v77);
      if ( v82 )
        std::_Ref_count_base::_Decref(v82);
      if ( ContainerMetadata < 0 )
      {
        v42 = (unsigned int)ContainerMetadata;
        v43 = 2339;
        goto LABEL_92;
      }
LABEL_100:
      v102[0] = 0;
      v103 = 1;
      v104 = 1;
      v105 = 0;
      v106 = 8;
      v107 = 127;
      v108 = 0;
      v109 = 2;
      v110 = 1;
      v111 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v47 = NgcPolicy::NgcPolicy::Initialize(v102, &v77);
        ContainerMetadata = v47;
        if ( v47 < 0 )
        {
          v42 = (unsigned int)v47;
          v43 = 2360;
LABEL_92:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v43,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
            (const char *)v42,
            v71);
          goto LABEL_157;
        }
LABEL_106:
        NgcKspServer::CredUIStringsContext::CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v115, 0, 1);
        v79 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
        v80 = 0;
        ContainerMetadata = NgcKspServer::PromptForNewPin(
                              **(_QWORD **)a1,
                              **(_QWORD **)(a1 + 16),
                              0,
                              (unsigned int)v102,
                              (__int64)v115,
                              (__int64)&v79);
        if ( ContainerMetadata < 0 )
        {
LABEL_107:
          v79 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v79);
          NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v115);
          goto LABEL_157;
        }
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
          &p_hMem,
          *((_QWORD *)v76 + 1),
          *((_QWORD *)v76 + 1) + *((unsigned int *)v76 + 4));
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
          v100,
          *((_QWORD *)v80 + 1),
          *((_QWORD *)v80 + 1) + *((unsigned int *)v80 + 4));
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v49 = NgcKspServer::TransportManager::Instance();
          v50 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v49, v81);
          ContainerMetadata = NgcLocalTransport::LocalTransport::ChangePin(*v50, v74, &p_hMem, v100);
          if ( v82 )
            std::_Ref_count_base::_Decref(v82);
          if ( ContainerMetadata < 0 )
          {
            v51 = 2403;
            goto LABEL_113;
          }
LABEL_121:
          v55 = NgcKspServer::TransportManager::Instance();
          v56 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v55, v81);
          NgcLocalTransport::LocalTransport::Deauthenticate(*v56, v74, 0, v84);
          if ( v82 )
            std::_Ref_count_base::_Decref(v82);
          if ( v83 )
          {
            v57 = NgcKspServer::TransportManager::Instance();
            v58 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v57, v81);
            NgcLocalTransport::LocalTransport::Deauthenticate(*v58, v74, 0, v83);
            if ( v82 )
              std::_Ref_count_base::_Decref(v82);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
          {
            v59 = NgcKspServer::TransportManager::Instance();
            v60 = (NgcLocalTransport::LocalTransport **)NgcKspServer::TransportManager::LocalTransport(v59, v81);
            ContainerMetadata = NgcLocalTransport::LocalTransport::AuthenticateGesture(*v60, v74, v80, &v84, &v83);
            if ( v82 )
              std::_Ref_count_base::_Decref(v82);
            if ( ContainerMetadata < 0 )
            {
              v51 = 2442;
LABEL_113:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v51,
                (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
                (const char *)(unsigned int)ContainerMetadata,
                v71);
              goto LABEL_114;
            }
LABEL_136:
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v100);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&p_hMem);
            v79 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
            Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v79);
            NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v115);
LABEL_144:
            v64 = NgcKspServer::TransportManager::Instance();
            v65 = (NgcLocalTransport::LocalTransport **)NgcKspServer::TransportManager::LocalTransport(v64, v81);
            ContainerMetadata = NgcLocalTransport::LocalTransport::AddBioProtector(*v65, v74, v84, v83);
            if ( v82 )
              std::_Ref_count_base::_Decref(v82);
            if ( (int)(ContainerMetadata + 0x80000000) >= 0 && ContainerMetadata != -2147024713 )
              goto LABEL_181;
            v83 = 0;
            updated = NgcUtils::ClearBioProtectorUpdateNeeded(*(PSID *)&v74[1].Data1, v66);
            if ( updated < 0 && (unsigned int)dword_180122070 > 3 )
            {
              v117 = updated;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (__int64)&dword_180122070,
                (unsigned __int8 *)byte_1800FEEEF,
                0,
                0,
                (__int64)&v117);
            }
            if ( ContainerMetadata < 0 && ContainerMetadata != -2147024713 )
            {
LABEL_181:
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
              {
                wil::details::in1diag3::Log_Hr(
                  retaddr,
                  (void *)0x9C5,
                  (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
                  (const char *)(unsigned int)ContainerMetadata,
                  v71);
              }
              else if ( (unsigned int)dword_180122070 > 2 )
              {
                v117 = ContainerMetadata;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (__int64)&dword_180122070,
                  (unsigned __int8 *)word_1800FEEC2,
                  0,
                  0,
                  (__int64)&v117);
              }
            }
            goto LABEL_157;
          }
          v61 = NgcKspServer::TransportManager::Instance();
          v62 = (NgcLocalTransport::LocalTransport **)NgcKspServer::TransportManager::LocalTransport(v61, v81);
          ContainerMetadata = NgcLocalTransport::LocalTransport::AuthenticateGesture(*v62, v74, v80, &v84, &v83);
          if ( v82 )
            std::_Ref_count_base::_Decref(v82);
          if ( ContainerMetadata >= 0 )
            goto LABEL_136;
          if ( (unsigned int)dword_180122070 <= 2 )
            goto LABEL_114;
          v54 = (unsigned __int8 *)byte_1800FEF5B;
        }
        else
        {
          v52 = NgcKspServer::TransportManager::Instance();
          v53 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v52, v81);
          ContainerMetadata = NgcLocalTransport::LocalTransport::ChangePin(*v53, v74, &p_hMem, v100);
          if ( v82 )
            std::_Ref_count_base::_Decref(v82);
          if ( ContainerMetadata >= 0 )
            goto LABEL_121;
          if ( (unsigned int)dword_180122070 <= 2 )
          {
LABEL_114:
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v100);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&p_hMem);
            goto LABEL_107;
          }
          v54 = (unsigned __int8 *)&dword_1800FEF8C;
        }
        v117 = ContainerMetadata;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          v54,
          0,
          0,
          (__int64)&v117);
        goto LABEL_114;
      }
      v48 = NgcPolicy::NgcPolicy::Initialize(v102, &v77);
      ContainerMetadata = v48;
      if ( v48 >= 0 )
        goto LABEL_106;
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_157;
      v117 = v48;
      v46 = (unsigned __int8 *)byte_1800FEFB3;
LABEL_99:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        v46,
        0,
        0,
        (__int64)&v117);
      goto LABEL_157;
    }
    v44 = NgcKspServer::TransportManager::Instance();
    v45 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v44, v81);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v45, v74, 2, &v77);
    if ( v82 )
      std::_Ref_count_base::_Decref(v82);
    if ( ContainerMetadata >= 0 )
      goto LABEL_100;
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v117 = ContainerMetadata;
      v46 = (unsigned __int8 *)&dword_1800FEFE4;
      goto LABEL_99;
    }
LABEL_157:
    wil::details::ScopeExitFnGuard__lambda_a5b86125696fcb6abfc57332ce38a4f2___::operator()(&v89);
    std::vector<unsigned char>::_Tidy(v85);
    std::vector<unsigned char>::_Tidy(v87);
    v75 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v75);
    v68 = hMem;
    hMem = 0;
LABEL_158:
    if ( v68 )
      LocalFree(v68);
LABEL_175:
    NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v112);
    goto LABEL_176;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x9A1,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
      (const char *)(unsigned int)v5,
      v71);
  }
  else if ( (unsigned int)dword_180122070 > 2 )
  {
    v117 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)word_1800FEF2A,
      0,
      0,
      (__int64)&v117);
  }
  wil::details::ScopeExitFnGuard__lambda_a5b86125696fcb6abfc57332ce38a4f2___::operator()(&v89);
  std::vector<unsigned char>::_Tidy(v85);
  std::vector<unsigned char>::_Tidy(v87);
  v75 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v75);
  v63 = hMem;
  hMem = 0;
  if ( v63 )
    LocalFree(v63);
  NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v112);
  std::vector<unsigned char>::_Tidy(&v77);
  ContainerMetadata = v5;
LABEL_177:
  std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(&v74);
  return (unsigned int)ContainerMetadata;
}

```

## disassembly

```asm
0x18006e554  mov     [rsp-8+arg_0], rbx
0x18006e559  push    rbp
0x18006e55a  push    rsi
0x18006e55b  push    rdi
0x18006e55c  push    r12
0x18006e55e  push    r13
0x18006e560  push    r14
0x18006e562  push    r15
0x18006e564  lea     rbp, [rsp-190h]
0x18006e56c  sub     rsp, 2B0h
0x18006e573  mov     r12, rcx
0x18006e576  lea     rsi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006e57d  mov     rcx, rsi
0x18006e580  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e585  mov     rdx, [r12+8]
0x18006e58a  mov     r9, [rdx]
0x18006e58d  mov     rdx, [r12]
0x18006e591  mov     rcx, [rdx]
0x18006e594  xor     r15d, r15d
0x18006e597  mov     dword ptr [rsp+2E0h+var_2C0], r15d; int
0x18006e59c  xor     r8d, r8d
0x18006e59f  xor     edx, edx
0x18006e5a1  test    al, al
0x18006e5a3  jz      short loc_18006E5D0
0x18006e5a5  call    I_CheckNgcApiAccessRight
0x18006e5aa  mov     ebx, eax
0x18006e5ac  test    eax, eax
0x18006e5ae  jns     short loc_18006E61E
0x18006e5b0  mov     rcx, [rbp+1C8h]; this
0x18006e5b7  mov     r9d, eax; char *
0x18006e5ba  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006e5c1  mov     edx, 7E0h; void *
0x18006e5c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e5cb  jmp     loc_18006F55C
0x18006e5d0  call    I_CheckNgcApiAccessRight
0x18006e5d5  mov     ebx, eax
0x18006e5d7  test    eax, eax
0x18006e5d9  jns     short loc_18006E61E
0x18006e5db  mov     ecx, cs:dword_180122070
0x18006e5e1  mov     edi, 2
0x18006e5e6  cmp     ecx, edi
0x18006e5e8  jbe     loc_18006F55C
0x18006e5ee  mov     [rbp+1C0h+arg_8], eax
0x18006e5f4  lea     rax, [rbp+1C0h+arg_8]
0x18006e5fb  mov     [rsp+2E0h+var_2C0], rax
0x18006e600  xor     r9d, r9d
0x18006e603  xor     r8d, r8d
0x18006e606  lea     rdx, word_1800FF202
0x18006e60d  lea     rcx, dword_180122070
0x18006e614  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006e619  jmp     loc_18006F55C
0x18006e61e  mov     [rbp+1C0h+var_238], r15
0x18006e622  mov     rcx, rsi
0x18006e625  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e62a  test    al, al
0x18006e62c  jz      short loc_18006E66A
0x18006e62e  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006e633  mov     rcx, [r12+8]
0x18006e638  lea     rdx, [rbp+1C0h+var_238]
0x18006e63c  mov     rcx, [rcx]
0x18006e63f  call    ?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z; NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo> *)
0x18006e644  mov     ebx, eax
0x18006e646  test    eax, eax
0x18006e648  jns     short loc_18006E6C9
0x18006e64a  mov     rcx, [rbp+1C8h]; this
0x18006e651  mov     r9d, eax; char *
0x18006e654  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006e65b  mov     edx, 7F7h; void *
0x18006e660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e665  jmp     loc_18006F553
0x18006e66a  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006e66f  mov     rcx, [r12+8]
0x18006e674  lea     rdx, [rbp+1C0h+var_238]
0x18006e678  mov     rcx, [rcx]
0x18006e67b  call    ?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z; NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo> *)
0x18006e680  mov     ebx, eax
0x18006e682  test    eax, eax
0x18006e684  jns     short loc_18006E6C9
0x18006e686  mov     ecx, cs:dword_180122070
0x18006e68c  mov     edi, 2
0x18006e691  cmp     ecx, edi
0x18006e693  jbe     loc_18006F553
0x18006e699  mov     [rbp+1C0h+arg_8], eax
0x18006e69f  lea     rax, [rbp+1C0h+arg_8]
0x18006e6a6  mov     [rsp+2E0h+var_2C0], rax
0x18006e6ab  xor     r9d, r9d
0x18006e6ae  xor     r8d, r8d
0x18006e6b1  lea     rdx, word_1800FF1D2
0x18006e6b8  lea     rcx, dword_180122070
0x18006e6bf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006e6c4  jmp     loc_18006F553
0x18006e6c9  xorps   xmm0, xmm0
0x18006e6cc  movdqu  [rbp+1C0h+var_220], xmm0
0x18006e6d1  mov     [rbp+1C0h+var_210], r15
0x18006e6d5  mov     rcx, rsi
0x18006e6d8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e6dd  test    al, al
0x18006e6df  jz      short loc_18006E743
0x18006e6e1  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006e6e6  lea     rdx, [rbp+1C0h+var_208]
0x18006e6ea  mov     rcx, rax
0x18006e6ed  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006e6f2  nop
0x18006e6f3  lea     r9, [rbp+1C0h+var_220]
0x18006e6f7  mov     edi, 2
0x18006e6fc  mov     r8d, edi
0x18006e6ff  mov     rdx, [rbp+1C0h+var_238]
0x18006e703  mov     rcx, [rax]
0x18006e706  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006e70b  mov     ebx, eax
0x18006e70d  mov     rcx, [rbp+1C0h+var_200]; this
0x18006e711  test    rcx, rcx
0x18006e714  jz      short loc_18006E71B
0x18006e716  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006e71b  test    ebx, ebx
0x18006e71d  jns     loc_18006E7BF
0x18006e723  mov     edx, 80Eh; void *
0x18006e728  mov     r9d, ebx; char *
0x18006e72b  mov     rcx, [rbp+1C8h]; this
0x18006e732  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006e739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e73e  jmp     loc_18006F549
0x18006e743  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006e748  lea     rdx, [rbp+1C0h+var_208]
0x18006e74c  mov     rcx, rax
0x18006e74f  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006e754  nop
0x18006e755  lea     r9, [rbp+1C0h+var_220]
0x18006e759  mov     edi, 2
0x18006e75e  mov     r8d, edi
0x18006e761  mov     rdx, [rbp+1C0h+var_238]
0x18006e765  mov     rcx, [rax]
0x18006e768  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006e76d  mov     ebx, eax
0x18006e76f  mov     rcx, [rbp+1C0h+var_200]; this
0x18006e773  test    rcx, rcx
0x18006e776  jz      short loc_18006E77D
0x18006e778  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006e77d  test    ebx, ebx
0x18006e77f  jns     short loc_18006E7BF
0x18006e781  mov     ecx, cs:dword_180122070
0x18006e787  cmp     ecx, edi
0x18006e789  jbe     loc_18006F549
0x18006e78f  lea     rdx, word_1800FF19A
0x18006e796  mov     [rbp+1C0h+arg_8], ebx
0x18006e79c  lea     rax, [rbp+1C0h+arg_8]
0x18006e7a3  xor     r9d, r9d
0x18006e7a6  mov     [rsp+2E0h+var_2C0], rax
0x18006e7ab  xor     r8d, r8d
0x18006e7ae  lea     rcx, dword_180122070
0x18006e7b5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006e7ba  jmp     loc_18006F549
0x18006e7bf  mov     byte ptr [rbp+1C0h+var_1A8], r15b
0x18006e7c3  mov     r14d, 1
0x18006e7c9  mov     dword ptr [rbp+1C0h+var_1A8+4], r14d
0x18006e7cd  mov     [rbp+1C0h+var_1A0], r14
0x18006e7d1  mov     byte ptr [rbp+1C0h+var_198], r15b
0x18006e7d5  mov     dword ptr [rbp+1C0h+var_198+4], 8
0x18006e7dc  mov     [rbp+1C0h+var_190], 7Fh
0x18006e7e3  xorps   xmm0, xmm0
0x18006e7e6  movdqu  [rbp+1C0h+var_18C], xmm0
0x18006e7eb  mov     [rbp+1C0h+var_17C], edi
0x18006e7ee  mov     [rbp+1C0h+var_178], r14
0x18006e7f2  mov     [rbp+1C0h+var_170], r15d
0x18006e7f6  mov     rcx, rsi
0x18006e7f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e7fe  lea     rdx, [rbp+1C0h+var_220]
0x18006e802  lea     rcx, [rbp+1C0h+var_1A8]
0x18006e806  test    al, al
0x18006e808  jz      short loc_18006E822
0x18006e80a  call    ?Initialize@NgcPolicy@1@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcPolicy::NgcPolicy::Initialize(std::vector<uchar> const &)
0x18006e80f  mov     ebx, eax
0x18006e811  test    eax, eax
0x18006e813  jns     short loc_18006E84D
0x18006e815  mov     r9d, eax
0x18006e818  mov     edx, 823h
0x18006e81d  jmp     loc_18006E72B
0x18006e822  call    ?Initialize@NgcPolicy@1@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcPolicy::NgcPolicy::Initialize(std::vector<uchar> const &)
0x18006e827  mov     ebx, eax
0x18006e829  test    eax, eax
0x18006e82b  jns     short loc_18006E84D
0x18006e82d  mov     ecx, cs:dword_180122070
0x18006e833  cmp     ecx, edi
0x18006e835  jbe     loc_18006F549
0x18006e83b  mov     [rbp+1C0h+arg_8], eax
0x18006e841  lea     rdx, byte_1800FF169
0x18006e848  jmp     loc_18006E79C
0x18006e84d  cmp     dword ptr [rbp+1C0h+var_1A8+4], r15d
0x18006e851  jnz     short loc_18006E8A8
0x18006e853  mov     rcx, rsi
0x18006e856  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e85b  mov     ebx, 80090029h
0x18006e860  test    al, al
0x18006e862  jz      short loc_18006E884
0x18006e864  mov     edx, 837h; void *
0x18006e869  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006e870  mov     r9d, ebx; char *
0x18006e873  mov     rcx, [rbp+1C8h]; this
0x18006e87a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18006e87f  jmp     loc_18006F549
0x18006e884  mov     eax, cs:dword_180122070
0x18006e88a  cmp     eax, edi
0x18006e88c  jbe     loc_18006F549
0x18006e892  mov     [rbp+1C0h+arg_8], 80090029h
0x18006e89c  lea     rdx, byte_1800FF13D
0x18006e8a3  jmp     loc_18006E79C
0x18006e8a8  mov     byte ptr [rbp+1C0h+arg_8], r15b
0x18006e8af  mov     byte ptr [rbp+1C0h+arg_10], r15b
0x18006e8b6  mov     [rbp+1C0h+arg_18], r15d
0x18006e8bd  mov     rax, [rbp+1C0h+var_238]
0x18006e8c1  mov     ebx, [rax+28h]
0x18006e8c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18006e8cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18006e8d0  movzx   r13d, al
0x18006e8d4  xor     r13d, r14d
0x18006e8d7  shl     r13d, 6
0x18006e8db  sub     r13d, 4Bh ; 'K'
0x18006e8df  and     r13d, ebx
0x18006e8e2  mov     ebx, 3
0x18006e8e7  test    r14b, r13b
0x18006e8ea  jz      loc_18006EA1E
0x18006e8f0  mov     rax, qword ptr [rbp+1C0h+var_220+8]
0x18006e8f4  cmp     qword ptr [rbp+1C0h+var_220], rax
0x18006e8f8  cmovnz  rax, qword ptr [rbp+1C0h+var_220]
0x18006e8fd  mov     qword ptr [rbp+1C0h+var_220+8], rax
0x18006e901  mov     rcx, rsi
0x18006e904  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e909  test    al, al
0x18006e90b  jz      short loc_18006E950
0x18006e90d  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006e912  lea     rdx, [rbp+1C0h+var_208]
0x18006e916  mov     rcx, rax
0x18006e919  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006e91e  nop
0x18006e91f  lea     r9, [rbp+1C0h+var_220]
0x18006e923  mov     r8d, ebx
0x18006e926  mov     rdx, [rbp+1C0h+var_238]
0x18006e92a  mov     rcx, [rax]
0x18006e92d  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006e932  mov     ebx, eax
0x18006e934  mov     rcx, [rbp+1C0h+var_200]; this
0x18006e938  test    rcx, rcx
0x18006e93b  jz      short loc_18006E942
0x18006e93d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006e942  test    ebx, ebx
0x18006e944  jns     short loc_18006E9A3
0x18006e946  mov     edx, 85Ah
0x18006e94b  jmp     loc_18006E728
0x18006e950  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006e955  lea     rdx, [rbp+1C0h+var_208]
0x18006e959  mov     rcx, rax
0x18006e95c  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006e961  nop
0x18006e962  lea     r9, [rbp+1C0h+var_220]
0x18006e966  mov     r8d, ebx
0x18006e969  mov     rdx, [rbp+1C0h+var_238]
0x18006e96d  mov     rcx, [rax]
0x18006e970  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006e975  mov     ebx, eax
0x18006e977  mov     rcx, [rbp+1C0h+var_200]; this
0x18006e97b  test    rcx, rcx
0x18006e97e  jz      short loc_18006E985
0x18006e980  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006e985  test    ebx, ebx
0x18006e987  jns     short loc_18006E9A3
0x18006e989  mov     ecx, cs:dword_180122070
0x18006e98f  cmp     ecx, edi
0x18006e991  jbe     loc_18006F549
0x18006e997  lea     rdx, byte_1800FF0F5
0x18006e99e  jmp     loc_18006E796
0x18006e9a3  mov     r14, qword ptr [rbp+1C0h+var_220+8]
0x18006e9a7  mov     rax, r14
0x18006e9aa  mov     rsi, qword ptr [rbp+1C0h+var_220]
0x18006e9ae  sub     rax, rsi
0x18006e9b1  cmp     rax, 4
0x18006e9b5  jz      short loc_18006E9FA
0x18006e9b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006e9be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006e9c3  mov     ebx, 80090020h
0x18006e9c8  test    al, al
0x18006e9ca  jz      short loc_18006E9D6
0x18006e9cc  mov     edx, 872h
0x18006e9d1  jmp     loc_18006E869
0x18006e9d6  mov     eax, cs:dword_180122070
0x18006e9dc  cmp     eax, edi
0x18006e9de  jbe     loc_18006F549
0x18006e9e4  mov     [rbp+1C0h+arg_8], 80090020h
0x18006e9ee  lea     rdx, dword_1800FF0BC
0x18006e9f5  jmp     loc_18006E79C
0x18006e9fa  mov     eax, [rsi]
0x18006e9fc  mov     ecx, eax
0x18006e9fe  shr     ecx, 10h
0x18006ea01  mov     [rbp+1C0h+arg_18], ecx
0x18006ea07  mov     cl, al
0x18006ea09  and     cl, 1
0x18006ea0c  mov     byte ptr [rbp+1C0h+arg_8], cl
0x18006ea12  shr     eax, 1
0x18006ea14  and     al, 1
0x18006ea16  mov     [rbp+1C0h+arg_10], eax
0x18006ea1c  jmp     short loc_18006EA26
  ... truncated ...
```
