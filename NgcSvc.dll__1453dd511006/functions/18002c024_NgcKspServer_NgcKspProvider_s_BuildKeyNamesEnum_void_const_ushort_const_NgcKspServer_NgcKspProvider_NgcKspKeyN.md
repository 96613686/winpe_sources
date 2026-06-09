# NgcKspServer::NgcKspProvider::s_BuildKeyNamesEnum(void * const,ushort const *,NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState * *)

- ea: `0x18002c024`
- end: `0x18002c7f4`
- name: `?s_BuildKeyNamesEnum@NgcKspProvider@NgcKspServer@@CAJQEAXPEBGPEAPEAUNgcKspKeyNameEnumState@12@@Z`
- size: `2000`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, struct NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState **)`
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002bbc0`

## callees

- `0x1800014c4`
- `0x1800049e0`
- `0x180004e90`
- `0x180005e90`
- `0x18000782c`
- `0x18000e570`
- `0x18000e844`
- `0x18000e960`
- `0x18000fbcc`
- `0x180010d60`
- `0x180011810`
- `0x18001219c`
- `0x1800122e0`
- `0x180012310`
- `0x1800128e4`
- `0x1800137c0`
- `0x180016280`
- `0x180021f00`
- `0x180024b50`
- `0x180024e40`
- `0x180026f30`
- `0x1800281e0`
- `0x180028420`
- `0x1800288a0`
- `0x180028d18`
- `0x180029dd0`
- `0x18002c024`
- `0x180031c3c`
- `0x1800320a0`
- `0x180034cf8`
- `0x1800352bc`
- `0x180036c6c`
- `0x180045d60`
- `0x180046d90`
- `0x180048394`
- `0x180048434`
- `0x18005cee0`
- `0x18005d2ec`
- `0x18005dd20`
- `0x18005dd44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c702`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c26d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c26d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c3c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c3c0`

## string_xrefs

- `0x18002c12f`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18002c3fa`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18002c69d`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18002c724`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall NgcKspServer::NgcKspProvider::s_BuildKeyNamesEnum(
        void *const a1,
        unsigned __int16 *a2,
        struct NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState **a3)
{
  __int64 v5; // r15
  int v6; // edi
  GUID *v7; // rsi
  struct NgcKspServer::TransportManager *v8; // rax
  _QWORD *v9; // rax
  unsigned int v10; // edx
  _QWORD *v11; // rax
  const GUID *const *i; // rbx
  struct NgcKspServer::TransportManager *v13; // rax
  _QWORD *v14; // rax
  int v15; // r14d
  struct NgcKspServer::TransportManager *v16; // rax
  _QWORD *v17; // rax
  std::_Ref_count_base *v18; // rcx
  const void *v19; // rdx
  size_t v20; // r8
  const GUID *v21; // rax
  char *v22; // rdx
  char *v23; // rcx
  char *v24; // rax
  __int64 *v25; // rbx
  int v26; // r9d
  unsigned __int64 **v27; // r14
  unsigned __int64 **v28; // r12
  unsigned int v29; // edx
  unsigned __int64 *v30; // r8
  _QWORD *v31; // rcx
  unsigned __int64 *v32; // rax
  wchar_t *v33; // rcx
  _QWORD *v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 **v37; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  signed int LastError; // ebx
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  GUID *v43; // [rsp+40h] [rbp-C0h] BYREF
  const GUID *v44; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v45; // [rsp+50h] [rbp-B0h]
  void *v46[2]; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v48; // [rsp+70h] [rbp-90h]
  __int128 v49; // [rsp+78h] [rbp-88h] BYREF
  char *v50; // [rsp+88h] [rbp-78h]
  __int128 v51; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h]
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  void *v54; // [rsp+B0h] [rbp-50h]
  struct NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState **v55; // [rsp+B8h] [rbp-48h]
  _BYTE v56[16]; // [rsp+C0h] [rbp-40h] BYREF
  char *v57[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v58; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v59; // [rsp+100h] [rbp+0h]
  __int64 v60; // [rsp+108h] [rbp+8h]
  __int128 v61; // [rsp+110h] [rbp+10h] BYREF
  __int64 v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  __int64 v64; // [rsp+130h] [rbp+30h]
  OLECHAR sz[56]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v55 = a3;
  v54 = a1;
  LODWORD(v43) = 0;
  v5 = 0;
  v53 = 0;
  if ( !a2
    || (v44 = (const GUID *)operator new(0xC8u),
        std::wstring::wstring(v57, a2),
        LODWORD(v43) = 1,
        v5 = NgcUtils::NgcKeyName::NgcKeyName(v44, v57),
        v53 = v5,
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v57),
        *(_QWORD *)v5 != *(_QWORD *)(v5 + 8))
    && !*(_QWORD *)(v5 + 24)
    && *(_QWORD *)(v5 + 32) == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0]
    && (!(unsigned __int8)std::operator!=<unsigned short>(v5 + 104, L"9DDC52DB-DC02-4A8C-B892-38DEF4FA748F")
     || !(unsigned __int8)std::operator!=<unsigned short>(v5 + 104, L"CA00CFA8-EB0F-42BA-A707-A3A43CDA5BD9")) )
  {
    v7 = (GUID *)operator new(0x20u);
    v44 = v7;
    *(_QWORD *)&v7->Data1 = 0;
    *(_QWORD *)v7->Data4 = 0;
    *(_QWORD *)&v7[1].Data1 = 0;
    *(_QWORD *)v7[1].Data4 = 0;
    v43 = v7;
    v51 = 0;
    v52 = 0;
    v8 = NgcKspServer::TransportManager::Instance();
    v9 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v8, &v44);
    v6 = NgcLocalTransport::LocalTransport::EnumContainers(*v9, &v51);
    if ( v45 )
      std::_Ref_count_base::_Decref(v45);
    if ( v6 < 0 )
    {
LABEL_14:
      std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(&v51);
      NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState::`scalar deleting destructor'(
        (NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState *)v7,
        v10);
      goto LABEL_88;
    }
    v46[0] = 0;
    v46[1] = 0;
    v11 = operator new(0x40u);
    *v11 = v11;
    v11[1] = v11;
    v11[2] = v11;
    *((_WORD *)v11 + 12) = 257;
    v46[0] = v11;
    for ( i = (const GUID *const *)v51; i != *((const GUID *const **)&v51 + 1); ++i )
    {
      v49 = 0;
      v50 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        memset_0(sz, 0, 0x64u);
        StringFromGUID2(*i, sz, 50);
        v13 = NgcKspServer::TransportManager::Instance();
        v14 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v13, &v44);
        v15 = NgcLocalTransport::LocalTransport::EnumKeys(*v14, *i, &v49);
        if ( v45 )
          std::_Ref_count_base::_Decref(v45);
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x33E,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v15,
            (int)"containerId: %ws",
            (const char *)sz);
          std::vector<std::unique_ptr<NgcTransportKeyInfo>>::_Tidy(&v49);
          std::map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(v46);
          std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(&v51);
          NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState::`scalar deleting destructor'(
            (NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState *)v7,
            v29);
          v6 = v15;
          goto LABEL_88;
        }
      }
      else
      {
        v16 = NgcKspServer::TransportManager::Instance();
        v17 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v16, &StringSid);
        v6 = NgcLocalTransport::LocalTransport::EnumKeys(*v17, *i, &v49);
        v18 = v48;
        if ( v48 )
          std::_Ref_count_base::_Decref(v48);
        if ( v6 < 0 )
        {
          if ( (unsigned int)dword_180122070 > 2 )
          {
            v44 = *i;
            LODWORD(v43) = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              (__int64)v18,
              (__int64)&dword_1801044F4);
          }
          v6 = HResultToSecurityStatus(v6);
          std::vector<std::unique_ptr<NgcTransportKeyInfo>>::_Tidy(&v49);
          goto LABEL_38;
        }
      }
      if ( !v5
        || (v19 = *(const void **)&(*i)[1].Data1,
            v20 = *(_QWORD *)(v5 + 8) - *(_QWORD *)v5,
            v20 == *(_QWORD *)(*i)[1].Data4 - (_QWORD)v19)
        && !memcmp_0(*(const void **)v5, v19, v20) )
      {
        v21 = *i;
        *i = 0;
        v57[0] = (char *)v21;
        v22 = v50;
        v50 = 0;
        v23 = (char *)*((_QWORD *)&v49 + 1);
        v24 = (char *)v49;
        v49 = 0u;
        v57[1] = v24;
        v57[2] = v23;
        v57[3] = v22;
        std::_Tree<std::_Tmap_traits<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>,std::less<std::unique_ptr<NgcTransportContainerInfo>>,std::allocator<std::pair<std::unique_ptr<NgcTransportContainerInfo> const,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>>,0>>::_Emplace<std::pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>>(
          v46,
          (__int64)v56,
          (__int64 *)v57);
        std::pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(v57);
      }
      std::vector<std::unique_ptr<NgcTransportKeyInfo>>::_Tidy(&v49);
    }
    NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v44, a1);
    v25 = *(__int64 **)v46[0];
