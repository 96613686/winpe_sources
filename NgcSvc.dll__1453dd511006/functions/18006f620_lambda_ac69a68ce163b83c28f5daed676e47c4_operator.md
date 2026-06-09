# _lambda_ac69a68ce163b83c28f5daed676e47c4_::operator()

- ea: `0x18006f620`
- end: `0x18006ffb3`
- name: `_lambda_ac69a68ce163b83c28f5daed676e47c4_::operator()`
- size: `2451`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006c520`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180011810`
- `0x180011c04`
- `0x180012260`
- `0x180013950`
- `0x180021950`
- `0x180028420`
- `0x180028d18`
- `0x180029dd0`
- `0x18002c9d8`
- `0x180034cf8`
- `0x180046d90`
- `0x180048394`
- `0x18006c8d0`
- `0x18006caa4`
- `0x18006f620`
- `0x180081f9c`
- `0x180085048`
- `0x180088740`
- `0x1800a962c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fafa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fb81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fc69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ff0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ff83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fb81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fc69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ff0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ff83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006fae1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006fae1`

## string_xrefs

- `0x18006f688`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f719`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f7af`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006f850`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006fa66`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006fb1c`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006fc36`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006fe09`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006fea0`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall lambda_ac69a68ce163b83c28f5daed676e47c4_::operator()(void ***a1)
{
  char IsEnabled; // al
  const WCHAR *v3; // r9
  void *v4; // rcx
  unsigned int v5; // r13d
  int v6; // eax
  DWORD LastError; // ebx
  int v9; // eax
  int LocalContainer; // eax
  int v11; // eax
  unsigned __int8 *v12; // rdx
  __int64 v13; // rbx
  struct NgcKspServer::TransportManager *v14; // rax
  _QWORD *v15; // rax
  int ContainerMetadata; // edi
  __int64 v17; // rdx
  struct NgcKspServer::TransportManager *v18; // rax
  _QWORD *v19; // rax
  __int16 *v20; // rdx
  __int64 v21; // rax
  struct NgcKspServer::TransportManager *v22; // rax
  _QWORD *v23; // rax
  struct NgcKspServer::TransportManager *v24; // rax
  _QWORD *v25; // rax
  unsigned int *v26; // r15
  unsigned int *v27; // r14
  BOOL v28; // edi
  HLOCAL v29; // rcx
  unsigned int v30; // ecx
  unsigned int v31; // eax
  struct NgcKspServer::TransportManager *v32; // rax
  _QWORD *v33; // rax
  HLOCAL v34; // rcx
  struct NgcKspServer::TransportManager *v35; // rax
  _QWORD *v36; // rax
  int v37; // edi
  struct NgcKspServer::TransportManager *v38; // rax
  _QWORD *v39; // rax
  HLOCAL v40; // rcx
  HLOCAL v41; // rcx
  bool v42; // zf
  unsigned int v43; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[8]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v49; // [rsp+90h] [rbp-70h]
  unsigned int v50; // [rsp+98h] [rbp-68h]
  PSID Sid[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  __int128 v53; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-38h]
  _BYTE v55[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v56; // [rsp+D4h] [rbp-2Ch]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  char v58; // [rsp+E0h] [rbp-20h]
  int v59; // [rsp+E4h] [rbp-1Ch]
  int v60; // [rsp+E8h] [rbp-18h]
  __int128 v61; // [rsp+ECh] [rbp-14h]
  int v62; // [rsp+FCh] [rbp-4h]
  __int64 v63; // [rsp+100h] [rbp+0h]
  int v64; // [rsp+108h] [rbp+8h]
  _BYTE v65[8]; // [rsp+110h] [rbp+10h] BYREF
  std::_Ref_count_base *v66; // [rsp+118h] [rbp+18h]
  _BYTE v67[8]; // [rsp+120h] [rbp+20h] BYREF
  std::_Ref_count_base *v68; // [rsp+128h] [rbp+28h]
  _BYTE v69[84]; // [rsp+130h] [rbp+30h] BYREF
  int v70; // [rsp+184h] [rbp+84h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]
  int v72; // [rsp+1D8h] [rbp+D8h] BYREF
  int v73; // [rsp+1E0h] [rbp+E0h]
  unsigned int v74; // [rsp+1E8h] [rbp+E8h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v3 = (const WCHAR *)*a1[1];
  v4 = **a1;
  v5 = 0;
  if ( IsEnabled )
  {
    v6 = I_CheckNgcApiAccessRight(v4, (__int64)L"userSigninSupport", 1, v3, 0);
    LastError = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F1,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)v6,
        v43);
      return LastError;
    }
  }
  else
  {
    v9 = I_CheckNgcApiAccessRight(v4, (__int64)L"userSigninSupport", 1, v3, 0);
    LastError = v9;
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v72 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)word_1800FF8B2,
          0,
          0,
          (__int64)&v72);
      }
      return LastError;
    }
  }
  v47 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    NgcKspServer::TransportManager::Instance();
    LocalContainer = NgcKspServer::TransportManager::FindLocalContainer(*a1[1], &v47);
    LastError = LocalContainer;
    if ( LocalContainer < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x408,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)LocalContainer,
        v43);
