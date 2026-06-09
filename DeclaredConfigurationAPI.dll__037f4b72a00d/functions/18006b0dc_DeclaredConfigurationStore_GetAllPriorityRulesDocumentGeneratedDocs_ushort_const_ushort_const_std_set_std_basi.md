# DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs(ushort const *,ushort const *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18006b0dc`
- end: `0x18006ba16`
- name: `?DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs@@YAJPEBG0AEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `2362`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180064de4`

## callees

- `0x18000b9e0`
- `0x18001438c`
- `0x180018ac0`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180054af4`
- `0x180058b08`
- `0x18005a378`
- `0x18006b0dc`
- `0x1800725e0`
- `0x18008cec8`
- `0x18008ea9c`
- `0x18008fcd4`
- `0x1800a036c`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100ad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b1c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b307`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b550`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b1c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b307`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b550`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b173`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b25a`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b318`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b173`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b25a`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b318`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006b1e5`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006b1e5`

## string_xrefs

- `0x18006b681`: `DCCDNUtil_GetRegistryString`
- `0x18006b83e`: `DCCDNUtil_GetRegistryString`
- `0x18006b8cf`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey`
- `0x18006b1f5`: `DmGetActiveUserSid`
- `0x18006b71d`: `GetEnrollmentIdSidStateDocIdVersionRawKey`
- `0x18006b240`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b3cc`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b604`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b708`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b799`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b824`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b8ba`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b940`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b99e`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b9e1`: `DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs`
- `0x18006b201`: `Failed DmGetActiveUserSid`
- `0x18006b275`: `Out of memory allocating scopeData.m_pszUserSid for user context`
- `0x18006b333`: `Out of memory allocating scopeData.m_pszUserSid for device context`
- `0x18006b957`: `Out of memory allocating scopeData.m_pszUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs(
        OLECHAR *a1,
        const OLECHAR *a2,
        __int64 a3)
{
  int ActiveUserSid; // ebx
  CDeclaredConfigurationLogger *v7; // rax
  CDeclaredConfigurationLogger *v8; // rax
  unsigned int v9; // edi
  unsigned int v10; // esi
  CDeclaredConfigurationLogger *v11; // rax
  CDeclaredConfigurationLogger *v12; // rax
  CDeclaredConfigurationLogger *v13; // rax
  CDeclaredConfigurationLogger *v14; // rax
  CDeclaredConfigurationLogger *v16; // rax
  CDeclaredConfigurationLogger *v17; // rax
  CDeclaredConfigurationLogger *v18; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  int EnrollmentIdSidStateDocIdKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v22; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v26; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v27; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  BSTR v30; // [rsp+80h] [rbp-80h] BYREF
  BSTR v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+94h] [rbp-6Ch]
  HKEY *p_hKey; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v35; // [rsp+A0h] [rbp-60h] BYREF
  char v36; // [rsp+A8h] [rbp-58h]
  int *v37; // [rsp+B0h] [rbp-50h]
  unsigned __int16 **v38; // [rsp+B8h] [rbp-48h]
  unsigned __int16 **v39; // [rsp+C0h] [rbp-40h]
  char v40; // [rsp+C8h] [rbp-38h]
  _BYTE v41[16]; // [rsp+D0h] [rbp-30h] BYREF
  HKEY *v42; // [rsp+E0h] [rbp-20h] BYREF
  HKEY v43; // [rsp+E8h] [rbp-18h] BYREF
  char v44; // [rsp+F0h] [rbp-10h]

  EnrollmentIdSidStateDocIdKey = 0;
  v22 = (unsigned __int16 *)&word_180142E98;
  v21 = (unsigned __int16 *)&word_180142E98;
  v37 = &EnrollmentIdSidStateDocIdKey;
  v38 = &v22;
  v39 = &v21;
  v40 = 1;
  if ( !a1 || !a2 )
  {
    v21 = L"pszEnrollmentId or pszContext is a nullptr";
    ActiveUserSid = -2147024809;
    EnrollmentIdSidStateDocIdKey = -2147024809;
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
      v22,
      v21,
      EnrollmentIdSidStateDocIdKey);
    return (unsigned int)ActiveUserSid;
  }
  v25 = 0;
  v24 = 0;
  psz = 0;
  v31 = 0;
  v32 = 0;
  v33 = 63;
  v30 = SysAllocString(a1);
  if ( !v30 )
  {
    v22 = L"SysAllocString";
    v21 = L"Out of memory allocating scopeData.m_pszEnrollmentId";
    EnrollmentIdSidStateDocIdKey = -2147024882;
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
LABEL_55:
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v18 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v18,
        L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
        v22,
        v21,
        EnrollmentIdSidStateDocIdKey);
    }
    return 2147942414LL;
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"user") )
  {
    if ( (unsigned int)_o__wcsicmp(a2, L"device") )
    {
      v21 = L"Out of memory allocating scopeData.m_pszUserSid";
      EnrollmentIdSidStateDocIdKey = -2147024882;
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      goto LABEL_55;
    }
    v31 = SysAllocString(a2);
    if ( !v31 )
    {
      v22 = L"SysAllocString";
      v21 = L"Out of memory allocating scopeData.m_pszUserSid for device context";
      EnrollmentIdSidStateDocIdKey = -2147024882;
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      goto LABEL_55;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &psz,
      0);
    ActiveUserSid = DmGetActiveUserSid(&psz);
    EnrollmentIdSidStateDocIdKey = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      v22 = L"DmGetActiveUserSid";
      v21 = L"Failed DmGetActiveUserSid";
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v7 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v7,
          L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
          v22,
          v21,
          EnrollmentIdSidStateDocIdKey);
      }
      return (unsigned int)ActiveUserSid;
    }
    v31 = SysAllocString(psz);
    if ( !v31 )
    {
      v22 = L"SysAllocString";
      v21 = L"Out of memory allocating scopeData.m_pszUserSid for user context";
      EnrollmentIdSidStateDocIdKey = -2147024882;
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      goto LABEL_55;
    }
    v32 = 1;
  }
  hKey = 0;
  p_hKey = &hKey;
  v35 = 0;
  v36 = 1;
  ActiveUserSid = GetResultsEnrollmentIdSidStateKey(&v30, &v35);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( ActiveUserSid < 0 )
  {
    if ( ActiveUserSid == -2147024894 )
    {
      v25 = 0;
      v24 = 0;
      ActiveUserSid = 0;
    }
  }
  else
  {
    ActiveUserSid = GetDocIdSubKeys(hKey);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  EnrollmentIdSidStateDocIdKey = ActiveUserSid;
  if ( ActiveUserSid < 0 )
  {
    v22 = L"GetAllDocIds";
    v21 = a1;
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v8 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v8,
        L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
        v22,
        v21,
        EnrollmentIdSidStateDocIdKey);
    }
    return (unsigned int)ActiveUserSid;
  }
  p_hKey = (HKEY *)&v25;
  v35 = &v24;
  v36 = 1;
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(a3);
  v9 = 0;
  if ( !v24 )
  {
LABEL_34:
    ActiveUserSid = EnrollmentIdSidStateDocIdKey;
    v36 = 0;
    lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v11 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v11,
        L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
        v22,
        v21,
        EnrollmentIdSidStateDocIdKey);
    }
    return (unsigned int)ActiveUserSid;
  }
  while ( 1 )
  {
    v27 = 0;
    v26 = 0;
    v42 = &v27;
    v43 = 0;
    v44 = 1;
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     (struct DeclaredConfigurationScopeData *)&v30,
                                     *(const unsigned __int16 **)(v25 + 8LL * v9),
                                     &v43,
                                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v42);
    v10 = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v22 = L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey";
      v21 = *(unsigned __int16 **)(v25 + 8LL * v9);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      v36 = 0;
      lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v17 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v17,
          L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
          v22,
          v21,
          EnrollmentIdSidStateDocIdKey);
      }
      return v10;
    }
    v29 = 0;
    v42 = (HKEY *)&v29;
    v43 = 0;
    v44 = 1;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v27, 0, L"MostRecentVersion", (unsigned __int16 **)&v43);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v42);
    v10 = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v22 = L"DCCDNUtil_GetRegistryString";
      v21 = *(unsigned __int16 **)(v25 + 8LL * v9);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      v36 = 0;
      lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v16 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v16,
          L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
          v22,
          v21,
          EnrollmentIdSidStateDocIdKey);
      }
      return v10;
    }
    if ( !v29 )
      break;
    v42 = &v26;
    v43 = 0;
    v44 = 1;
    EnrollmentIdSidStateDocIdKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                     (unsigned int)&v30,
                                     *(_QWORD *)(v25 + 8LL * v9),
                                     v29,
                                     (unsigned int)&v43,
                                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v42);
    v10 = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v22 = L"GetEnrollmentIdSidStateDocIdVersionRawKey";
      v21 = *(unsigned __int16 **)(v25 + 8LL * v9);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      v36 = 0;
      lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v13 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v13,
          L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
          v22,
          v21,
          EnrollmentIdSidStateDocIdKey);
      }
      return v10;
    }
    hKey = 0;
    v42 = &hKey;
    v43 = 0;
    v44 = 1;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v26, 0, L"osdefinedscenario", (unsigned __int16 **)&v43);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v42);
    v10 = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v22 = L"DCCDNUtil_GetRegistryString";
      v21 = *(unsigned __int16 **)(v25 + 8LL * v9);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      v36 = 0;
      lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v12 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v12,
          L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
          v22,
          v21,
          EnrollmentIdSidStateDocIdKey);
      }
      return v10;
    }
    if ( !hKey )
    {
      v21 = L"osDefinedScenario or osDefinedScenario.get() is a nullptr";
      EnrollmentIdSidStateDocIdKey = -2147467259;
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      v36 = 0;
      lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      goto LABEL_45;
    }
    if ( !(unsigned int)_o__wcsicmp(L"besteffortsettingsafterCR", hKey) )
    {
      std::wstring::wstring((__int64)&v42, *(_QWORD *)(v25 + 8LL * v9));
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        a3,
        v41,
        &v42);
      std::wstring::_Tidy_deallocate(&v42);
    }
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v29);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
    if ( ++v9 >= v24 )
      goto LABEL_34;
  }
  v21 = L"mostRecentVersion or mostRecentVersion.get() is a nullptr";
  EnrollmentIdSidStateDocIdKey = -2147467259;
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v29);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
  v36 = 0;
  lambda_f6684aa64fb5f0146ee706879b07c738_::operator()(&p_hKey);
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
LABEL_45:
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v14 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v14,
      L"DeclaredConfigurationStore_GetAllPriorityRulesDocumentGeneratedDocs",
      v22,
      v21,
      EnrollmentIdSidStateDocIdKey);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18006b0dc  mov     [rsp-8+arg_18], rbx