LABEL_31:
    if ( *((_BYTE *)v25 + 25) )
    {
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v44);
      *v55 = (struct NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState *)v7;
      std::map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(v46);
      std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(&v51);
      goto LABEL_88;
    }
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW(*(PSID *)(v25[4] + 16), &StringSid) )
    {
      LastError = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x36B,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)(unsigned int)LastError,
          v42);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(v43) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1801044C7,
          0,
          0,
          (__int64)&v43);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = HResultToSecurityStatus(LastError);
LABEL_86:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v44);
LABEL_38:
      std::map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(v46);
      goto LABEL_14;
    }
    v27 = (unsigned __int64 **)v25[5];
    v28 = (unsigned __int64 **)v25[6];
    while ( 1 )
    {
      if ( v27 == v28 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        v37 = (__int64 **)v25[2];
        if ( *((_BYTE *)v37 + 25) )
        {
          for ( j = (__int64 *)v25[1]; !*((_BYTE *)j + 25) && v25 == (__int64 *)j[2]; j = (__int64 *)j[1] )
            v25 = j;
          v25 = j;
        }
        else
        {
          v25 = (__int64 *)v25[2];
          for ( k = *v37; !*((_BYTE *)k + 25); k = (__int64 *)*k )
            v25 = k;
        }
        goto LABEL_31;
      }
      if ( v5 )
      {
        v30 = *v27;
        v31 = (_QWORD *)(v5 + 104);
        if ( (*v27)[3] > 7 )
          v30 = (unsigned __int64 *)*v30;
        if ( *(_QWORD *)(v5 + 128) > 7u )
          v31 = (_QWORD *)*v31;
        if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                 v31,
                                 *(_QWORD *)(v5 + 120),
                                 v30,
                                 (*v27)[2]) )
          goto LABEL_63;
      }
      else if ( !(*v27)[6]
             && ((unsigned __int8)std::wstring::_Equal(*v27, L"9DDC52DB-DC02-4A8C-B892-38DEF4FA748F")
              || (unsigned __int8)std::wstring::_Equal(*v27, L"C611D9F1-CFF7-4B38-B5DE-7CB504C997ED")
              || (unsigned __int8)std::wstring::_Equal(*v27, L"CA00CFA8-EB0F-42BA-A707-A3A43CDA5BD9")) )
      {
        goto LABEL_63;
      }
      v32 = *v27;
      if ( (*v27)[6] )
      {
        v33 = (wchar_t *)(v32 + 4);
        if ( v32[7] > 7 )
          v33 = *(wchar_t **)v33;
      }
      else
      {
        v33 = 0;
      }
      if ( v32[10] )
      {
        v34 = v32 + 8;
        if ( v34[3] > 7u )
          v34 = (_QWORD *)*v34;
      }
      else
      {
        v34 = 0;
      }
      v35 = NgcKspCheckKeyAccessRight(v54, 0, StringSid, v26, v33, (__int64)v34, 0);
      v6 = v35;
      if ( v35 >= 0 )
      {
        v58 = 0;
        v59 = 0;
        v60 = 7;
        LOWORD(v58) = 0;
        v61 = 0;
        v62 = 0;
        v63 = 7;
        LOWORD(v61) = 0;
        v64 = 0;
        std::wstring::assign(&v61, L"RSA");
        v64 = 0;
        v36 = NgcUtils::NgcKeyName::BuildNgcKeyNameString(
                (PSID *)(v25[4] + 16),
                (const UUID *)v25[4],
                *v27 + 4,
                *v27 + 8,
                *v27,
                (__int64)&v58);
        v6 = v36;
        if ( v36 < 0 )
        {
          v6 = HResultToSecurityStatus(v36);
          std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(&v58);
          goto LABEL_86;
        }
        std::vector<NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumEntry>::push_back(v7->Data4, &v58);
        ++v7->Data1;
        std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(&v58);
      }
      else
      {
        if ( v35 != -2146893808 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x39D,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)(unsigned int)v6,
              v42);
          }
          else if ( (unsigned int)dword_180122070 > 2 )
          {
            LODWORD(v43) = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)&word_180104496,
              0,
              0,
              (__int64)&v43);
          }
          goto LABEL_86;
        }
        v6 = 0;
      }