LABEL_107:
      std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(&v47);
      return LastError;
    }
  }
  else
  {
    NgcKspServer::TransportManager::Instance();
    v11 = NgcKspServer::TransportManager::FindLocalContainer(*a1[1], &v47);
    LastError = v11;
    if ( v11 < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_107;
      v72 = v11;
      v12 = (unsigned __int8 *)&byte_1800FF87F;
LABEL_14:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        v12,
        0,
        0,
        (__int64)&v72);
      goto LABEL_107;
    }
  }
  v13 = v47;
  if ( (*(_BYTE *)(v47 + 40) & 1) == 0 )
  {
    LastError = -2147467263;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x41E,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)0x80004001LL,
        v43);
      goto LABEL_107;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_107;
    v72 = -2147467263;
    v12 = (unsigned __int8 *)word_1800FF84A;
    goto LABEL_14;
  }
  v45 = 0;
  v46 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    v14 = NgcKspServer::TransportManager::Instance();
    v15 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v14, v48);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v15, v13, 2, &v45);
    if ( v49 )
      std::_Ref_count_base::_Decref(v49);
    if ( ContainerMetadata < 0 )
    {
      v17 = 1074;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)ContainerMetadata,
        v43);
LABEL_26:
      std::vector<unsigned char>::_Tidy(&v45);
      LastError = ContainerMetadata;
      goto LABEL_107;
    }
  }
  else
  {
    v18 = NgcKspServer::TransportManager::Instance();
    v19 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v18, v48);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v19, v13, 2, &v45);
    if ( v49 )
      std::_Ref_count_base::_Decref(v49);
    if ( ContainerMetadata < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_26;
      v20 = &word_1800FF816;
LABEL_32:
      v72 = ContainerMetadata;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)v20,
        0,
        0,
        (__int64)&v72);
      goto LABEL_26;
    }
  }
  v55[0] = 0;
  v56 = 1;
  v57 = 1;
  v58 = 0;
  v59 = 8;
  v60 = 127;
  v61 = 0;
  v62 = 2;
  v63 = 1;
  v64 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    ContainerMetadata = NgcPolicy::NgcPolicy::Initialize(v55, &v45);
    if ( ContainerMetadata < 0 )
    {
      v17 = 1095;
      goto LABEL_25;
    }
  }
  else
  {
    ContainerMetadata = NgcPolicy::NgcPolicy::Initialize(v55, &v45);
    if ( ContainerMetadata < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_26;
      v20 = &word_1800FF7E6;
      goto LABEL_32;
    }
  }
  v21 = *((_QWORD *)&v45 + 1);
  if ( (_QWORD)v45 != *((_QWORD *)&v45 + 1) )
    v21 = v45;
  *((_QWORD *)&v45 + 1) = v21;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    v22 = NgcKspServer::TransportManager::Instance();
    v23 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v22, v48);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v23, v13, 3, &v45);
    if ( v49 )
      std::_Ref_count_base::_Decref(v49);
    if ( ContainerMetadata < 0 )
    {
      v17 = 1116;
      goto LABEL_25;
    }
    goto LABEL_51;
  }
  v24 = NgcKspServer::TransportManager::Instance();
  v25 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v24, v48);
  ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v25, v13, 3, &v45);
  if ( v49 )
    std::_Ref_count_base::_Decref(v49);
  if ( ContainerMetadata < 0 )
  {
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_26;
    v20 = word_1800FF7A2;
    goto LABEL_32;
  }