0x18006b0e1  push    rbp
0x18006b0e2  push    rsi
0x18006b0e3  push    rdi
0x18006b0e4  push    r14
0x18006b0e6  push    r15
0x18006b0e8  lea     rbp, [rsp-10h]
0x18006b0ed  sub     rsp, 110h
0x18006b0f4  mov     rax, cs:__security_cookie
0x18006b0fb  xor     rax, rsp
0x18006b0fe  mov     [rbp+30h+var_30], rax
0x18006b102  mov     r14, r8
0x18006b105  mov     rbx, rdx
0x18006b108  mov     rdi, rcx
0x18006b10b  xor     r15d, r15d
0x18006b10e  mov     [rsp+130h+var_100], r15d
0x18006b113  lea     rax, word_180142E98
0x18006b11a  mov     [rsp+130h+var_F0], rax
0x18006b11f  mov     [rsp+130h+var_F8], rax
0x18006b124  lea     rax, [rsp+130h+var_100]
0x18006b129  mov     [rbp+30h+var_80], rax
0x18006b12d  lea     rax, [rsp+130h+var_F0]
0x18006b132  mov     [rbp+30h+var_78], rax
0x18006b136  lea     rax, [rsp+130h+var_F8]
0x18006b13b  mov     [rbp+30h+var_70], rax
0x18006b13f  mov     [rbp+30h+var_68], 1
0x18006b143  test    rcx, rcx
0x18006b146  jz      loc_18006B9B5
0x18006b14c  test    rdx, rdx
0x18006b14f  jz      loc_18006B9B5
0x18006b155  mov     [rsp+130h+var_D8], r15
0x18006b15a  mov     [rsp+130h+var_E0], r15d
0x18006b15f  mov     [rsp+130h+psz], r15
0x18006b164  mov     [rbp+30h+var_A8], r15
0x18006b168  mov     [rbp+30h+var_A0], r15d
0x18006b16c  mov     [rbp+30h+var_9C], 3Fh ; '?'
0x18006b173  call    cs:__imp_SysAllocString
0x18006b179  mov     [rbp+30h+var_B0], rax
0x18006b17d  test    rax, rax
0x18006b180  jnz     short loc_18006B1BC
0x18006b182  lea     rax, aSysallocstring; "SysAllocString"
0x18006b189  mov     [rsp+130h+var_F0], rax
0x18006b18e  lea     rax, aOutOfMemoryAll_5; "Out of memory allocating scopeData.m_ps"...
0x18006b195  mov     [rsp+130h+var_F8], rax
0x18006b19a  mov     [rsp+130h+var_100], 8007000Eh
0x18006b1a2  lea     rcx, [rbp+30h+var_B0]; this
0x18006b1a6  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006b1ab  nop
0x18006b1ac  lea     rcx, [rsp+130h+psz]
0x18006b1b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b1b6  nop
0x18006b1b7  jmp     loc_18006B980
0x18006b1bc  lea     rdx, aUser_0; "user"
0x18006b1c3  mov     rcx, rbx
0x18006b1c6  call    cs:__imp__o__wcsicmp
0x18006b1cc  test    eax, eax
0x18006b1ce  jnz     loc_18006B2FD
0x18006b1d4  xor     edx, edx
0x18006b1d6  lea     rcx, [rsp+130h+psz]
0x18006b1db  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006b1e0  lea     rcx, [rsp+130h+psz]
0x18006b1e5  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18006b1eb  mov     ebx, eax
0x18006b1ed  mov     [rsp+130h+var_100], eax
0x18006b1f1  test    eax, eax
0x18006b1f3  jns     short loc_18006B255
0x18006b1f5  lea     rax, aDmgetactiveuse_1; "DmGetActiveUserSid"
0x18006b1fc  mov     [rsp+130h+var_F0], rax
0x18006b201  lea     rax, aFailedDmgetact; "Failed DmGetActiveUserSid"
0x18006b208  mov     [rsp+130h+var_F8], rax
0x18006b20d  lea     rcx, [rbp+30h+var_B0]; this
0x18006b211  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006b216  nop
0x18006b217  lea     rcx, [rsp+130h+psz]
0x18006b21c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b221  nop
0x18006b222  cmp     [rsp+130h+var_100], r15d
0x18006b227  jge     short loc_18006B250
0x18006b229  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18006b22e  mov     ecx, [rsp+130h+var_100]
0x18006b232  mov     [rsp+130h+var_110], ecx; int
0x18006b236  mov     r9, [rsp+130h+var_F8]; unsigned __int16 *
0x18006b23b  mov     r8, [rsp+130h+var_F0]; unsigned __int16 *
0x18006b240  lea     rdx, aDeclaredconfig_240; "DeclaredConfigurationStore_GetAllPriori"...
0x18006b247  mov     rcx, rax; this
0x18006b24a  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18006b24f  nop
0x18006b250  jmp     loc_18006B9F1
0x18006b255  mov     rcx, [rsp+130h+psz]; psz
0x18006b25a  call    cs:__imp_SysAllocString
0x18006b260  mov     [rbp+30h+var_A8], rax
0x18006b264  test    rax, rax
0x18006b267  jnz     short loc_18006B2A3
0x18006b269  lea     rax, aSysallocstring; "SysAllocString"
0x18006b270  mov     [rsp+130h+var_F0], rax
0x18006b275  lea     rax, aOutOfMemoryAll_7; "Out of memory allocating scopeData.m_ps"...
0x18006b27c  mov     [rsp+130h+var_F8], rax
0x18006b281  mov     [rsp+130h+var_100], 8007000Eh
0x18006b289  lea     rcx, [rbp+30h+var_B0]; this
0x18006b28d  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006b292  nop
0x18006b293  lea     rcx, [rsp+130h+psz]
0x18006b298  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b29d  nop
0x18006b29e  jmp     loc_18006B980
0x18006b2a3  mov     [rbp+30h+var_A0], 1
0x18006b2aa  test    rax, rax
0x18006b2ad  jz      loc_18006B957
0x18006b2b3  mov     [rsp+130h+hKey], r15
0x18006b2b8  lea     rax, [rsp+130h+hKey]
0x18006b2bd  mov     [rbp+30h+var_98], rax
0x18006b2c1  mov     [rbp+30h+var_90], r15
0x18006b2c5  mov     [rbp+30h+var_88], 1
0x18006b2c9  lea     rdx, [rbp+30h+var_90]
0x18006b2cd  lea     rcx, [rbp+30h+var_B0]
0x18006b2d1  call    GetResultsEnrollmentIdSidStateKey
0x18006b2d6  mov     ebx, eax
0x18006b2d8  lea     rcx, [rbp+30h+var_98]
0x18006b2dc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18006b2e1  test    ebx, ebx
0x18006b2e3  js      short loc_18006B361
0x18006b2e5  lea     r8, [rsp+130h+var_D8]
0x18006b2ea  lea     rdx, [rsp+130h+var_E0]
0x18006b2ef  mov     rcx, [rsp+130h+hKey]; hKey
0x18006b2f4  call    GetDocIdSubKeys
0x18006b2f9  mov     ebx, eax
0x18006b2fb  jmp     short loc_18006B376
0x18006b2fd  lea     rdx, aDevice_4; "device"
0x18006b304  mov     rcx, rbx
0x18006b307  call    cs:__imp__o__wcsicmp
0x18006b30d  test    eax, eax
0x18006b30f  jnz     loc_18006B957
0x18006b315  mov     rcx, rbx; psz
0x18006b318  call    cs:__imp_SysAllocString
0x18006b31e  mov     [rbp+30h+var_A8], rax
0x18006b322  test    rax, rax
0x18006b325  jnz     short loc_18006B2B3
0x18006b327  lea     rax, aSysallocstring; "SysAllocString"
0x18006b32e  mov     [rsp+130h+var_F0], rax
0x18006b333  lea     rax, aOutOfMemoryAll_3; "Out of memory allocating scopeData.m_ps"...
0x18006b33a  mov     [rsp+130h+var_F8], rax
0x18006b33f  mov     [rsp+130h+var_100], 8007000Eh
0x18006b347  lea     rcx, [rbp+30h+var_B0]; this
0x18006b34b  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006b350  nop
0x18006b351  lea     rcx, [rsp+130h+psz]
0x18006b356  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b35b  nop
0x18006b35c  jmp     loc_18006B980
0x18006b361  cmp     ebx, 80070002h
0x18006b367  jnz     short loc_18006B376
0x18006b369  mov     [rsp+130h+var_D8], r15
0x18006b36e  mov     [rsp+130h+var_E0], r15d
0x18006b373  mov     ebx, r15d
0x18006b376  lea     rcx, [rsp+130h+hKey]
0x18006b37b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006b380  mov     [rsp+130h+var_100], ebx
0x18006b384  test    ebx, ebx
0x18006b386  jns     short loc_18006B3E1
0x18006b388  lea     rax, aGetalldocids; "GetAllDocIds"
0x18006b38f  mov     [rsp+130h+var_F0], rax
0x18006b394  mov     [rsp+130h+var_F8], rdi
0x18006b399  lea     rcx, [rbp+30h+var_B0]; this
0x18006b39d  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006b3a2  nop
0x18006b3a3  lea     rcx, [rsp+130h+psz]
0x18006b3a8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b3ad  nop
0x18006b3ae  cmp     [rsp+130h+var_100], r15d
0x18006b3b3  jge     short loc_18006B3DC
0x18006b3b5  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18006b3ba  mov     ecx, [rsp+130h+var_100]
0x18006b3be  mov     [rsp+130h+var_110], ecx; int
0x18006b3c2  mov     r9, [rsp+130h+var_F8]; unsigned __int16 *
0x18006b3c7  mov     r8, [rsp+130h+var_F0]; unsigned __int16 *
0x18006b3cc  lea     rdx, aDeclaredconfig_240; "DeclaredConfigurationStore_GetAllPriori"...
0x18006b3d3  mov     rcx, rax; this
0x18006b3d6  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18006b3db  nop
0x18006b3dc  jmp     loc_18006B9F1
0x18006b3e1  lea     rax, [rsp+130h+var_D8]
0x18006b3e6  mov     [rbp+30h+var_98], rax
0x18006b3ea  lea     rax, [rsp+130h+var_E0]
0x18006b3ef  mov     [rbp+30h+var_90], rax
0x18006b3f3  mov     [rbp+30h+var_88], 1
0x18006b3f7  mov     rcx, r14
0x18006b3fa  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x18006b3ff  mov     edi, r15d
0x18006b402  cmp     [rsp+130h+var_E0], r15d
0x18006b407  jbe     loc_18006B5BF
0x18006b40d  mov     [rsp+130h+var_C8], r15
0x18006b412  mov     [rsp+130h+var_D0], r15
0x18006b417  lea     rax, [rsp+130h+var_C8]
0x18006b41c  mov     [rbp+30h+var_50], rax
0x18006b420  mov     [rbp+30h+var_48], r15
0x18006b424  mov     [rbp+30h+var_40], 1
0x18006b428  mov     ebx, edi
0x18006b42a  xor     r9d, r9d; int
0x18006b42d  lea     r8, [rbp+30h+var_48]; HKEY *
0x18006b431  mov     rdx, [rsp+130h+var_D8]
0x18006b436  mov     rdx, [rdx+rbx*8]; unsigned __int16 *
0x18006b43a  lea     rcx, [rbp+30h+var_B0]; struct DeclaredConfigurationScopeData *
0x18006b43e  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18006b443  mov     [rsp+130h+var_100], eax
0x18006b447  lea     rcx, [rbp+30h+var_50]
0x18006b44b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18006b450  mov     esi, [rsp+130h+var_100]
0x18006b454  test    esi, esi
0x18006b456  js      loc_18006B8CF
0x18006b45c  mov     [rsp+130h+var_B8], r15
0x18006b461  lea     rax, [rsp+130h+var_B8]
0x18006b466  mov     [rbp+30h+var_50], rax
0x18006b46a  mov     [rbp+30h+var_48], r15
0x18006b46e  mov     [rbp+30h+var_40], 1
0x18006b472  lea     r9, [rbp+30h+var_48]; unsigned __int16 **
0x18006b476  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18006b47d  xor     edx, edx; unsigned __int16 *
0x18006b47f  mov     rcx, [rsp+130h+var_C8]; HKEY
0x18006b484  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18006b489  mov     [rsp+130h+var_100], eax
0x18006b48d  lea     rcx, [rbp+30h+var_50]
0x18006b491  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x18006b496  mov     esi, [rsp+130h+var_100]
0x18006b49a  test    esi, esi
0x18006b49c  js      loc_18006B83E
0x18006b4a2  mov     r8, [rsp+130h+var_B8]
0x18006b4a7  test    r8, r8
0x18006b4aa  jz      loc_18006B7AE
0x18006b4b0  lea     rax, [rsp+130h+var_D0]
0x18006b4b5  mov     [rbp+30h+var_50], rax
0x18006b4b9  mov     [rbp+30h+var_48], r15
0x18006b4bd  mov     [rbp+30h+var_40], 1
0x18006b4c1  mov     [rsp+130h+var_110], r15d
0x18006b4c6  lea     r9, [rbp+30h+var_48]
0x18006b4ca  mov     rdx, [rsp+130h+var_D8]
0x18006b4cf  mov     rdx, [rdx+rbx*8]
0x18006b4d3  lea     rcx, [rbp+30h+var_B0]
0x18006b4d7  call    GetEnrollmentIdSidStateDocIdVersionRawKey
0x18006b4dc  mov     [rsp+130h+var_100], eax
0x18006b4e0  lea     rcx, [rbp+30h+var_50]
0x18006b4e4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18006b4e9  mov     esi, [rsp+130h+var_100]
0x18006b4ed  test    esi, esi
0x18006b4ef  js      loc_18006B71D
0x18006b4f5  mov     [rsp+130h+hKey], r15
0x18006b4fa  lea     rax, [rsp+130h+hKey]
0x18006b4ff  mov     [rbp+30h+var_50], rax
0x18006b503  mov     [rbp+30h+var_48], r15
0x18006b507  mov     [rbp+30h+var_40], 1
0x18006b50b  lea     r9, [rbp+30h+var_48]; unsigned __int16 **
0x18006b50f  lea     r8, aOsdefinedscena; "osdefinedscenario"
0x18006b516  xor     edx, edx; unsigned __int16 *
0x18006b518  mov     rcx, [rsp+130h+var_D0]; HKEY
0x18006b51d  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18006b522  mov     [rsp+130h+var_100], eax
0x18006b526  lea     rcx, [rbp+30h+var_50]
0x18006b52a  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x18006b52f  mov     esi, [rsp+130h+var_100]
0x18006b533  test    esi, esi
0x18006b535  js      loc_18006B681
0x18006b53b  mov     rdx, [rsp+130h+hKey]
0x18006b540  test    rdx, rdx
0x18006b543  jz      loc_18006B619
0x18006b549  lea     rcx, aBesteffortsett; "besteffortsettingsafterCR"
0x18006b550  call    cs:__imp__o__wcsicmp
0x18006b556  test    eax, eax
0x18006b558  jnz     short loc_18006B588
0x18006b55a  mov     rdx, [rsp+130h+var_D8]
0x18006b55f  mov     rdx, [rdx+rbx*8]
0x18006b563  lea     rcx, [rbp+30h+var_50]
0x18006b567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b56c  nop
0x18006b56d  lea     r8, [rbp+30h+var_50]
0x18006b571  lea     rdx, [rbp+30h+var_60]
0x18006b575  mov     rcx, r14
0x18006b578  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18006b57d  nop
0x18006b57e  lea     rcx, [rbp+30h+var_50]
0x18006b582  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b587  nop
0x18006b588  lea     rcx, [rsp+130h+hKey]
0x18006b58d  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18006b592  nop
0x18006b593  lea     rcx, [rsp+130h+var_B8]
0x18006b598  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18006b59d  nop
0x18006b59e  lea     rcx, [rsp+130h+var_D0]
0x18006b5a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006b5a8  nop
0x18006b5a9  lea     rcx, [rsp+130h+var_C8]
0x18006b5ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006b5b3  inc     edi
0x18006b5b5  cmp     edi, [rsp+130h+var_E0]
0x18006b5b9  jb      loc_18006B40D
0x18006b5bf  mov     ebx, [rsp+130h+var_100]
0x18006b5c3  mov     [rbp+30h+var_88], r15b
0x18006b5c7  lea     rcx, [rbp+30h+var_98]
0x18006b5cb  call    _lambda_f6684aa64fb5f0146ee706879b07c738___operator__
0x18006b5d0  nop
0x18006b5d1  lea     rcx, [rbp+30h+var_B0]; this
  ... truncated ...
```