LABEL_63:
      ++v27;
    }
  }
  v6 = -2146893785;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x318,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
      (const char *)0x80090027LL,
      v42);
  }
  else if ( (unsigned int)dword_180122070 > 2 )
  {
    LODWORD(v43) = -2146893785;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)&word_18010452E,
      0,
      0,
      (__int64)&v43);
  }
LABEL_88:
  std::unique_ptr<NgcUtils::NgcKeyName>::~unique_ptr<NgcUtils::NgcKeyName>(&v53);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c024  mov     [rsp-8+arg_18], rbx
0x18002c029  push    rbp
0x18002c02a  push    rsi
0x18002c02b  push    rdi
0x18002c02c  push    r12
0x18002c02e  push    r13
0x18002c030  push    r14
0x18002c032  push    r15
0x18002c034  lea     rbp, [rsp-0C0h]
0x18002c03c  sub     rsp, 1C0h
0x18002c043  mov     rax, cs:__security_cookie
0x18002c04a  xor     rax, rsp
0x18002c04d  mov     [rbp+0F0h+var_40], rax
0x18002c054  mov     [rbp+0F0h+var_138], r8
0x18002c058  mov     rdi, rdx
0x18002c05b  mov     r12, rcx
0x18002c05e  mov     [rbp+0F0h+var_140], rcx
0x18002c062  xor     r14d, r14d
0x18002c065  mov     dword ptr [rsp+1F0h+var_1B0], r14d
0x18002c06a  mov     r15d, r14d
0x18002c06d  mov     [rbp+0F0h+var_148], r14
0x18002c071  test    rdx, rdx
0x18002c074  jz      loc_18002C184
0x18002c07a  mov     ecx, 0C8h; Size
0x18002c07f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c084  mov     rbx, rax
0x18002c087  mov     [rsp+1F0h+var_1A8], rax
0x18002c08c  mov     rdx, rdi
0x18002c08f  lea     rcx, [rbp+0F0h+var_120]
0x18002c093  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002c098  nop
0x18002c099  mov     dword ptr [rsp+1F0h+var_1B0], 1
0x18002c0a1  lea     rdx, [rbp+0F0h+var_120]
0x18002c0a5  mov     rcx, rbx
0x18002c0a8  call    ??0NgcKeyName@NgcUtils@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcKeyName::NgcKeyName(std::wstring const &)
0x18002c0ad  mov     r15, rax
0x18002c0b0  mov     [rbp+0F0h+var_148], rax
0x18002c0b4  lea     rcx, [rbp+0F0h+var_120]
0x18002c0b8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18002c0bd  mov     rcx, [r15+8]
0x18002c0c1  cmp     [r15], rcx
0x18002c0c4  jz      short loc_18002C110
0x18002c0c6  xorps   xmm0, xmm0
0x18002c0c9  movq    rax, xmm0
0x18002c0ce  cmp     [r15+18h], rax
0x18002c0d2  jnz     short loc_18002C110
0x18002c0d4  psrldq  xmm0, 8
0x18002c0d9  movq    rax, xmm0
0x18002c0de  cmp     [r15+20h], rax
0x18002c0e2  jnz     short loc_18002C110
0x18002c0e4  lea     rdx, a9ddc52dbDc024a; "9DDC52DB-DC02-4A8C-B892-38DEF4FA748F"
0x18002c0eb  lea     rcx, [r15+68h]
0x18002c0ef  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18002c0f4  test    al, al
0x18002c0f6  jz      loc_18002C184
0x18002c0fc  lea     rdx, aCa00cfa8Eb0f42; "CA00CFA8-EB0F-42BA-A707-A3A43CDA5BD9"
0x18002c103  lea     rcx, [r15+68h]
0x18002c107  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18002c10c  test    al, al
0x18002c10e  jz      short loc_18002C184
0x18002c110  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18002c117  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18002c11c  mov     edi, 80090027h
0x18002c121  test    al, al
0x18002c123  jz      short loc_18002C145
0x18002c125  mov     rcx, [rbp+0F8h]; this
0x18002c12c  mov     r9d, edi; char *
0x18002c12f  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18002c136  mov     edx, 318h; void *
0x18002c13b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002c140  jmp     loc_18002C7BF
0x18002c145  mov     eax, cs:dword_180122070
0x18002c14b  cmp     eax, 2
0x18002c14e  jbe     loc_18002C7BF
0x18002c154  mov     dword ptr [rsp+1F0h+var_1B0], 80090027h
0x18002c15c  lea     rax, [rsp+1F0h+var_1B0]
0x18002c161  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18002c166  xor     r9d, r9d
0x18002c169  xor     r8d, r8d
0x18002c16c  lea     rdx, word_18010452E
0x18002c173  lea     rcx, dword_180122070
0x18002c17a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002c17f  jmp     loc_18002C7BF
0x18002c184  mov     ecx, 20h ; ' '; Size
0x18002c189  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c18e  mov     rsi, rax
0x18002c191  mov     [rsp+1F0h+var_1A8], rax
0x18002c196  mov     [rax], r14
0x18002c199  mov     [rax+8], r14
0x18002c19d  mov     [rax+10h], r14
0x18002c1a1  mov     [rax+18h], r14
0x18002c1a5  mov     [rsp+1F0h+var_1B0], rax
0x18002c1aa  xorps   xmm0, xmm0
0x18002c1ad  movdqu  [rbp+0F0h+var_160], xmm0
0x18002c1b2  mov     [rbp+0F0h+var_150], r14
0x18002c1b6  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18002c1bb  lea     rdx, [rsp+1F0h+var_1A8]
0x18002c1c0  mov     rcx, rax
0x18002c1c3  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18002c1c8  nop
0x18002c1c9  lea     rdx, [rbp+0F0h+var_160]
0x18002c1cd  mov     rcx, [rax]
0x18002c1d0  call    ?EnumContainers@LocalTransport@NgcLocalTransport@@UEAAJPEAV?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@@Z; NgcLocalTransport::LocalTransport::EnumContainers(std::vector<std::unique_ptr<NgcTransportContainerInfo>> *)
0x18002c1d5  mov     edi, eax
0x18002c1d7  mov     rcx, [rsp+1F0h+var_1A0]; this
0x18002c1dc  test    rcx, rcx
0x18002c1df  jz      short loc_18002C1E6
0x18002c1e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c1e6  test    edi, edi
0x18002c1e8  jns     short loc_18002C201
0x18002c1ea  lea     rcx, [rbp+0F0h+var_160]
0x18002c1ee  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(void)
0x18002c1f3  nop
0x18002c1f4  mov     rcx, rsi; this
0x18002c1f7  call    ??_GNgcKspKeyNameEnumState@NgcKspProvider@NgcKspServer@@QEAAPEAXI@Z; NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState::`scalar deleting destructor'(uint)
0x18002c1fc  jmp     loc_18002C7BF
0x18002c201  mov     [rsp+1F0h+var_198], r14
0x18002c206  mov     [rsp+1F0h+var_190], r14
0x18002c20b  mov     ecx, 40h ; '@'; Size
0x18002c210  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c215  mov     [rax], rax
0x18002c218  mov     [rax+8], rax
0x18002c21c  mov     [rax+10h], rax
0x18002c220  mov     word ptr [rax+18h], 101h
0x18002c226  mov     [rsp+1F0h+var_198], rax
0x18002c22b  mov     rbx, qword ptr [rbp+0F0h+var_160]
0x18002c22f  jmp     loc_18002C378
0x18002c234  xorps   xmm0, xmm0
0x18002c237  movdqu  [rsp+1F0h+var_178], xmm0
0x18002c23d  mov     [rbp+0F0h+var_168], r14
0x18002c241  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18002c248  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18002c24d  test    al, al
0x18002c24f  jz      short loc_18002C2B6
0x18002c251  xor     edx, edx; Val
0x18002c253  lea     r8d, [rdx+64h]; Size
0x18002c257  lea     rcx, [rbp+0F0h+sz]; void *
0x18002c25b  call    memset_0
0x18002c260  mov     r8d, 32h ; '2'; cchMax
0x18002c266  lea     rdx, [rbp+0F0h+sz]; lpsz
0x18002c26a  mov     rcx, [rbx]; rguid
0x18002c26d  call    cs:__imp_StringFromGUID2
0x18002c273  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18002c278  lea     rdx, [rsp+1F0h+var_1A8]
0x18002c27d  mov     rcx, rax
0x18002c280  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18002c285  nop
0x18002c286  lea     r8, [rsp+1F0h+var_178]
0x18002c28b  mov     rdx, [rbx]
0x18002c28e  mov     rcx, [rax]
0x18002c291  call    ?EnumKeys@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@PEAV?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@std@@@Z; NgcLocalTransport::LocalTransport::EnumKeys(_GUID const &,std::vector<std::unique_ptr<NgcTransportKeyInfo>> *)
0x18002c296  mov     r14d, eax
0x18002c299  mov     rcx, [rsp+1F0h+var_1A0]; this
0x18002c29e  test    rcx, rcx
0x18002c2a1  jz      short loc_18002C2A8
0x18002c2a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c2a8  test    r14d, r14d
0x18002c2ab  js      loc_18002C3DB
0x18002c2b1  xor     r14d, r14d
0x18002c2b4  jmp     short loc_18002C2F2
0x18002c2b6  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18002c2bb  lea     rdx, [rsp+1F0h+StringSid]
0x18002c2c0  mov     rcx, rax
0x18002c2c3  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18002c2c8  nop
0x18002c2c9  lea     r8, [rsp+1F0h+var_178]
0x18002c2ce  mov     rdx, [rbx]
0x18002c2d1  mov     rcx, [rax]
0x18002c2d4  call    ?EnumKeys@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@PEAV?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@std@@@Z; NgcLocalTransport::LocalTransport::EnumKeys(_GUID const &,std::vector<std::unique_ptr<NgcTransportKeyInfo>> *)
0x18002c2d9  mov     edi, eax
0x18002c2db  mov     rcx, [rsp+1F0h+var_180]; this
0x18002c2e0  test    rcx, rcx
0x18002c2e3  jz      short loc_18002C2EA
0x18002c2e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c2ea  test    edi, edi
0x18002c2ec  js      loc_18002C43C
0x18002c2f2  test    r15, r15
0x18002c2f5  jz      short loc_18002C31D
0x18002c2f7  mov     rax, [rbx]
0x18002c2fa  mov     rdx, [rax+10h]; Buf2
0x18002c2fe  mov     r8, [r15+8]
0x18002c302  sub     r8, [r15]; Size
0x18002c305  mov     rax, [rax+18h]
0x18002c309  sub     rax, rdx
0x18002c30c  cmp     r8, rax
0x18002c30f  jnz     short loc_18002C36A
0x18002c311  mov     rcx, [r15]; Buf1
0x18002c314  call    memcmp_0
0x18002c319  test    eax, eax
0x18002c31b  jnz     short loc_18002C36A
0x18002c31d  mov     rax, [rbx]
0x18002c320  mov     [rbx], r14
0x18002c323  mov     [rbp+0F0h+var_120], rax
0x18002c327  mov     rdx, [rbp+0F0h+var_168]
0x18002c32b  mov     [rbp+0F0h+var_168], r14
0x18002c32f  mov     rcx, qword ptr [rbp+0F0h+var_178+8]
0x18002c333  mov     qword ptr [rbp+0F0h+var_178+8], r14
0x18002c337  mov     rax, qword ptr [rsp+1F0h+var_178]
0x18002c33c  mov     qword ptr [rsp+1F0h+var_178], r14
0x18002c341  mov     [rbp+0F0h+var_118], rax
0x18002c345  mov     [rbp+0F0h+var_110], rcx
0x18002c349  mov     [rbp+0F0h+var_108], rdx
0x18002c34d  lea     r8, [rbp+0F0h+var_120]
0x18002c351  lea     rdx, [rbp+0F0h+var_130]
0x18002c355  lea     rcx, [rsp+1F0h+var_198]
0x18002c35a  call    ??$_Emplace@U?$pair@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@U?$less@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>,std::less<std::unique_ptr<NgcTransportContainerInfo>>,std::allocator<std::pair<std::unique_ptr<NgcTransportContainerInfo> const,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>>,0>>::_Emplace<std::pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>>(std::pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>> &&)
0x18002c35f  nop
0x18002c360  lea     rcx, [rbp+0F0h+var_120]
0x18002c364  call    ??1?$pair@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@std@@QEAA@XZ; std::pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~pair<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(void)
0x18002c369  nop
0x18002c36a  lea     rcx, [rsp+1F0h+var_178]
0x18002c36f  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportKeyInfo>>::_Tidy(void)
0x18002c374  add     rbx, 8
0x18002c378  cmp     rbx, qword ptr [rbp+0F0h+var_160+8]
0x18002c37c  jnz     loc_18002C234
0x18002c382  mov     rdx, r12; void *
0x18002c385  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18002c38a  call    ??0RpcCallerImpersonator@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator(void * const)
0x18002c38f  nop
0x18002c390  mov     rbx, [rsp+1F0h+var_198]
0x18002c395  mov     rbx, [rbx]
0x18002c398  cmp     [rbx+19h], r14b
0x18002c39c  jnz     loc_18002C799
0x18002c3a2  mov     [rsp+1F0h+StringSid], r14
0x18002c3a7  xor     edx, edx
0x18002c3a9  lea     rcx, [rsp+1F0h+StringSid]
0x18002c3ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c3b3  mov     rcx, [rbx+20h]
0x18002c3b7  lea     rdx, [rsp+1F0h+StringSid]; StringSid
0x18002c3bc  mov     rcx, [rcx+10h]; Sid
0x18002c3c0  call    cs:__imp_ConvertSidToStringSidW
0x18002c3c6  test    eax, eax
0x18002c3c8  jz      loc_18002C702
0x18002c3ce  mov     r14, [rbx+28h]
0x18002c3d2  mov     r12, [rbx+30h]
0x18002c3d6  jmp     loc_18002C61E
0x18002c3db  mov     rcx, [rbp+0F8h]; this
0x18002c3e2  lea     rax, [rbp+0F0h+sz]
0x18002c3e6  mov     [rsp+1F0h+var_1C8], rax; char *
0x18002c3eb  lea     rax, aContaineridWs; "containerId: %ws"
0x18002c3f2  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18002c3f7  mov     r9d, r14d; char *
0x18002c3fa  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18002c401  mov     edx, 33Eh; void *
0x18002c406  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002c40b  nop
0x18002c40c  lea     rcx, [rsp+1F0h+var_178]
0x18002c411  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportKeyInfo>>::_Tidy(void)
0x18002c416  nop
0x18002c417  lea     rcx, [rsp+1F0h+var_198]
0x18002c41c  call    ??1?$map@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@U?$less@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(void)
0x18002c421  nop
0x18002c422  lea     rcx, [rbp+0F0h+var_160]
0x18002c426  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(void)
0x18002c42b  nop
0x18002c42c  mov     rcx, rsi; this
0x18002c42f  call    ??_GNgcKspKeyNameEnumState@NgcKspProvider@NgcKspServer@@QEAAPEAXI@Z; NgcKspServer::NgcKspProvider::NgcKspKeyNameEnumState::`scalar deleting destructor'(uint)
0x18002c434  mov     edi, r14d
0x18002c437  jmp     loc_18002C7BF
0x18002c43c  mov     eax, cs:dword_180122070
0x18002c442  cmp     eax, 2
0x18002c445  jbe     short loc_18002C473
0x18002c447  mov     rax, [rbx]
0x18002c44a  mov     [rsp+1F0h+var_1A8], rax
0x18002c44f  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18002c453  lea     rax, [rsp+1F0h+var_1A8]
0x18002c458  mov     [rsp+1F0h+var_1C8], rax
0x18002c45d  lea     rax, [rsp+1F0h+var_1B0]
0x18002c462  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18002c467  lea     rdx, dword_1801044F4
0x18002c46e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18002c473  mov     ecx, edi; int
0x18002c475  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18002c47a  mov     edi, eax
0x18002c47c  lea     rcx, [rsp+1F0h+var_178]
0x18002c481  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportKeyInfo>>::_Tidy(void)
0x18002c486  nop
0x18002c487  lea     rcx, [rsp+1F0h+var_198]
0x18002c48c  call    ??1?$map@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@U?$less@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$vector@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportKeyInfo@@U?$default_delete@UNgcTransportKeyInfo@@@std@@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>::~map<std::unique_ptr<NgcTransportContainerInfo>,std::vector<std::unique_ptr<NgcTransportKeyInfo>>>(void)
0x18002c491  jmp     loc_18002C1EA
0x18002c496  test    r15, r15
0x18002c499  jz      short loc_18002C4CC
0x18002c49b  mov     r8, [r14]
0x18002c49e  lea     rcx, [r15+68h]
0x18002c4a2  mov     r9, [r8+10h]
0x18002c4a6  cmp     qword ptr [r8+18h], 7
0x18002c4ab  jbe     short loc_18002C4B0
0x18002c4ad  mov     r8, [r8]
0x18002c4b0  mov     rdx, [rcx+10h]
0x18002c4b4  cmp     qword ptr [rcx+18h], 7
0x18002c4b9  jbe     short loc_18002C4BE
0x18002c4bb  mov     rcx, [rcx]
0x18002c4be  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002c4c3  test    al, al
0x18002c4c5  jnz     short loc_18002C518
0x18002c4c7  jmp     loc_18002C61A
0x18002c4cc  mov     rcx, [r14]
0x18002c4cf  cmp     qword ptr [rcx+30h], 0
0x18002c4d4  jnz     short loc_18002C518
0x18002c4d6  lea     rdx, a9ddc52dbDc024a; "9DDC52DB-DC02-4A8C-B892-38DEF4FA748F"
  ... truncated ...
```