LABEL_51:
  v26 = (unsigned int *)*((_QWORD *)&v45 + 1);
  v27 = (unsigned int *)v45;
  if ( *((_QWORD *)&v45 + 1) - (_QWORD)v45 != 4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x474,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)0x80090020LL,
        v43);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v72 = -2146893792;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1800FF769,
        0,
        0,
        (__int64)&v72);
    }
LABEL_106:
    std::vector<unsigned char>::_Tidy(&v45);
    LastError = -2146893792;
    goto LABEL_107;
  }
  hMem = 0;
  Sid[0] = &hMem;
  Sid[1] = 0;
  LOBYTE(v52) = 1;
  v28 = ConvertStringSidToSidW((LPCWSTR)*a1[1], &Sid[1]);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)Sid);
  if ( !v28 )
  {
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x488,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)LastError,
        v43);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v72 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&word_1800FF736,
        0,
        0,
        (__int64)&v72);
    }
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v29 = hMem;
    hMem = 0;
    if ( v29 )
      LocalFree(v29);
    std::vector<unsigned char>::_Tidy(&v45);
    goto LABEL_107;
  }
  v30 = *v27;
  LOBYTE(v73) = *v27 & 1;
  v31 = v30 >> 1;
  LOBYTE(v31) = (v30 & 2) != 0;
  v74 = v31;
  v50 = HIWORD(v30);
  NgcKspServer::CredUIStringsContext::CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v69, 0, 1);
  LOBYTE(v72) = 0;
  while ( 1 )
  {
    if ( v27 != v26 )
      v26 = v27;
    *((_QWORD *)&v45 + 1) = v26;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      break;
    v32 = NgcKspServer::TransportManager::Instance();
    v33 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v32, v48);
    ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v33, v13, 8, &v45);
    if ( v49 )
      std::_Ref_count_base::_Decref(v49);
    if ( ContainerMetadata < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A7,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)ContainerMetadata,
        v43);
      goto LABEL_74;
    }
LABEL_79:
    v26 = (unsigned int *)*((_QWORD *)&v45 + 1);
    v27 = (unsigned int *)v45;
    if ( *((_QWORD *)&v45 + 1) - (_QWORD)v45 != 20 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x4BF,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)0x80090020LL,
          v43);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v72 = -2146893792;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1800FF6C7,
          0,
          0,
          (__int64)&v72);
      }
      NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v69);
      v40 = hMem;
      hMem = 0;
      if ( v40 )
        LocalFree(v40);
      goto LABEL_106;
    }
    if ( *(_DWORD *)v45 || !*(_DWORD *)(v45 + 12) )
    {
      v5 = -2146893775;
      v70 = -2146893775;
    }
    *(_OWORD *)Sid = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    LOBYTE(v43) = v73;
    ContainerMetadata = NgcKspServer::PromptForPinChange(**a1, *a1[2], v5, v55);
    if ( ContainerMetadata < 0 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v53);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(Sid);
LABEL_74:
      NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v69);
      v34 = hMem;
      hMem = 0;
      if ( v34 )
        LocalFree(v34);
      goto LABEL_26;
    }
    v38 = NgcKspServer::TransportManager::Instance();
    v39 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v38, v67);
    v37 = NgcLocalTransport::LocalTransport::ChangePin(*v39, v13, Sid, &v53);
    if ( v68 )
      std::_Ref_count_base::_Decref(v68);
    if ( v37 >= 0 )
    {
      LOBYTE(v72) = 1;
    }
    else
    {
      if ( v37 != -2146893773 && v37 != -2146893775 && v37 != -2147024279 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x4FA,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
            (const char *)(unsigned int)v37,
            v43);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          v72 = v37;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&unk_1800FF698,
            0,
            0,
            (__int64)&v72);
        }
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v53);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(Sid);
        goto LABEL_110;
      }
      v5 = v37;
      v70 = v37;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v53);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(Sid);
    if ( (_BYTE)v72 )
      goto LABEL_110;
  }
  v35 = NgcKspServer::TransportManager::Instance();
  v36 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v35, v65);
  v37 = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v36, v13, 8, &v45);
  if ( v66 )
    std::_Ref_count_base::_Decref(v66);
  if ( v37 >= 0 )
    goto LABEL_79;
  if ( (unsigned int)dword_180122070 > 2 )
  {
    v72 = v37;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_1800FF6F9,
      0,
      0,
      (__int64)&v72);
  }
LABEL_110:
  NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v69);
  v41 = hMem;
  v42 = hMem == 0;
  hMem = 0;
  if ( !v42 )
    LocalFree(v41);
  std::vector<unsigned char>::_Tidy(&v45);
  std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(&v47);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x18006f620  push    rbp
0x18006f622  push    rbx
0x18006f623  push    rdi
0x18006f624  push    r12
0x18006f626  push    r13
0x18006f628  push    r14
0x18006f62a  push    r15
0x18006f62c  lea     rbp, [rsp-90h]
0x18006f634  sub     rsp, 190h
0x18006f63b  mov     r12, rcx
0x18006f63e  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006f645  mov     rcx, r14
0x18006f648  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006f64d  mov     rdx, [r12+8]
0x18006f652  mov     r9, [rdx]
0x18006f655  mov     rdx, [r12]
0x18006f659  mov     rcx, [rdx]
0x18006f65c  xor     r13d, r13d
0x18006f65f  mov     [rsp+1C0h+var_1A0], r13d; int
0x18006f664  lea     r8d, [r13+1]
0x18006f668  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x18006f66f  test    al, al
0x18006f671  jz      short loc_18006F6A0
0x18006f673  call    I_CheckNgcApiAccessRight
0x18006f678  mov     ebx, eax
0x18006f67a  test    eax, eax
0x18006f67c  jns     short loc_18006F6E3
0x18006f67e  mov     rcx, [rbp+0C8h]; this
0x18006f685  mov     r9d, eax; char *
0x18006f688  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006f68f  mov     edx, 3F1h; void *
0x18006f694  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f699  mov     eax, ebx
0x18006f69b  jmp     loc_18006FFA0
0x18006f6a0  call    I_CheckNgcApiAccessRight
0x18006f6a5  mov     ebx, eax
0x18006f6a7  test    eax, eax
0x18006f6a9  jns     short loc_18006F6E3
0x18006f6ab  mov     ecx, cs:dword_180122070
0x18006f6b1  cmp     ecx, 2
0x18006f6b4  jbe     short loc_18006F699
0x18006f6b6  mov     [rbp+0C0h+arg_8], eax
0x18006f6bc  lea     rax, [rbp+0C0h+arg_8]
0x18006f6c3  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18006f6c8  xor     r9d, r9d
0x18006f6cb  xor     r8d, r8d
0x18006f6ce  lea     rdx, word_1800FF8B2
0x18006f6d5  lea     rcx, dword_180122070
0x18006f6dc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006f6e1  jmp     short loc_18006F699
0x18006f6e3  mov     [rbp+0C0h+var_140], r13
0x18006f6e7  mov     rcx, r14
0x18006f6ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006f6ef  test    al, al
0x18006f6f1  jz      short loc_18006F72F
0x18006f6f3  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006f6f8  mov     rcx, [r12+8]
0x18006f6fd  lea     rdx, [rbp+0C0h+var_140]
0x18006f701  mov     rcx, [rcx]
0x18006f704  call    ?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z; NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo> *)
0x18006f709  mov     ebx, eax
0x18006f70b  test    eax, eax
0x18006f70d  jns     short loc_18006F78A
0x18006f70f  mov     rcx, [rbp+0C8h]; this
0x18006f716  mov     r9d, eax; char *
0x18006f719  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006f720  mov     edx, 408h; void *
0x18006f725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f72a  jmp     loc_18006FF21
0x18006f72f  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006f734  mov     rcx, [r12+8]
0x18006f739  lea     rdx, [rbp+0C0h+var_140]
0x18006f73d  mov     rcx, [rcx]
0x18006f740  call    ?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z; NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo> *)
0x18006f745  mov     ebx, eax
0x18006f747  test    eax, eax
0x18006f749  jns     short loc_18006F78A
0x18006f74b  mov     ecx, cs:dword_180122070
0x18006f751  cmp     ecx, 2
0x18006f754  jbe     loc_18006FF21
0x18006f75a  mov     [rbp+0C0h+arg_8], eax
0x18006f760  lea     rdx, byte_1800FF87F
0x18006f767  xor     r9d, r9d
0x18006f76a  lea     rax, [rbp+0C0h+arg_8]
0x18006f771  xor     r8d, r8d
0x18006f774  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18006f779  lea     rcx, dword_180122070
0x18006f780  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006f785  jmp     loc_18006FF21
0x18006f78a  mov     rbx, [rbp+0C0h+var_140]
0x18006f78e  test    byte ptr [rbx+28h], 1
0x18006f792  jnz     short loc_18006F7E7
0x18006f794  mov     rcx, r14
0x18006f797  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006f79c  mov     ebx, 80004001h
0x18006f7a1  test    al, al
0x18006f7a3  jz      short loc_18006F7C5
0x18006f7a5  mov     rcx, [rbp+0C8h]; this
0x18006f7ac  mov     r9d, ebx; char *
0x18006f7af  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006f7b6  mov     edx, 41Eh; void *
0x18006f7bb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18006f7c0  jmp     loc_18006FF21
0x18006f7c5  mov     eax, cs:dword_180122070
0x18006f7cb  cmp     eax, 2
0x18006f7ce  jbe     loc_18006FF21
0x18006f7d4  mov     [rbp+0C0h+arg_8], 80004001h
0x18006f7de  lea     rdx, word_1800FF84A
0x18006f7e5  jmp     short loc_18006F767
0x18006f7e7  xorps   xmm0, xmm0
0x18006f7ea  movdqu  [rsp+1C0h+var_158], xmm0
0x18006f7f0  mov     [rsp+1C0h+var_148], r13
0x18006f7f5  mov     rcx, r14
0x18006f7f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006f7fd  test    al, al
0x18006f7ff  jz      short loc_18006F86E
0x18006f801  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006f806  lea     rdx, [rbp+0C0h+var_138]
0x18006f80a  mov     rcx, rax
0x18006f80d  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006f812  nop
0x18006f813  lea     r9, [rsp+1C0h+var_158]
0x18006f818  mov     r8d, 2
0x18006f81e  mov     rdx, rbx
0x18006f821  mov     rcx, [rax]
0x18006f824  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006f829  mov     edi, eax
0x18006f82b  mov     rcx, [rbp+0C0h+var_130]; this
0x18006f82f  test    rcx, rcx
0x18006f832  jz      short loc_18006F839
0x18006f834  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006f839  test    edi, edi
0x18006f83b  jns     loc_18006F8E5
0x18006f841  mov     edx, 432h; void *
0x18006f846  mov     rcx, [rbp+0C8h]; this
0x18006f84d  mov     r9d, edi; char *
0x18006f850  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006f857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f85c  nop
0x18006f85d  lea     rcx, [rsp+1C0h+var_158]
0x18006f862  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18006f867  mov     ebx, edi
0x18006f869  jmp     loc_18006FF21
0x18006f86e  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006f873  lea     rdx, [rbp+0C0h+var_138]
0x18006f877  mov     rcx, rax
0x18006f87a  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006f87f  nop
0x18006f880  lea     r9, [rsp+1C0h+var_158]
0x18006f885  mov     r8d, 2
0x18006f88b  mov     rdx, rbx
0x18006f88e  mov     rcx, [rax]
0x18006f891  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006f896  mov     edi, eax
0x18006f898  mov     rcx, [rbp+0C0h+var_130]; this
0x18006f89c  test    rcx, rcx
0x18006f89f  jz      short loc_18006F8A6
0x18006f8a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006f8a6  test    edi, edi
0x18006f8a8  jns     short loc_18006F8E5
0x18006f8aa  mov     ecx, cs:dword_180122070
0x18006f8b0  cmp     ecx, 2
0x18006f8b3  jbe     short loc_18006F85D
0x18006f8b5  lea     rdx, word_1800FF816
0x18006f8bc  lea     rax, [rbp+0C0h+arg_8]
0x18006f8c3  xor     r9d, r9d
0x18006f8c6  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18006f8cb  xor     r8d, r8d
0x18006f8ce  mov     [rbp+0C0h+arg_8], edi
0x18006f8d4  lea     rcx, dword_180122070
0x18006f8db  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006f8e0  jmp     loc_18006F85D
0x18006f8e5  mov     [rbp+0C0h+var_F0], r13b
0x18006f8e9  mov     [rbp+0C0h+var_EC], 1
0x18006f8f0  mov     [rbp+0C0h+var_E8], 1
0x18006f8f8  mov     [rbp+0C0h+var_E0], r13b
0x18006f8fc  mov     [rbp+0C0h+var_DC], 8
0x18006f903  mov     [rbp+0C0h+var_D8], 7Fh
0x18006f90a  xorps   xmm0, xmm0
0x18006f90d  movdqu  [rbp+0C0h+var_D4], xmm0
0x18006f912  mov     [rbp+0C0h+var_C4], 2
0x18006f919  mov     [rbp+0C0h+var_C0], 1
0x18006f921  mov     [rbp+0C0h+var_B8], r13d
0x18006f925  mov     rcx, r14
0x18006f928  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006f92d  lea     rdx, [rsp+1C0h+var_158]
0x18006f932  lea     rcx, [rbp+0C0h+var_F0]
0x18006f936  test    al, al
0x18006f938  jz      short loc_18006F94F
0x18006f93a  call    ?Initialize@NgcPolicy@1@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcPolicy::NgcPolicy::Initialize(std::vector<uchar> const &)
0x18006f93f  mov     edi, eax
0x18006f941  test    eax, eax
0x18006f943  jns     short loc_18006F975
0x18006f945  mov     edx, 447h
0x18006f94a  jmp     loc_18006F846
0x18006f94f  call    ?Initialize@NgcPolicy@1@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcPolicy::NgcPolicy::Initialize(std::vector<uchar> const &)
0x18006f954  mov     edi, eax
0x18006f956  test    eax, eax
0x18006f958  jns     short loc_18006F975
0x18006f95a  mov     ecx, cs:dword_180122070
0x18006f960  cmp     ecx, 2
0x18006f963  jbe     loc_18006F85D
0x18006f969  lea     rdx, word_1800FF7E6
0x18006f970  jmp     loc_18006F8BC
0x18006f975  mov     rax, qword ptr [rsp+1C0h+var_158+8]
0x18006f97a  cmp     qword ptr [rsp+1C0h+var_158], rax
0x18006f97f  cmovnz  rax, qword ptr [rsp+1C0h+var_158]
0x18006f985  mov     qword ptr [rsp+1C0h+var_158+8], rax
0x18006f98a  mov     rcx, r14
0x18006f98d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006f992  test    al, al
0x18006f994  jz      short loc_18006F9DC
0x18006f996  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006f99b  lea     rdx, [rbp+0C0h+var_138]
0x18006f99f  mov     rcx, rax
0x18006f9a2  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006f9a7  nop
0x18006f9a8  lea     r9, [rsp+1C0h+var_158]
0x18006f9ad  mov     r8d, 3
0x18006f9b3  mov     rdx, rbx
0x18006f9b6  mov     rcx, [rax]
0x18006f9b9  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006f9be  mov     edi, eax
0x18006f9c0  mov     rcx, [rbp+0C0h+var_130]; this
0x18006f9c4  test    rcx, rcx
0x18006f9c7  jz      short loc_18006F9CE
0x18006f9c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006f9ce  test    edi, edi
0x18006f9d0  jns     short loc_18006FA33
0x18006f9d2  mov     edx, 45Ch
0x18006f9d7  jmp     loc_18006F846
0x18006f9dc  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006f9e1  lea     rdx, [rbp+0C0h+var_138]
0x18006f9e5  mov     rcx, rax
0x18006f9e8  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006f9ed  nop
0x18006f9ee  lea     r9, [rsp+1C0h+var_158]
0x18006f9f3  mov     r8d, 3
0x18006f9f9  mov     rdx, rbx
0x18006f9fc  mov     rcx, [rax]
0x18006f9ff  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006fa04  mov     edi, eax
0x18006fa06  mov     rcx, [rbp+0C0h+var_130]; this
0x18006fa0a  test    rcx, rcx
0x18006fa0d  jz      short loc_18006FA14
0x18006fa0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006fa14  test    edi, edi
0x18006fa16  jns     short loc_18006FA33
0x18006fa18  mov     ecx, cs:dword_180122070
0x18006fa1e  cmp     ecx, 2
0x18006fa21  jbe     loc_18006F85D
0x18006fa27  lea     rdx, word_1800FF7A2
0x18006fa2e  jmp     loc_18006F8BC
0x18006fa33  mov     r15, qword ptr [rsp+1C0h+var_158+8]
0x18006fa38  mov     rax, r15
0x18006fa3b  mov     r14, qword ptr [rsp+1C0h+var_158]
0x18006fa40  sub     rax, r14
0x18006fa43  cmp     rax, 4
0x18006fa47  jz      short loc_18006FABF
0x18006fa49  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006fa50  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006fa55  test    al, al
0x18006fa57  jz      short loc_18006FA7C
0x18006fa59  mov     rcx, [rbp+0C8h]; this
0x18006fa60  mov     r9d, 80090020h; char *
0x18006fa66  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006fa6d  mov     edx, 474h; void *
0x18006fa72  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18006fa77  jmp     loc_18006FF12
0x18006fa7c  mov     eax, cs:dword_180122070
0x18006fa82  cmp     eax, 2
0x18006fa85  jbe     loc_18006FF12
0x18006fa8b  mov     [rbp+0C0h+arg_8], 80090020h
0x18006fa95  lea     rax, [rbp+0C0h+arg_8]
0x18006fa9c  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18006faa1  xor     r9d, r9d
0x18006faa4  xor     r8d, r8d
0x18006faa7  lea     rdx, byte_1800FF769
0x18006faae  lea     rcx, dword_180122070
0x18006fab5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006faba  jmp     loc_18006FF12
0x18006fabf  mov     [rsp+1C0h+hMem], r13
0x18006fac4  lea     rax, [rsp+1C0h+hMem]
0x18006fac9  mov     [rbp+0C0h+Sid], rax
0x18006facd  mov     [rbp+0C0h+Sid+8], r13
0x18006fad1  mov     byte ptr [rbp+0C0h+var_110], 1
0x18006fad5  mov     rcx, [r12+8]
0x18006fada  lea     rdx, [rbp+0C0h+Sid+8]; Sid
0x18006fade  mov     rcx, [rcx]; StringSid
0x18006fae1  call    cs:__imp_ConvertStringSidToSidW
0x18006fae7  mov     edi, eax
0x18006fae9  lea     rcx, [rbp+0C0h+Sid]
0x18006faed  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006faf2  test    edi, edi
0x18006faf4  jnz     loc_18006FB97
0x18006fafa  call    cs:__imp_GetLastError
0x18006fb00  mov     ebx, eax
0x18006fb02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006fb09  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006fb0e  test    al, al
  ... truncated ...
```
