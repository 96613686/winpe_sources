# DeclaredConfigurationStore_ProcessTemplateBulkVariable(DeclaredConfigurationScopeData *,ushort const *,ushort const *)

- ea: `0x180080e90`
- end: `0x180081822`
- name: `?DeclaredConfigurationStore_ProcessTemplateBulkVariable@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1@Z`
- size: `2450`
- prototype: `int(struct DeclaredConfigurationScopeData *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x1800117dc`
- `0x180014348`
- `0x180019d38`
- `0x18001c2d0`
- `0x18001c32c`
- `0x18001cb40`
- `0x18001ce5c`
- `0x18001cec8`
- `0x18001d020`
- `0x18001d0b0`
- `0x18001d37c`
- `0x1800370d4`
- `0x180058148`
- `0x18005e934`
- `0x1800725e0`
- `0x180076c10`
- `0x180080e90`
- `0x180086c10`
- `0x18008ea9c`
- `0x18008f6b0`
- `0x180090260`
- `0x1800a1004`
- `0x1800f5c8c`
- `0x1800f6864`
- `0x1800f9d70`
- `0x180100ad8`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800812d2`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800812d2`
- `DeclaredConfiguration!DMOrchestratorConfig` at `0x18008168f`
- `DeclaredConfiguration!DMOrchestratorConfig` at `0x18008168f`
- `DeclaredConfiguration!DMOrchestratorSetInstanceVariable` at `0x18008126c`
- `DeclaredConfiguration!DMOrchestratorSetInstanceVariable` at `0x180081370`
- `DeclaredConfiguration!DMOrchestratorSetInstanceVariable` at `0x1800813c5`
- `DeclaredConfiguration!DMOrchestratorSetInstanceVariable` at `0x18008126c`
- `DeclaredConfiguration!DMOrchestratorSetInstanceVariable` at `0x180081370`
- `DeclaredConfiguration!DMOrchestratorSetInstanceVariable` at `0x1800813c5`
- `OLEAUT32!__imp_VariantInit` at `0x1800815a8`
- `OLEAUT32!__imp_VariantInit` at `0x1800815a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800816ca`
- `OLEAUT32!__imp_VariantClear` at `0x180081774`
- `OLEAUT32!__imp_VariantClear` at `0x1800816ca`
- `OLEAUT32!__imp_VariantClear` at `0x180081774`

## string_xrefs

- `0x180080f73`: `BulkTemplateVersion`
- `0x18008135e`: `@#InstanceAmount#`
- `0x1800813b3`: `@#InstanceAmount#`
- `0x18008162e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180080f9c`: `DCCDNUtil_GetRegistryString`
- `0x180081427`: `DCCDNUtil_SetRegistryString`
- `0x18008155a`: `DCCDNUtil_SetRegistryString`
- `0x180080f39`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey`
- `0x18008106c`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x18008160e`: `DeclaredConfigurationStore_WriteResultData`
- `0x1800814fa`: `GetEnrollmentIdSidStateDocIdVersionRawKey`
- `0x180080f40`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x180080fa3`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x180081073`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x1800810e9`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x180081151`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x1800811c3`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x18008129d`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x1800812f7`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x180081393`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x180081435`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x18008150c`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x180081615`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x1800816b6`: `DeclaredConfigurationStore_ProcessTemplateBulkVariable`
- `0x1800810e2`: `CreateXmlParser`
- `0x1800816af`: `DMOrchestratorConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DeclaredConfigurationStore_ProcessTemplateBulkVariable(
        const unsigned __int16 **a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int EnrollmentIdSidStateDocIdKey; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  CDeclaredConfigurationLogger *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // r8
  const unsigned __int16 *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r8
  int PersistedDocument; // edi
  CDeclaredConfigurationLogger *v16; // rax
  CDeclaredConfigurationLogger *v17; // rax
  CDeclaredConfigurationLogger *v18; // rax
  CDeclaredConfigurationLogger *v19; // rax
  _QWORD *v20; // rdi
  _QWORD *i; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // r9
  int EnrollmentIdSidStateDocIdVersionRawKey; // esi
  CDeclaredConfigurationLogger *v25; // rax
  unsigned int v26; // edi
  CDeclaredConfigurationLogger *v27; // rax
  CDeclaredConfigurationLogger *v28; // rax
  CDeclaredConfigurationLogger *v29; // rax
  unsigned __int16 **v30; // rcx
  CDeclaredConfigurationLogger *v31; // rax
  unsigned __int16 **v32; // rdx
  CDeclaredConfigurationLogger *v33; // rax
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r9
  const unsigned __int16 *v36; // rdx
  CDeclaredConfigurationLogger *v37; // rax
  _QWORD *v38; // rdx
  CDeclaredConfigurationLogger *v39; // rax
  CDeclaredConfigurationLogger *v40; // rax
  int v41; // [rsp+20h] [rbp-E0h]
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v43; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v44; // [rsp+50h] [rbp-B0h] BYREF
  struct IXmlReader *v45; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v46; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v47; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v48; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v49; // [rsp+74h] [rbp-8Ch] BYREF
  void *v50; // [rsp+78h] [rbp-88h] BYREF
  HKEY v51; // [rsp+80h] [rbp-80h] BYREF
  char v52; // [rsp+88h] [rbp-78h]
  _BYTE v53[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v54; // [rsp+98h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  HKEY *v56; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v57; // [rsp+F0h] [rbp-10h] BYREF
  char v58; // [rsp+F8h] [rbp-8h]
  void **p_Block; // [rsp+100h] [rbp+0h]
  char v60; // [rsp+108h] [rbp+8h]
  _QWORD v61[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v62[4]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v63; // [rsp+150h] [rbp+50h]
  unsigned __int16 *v64[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v65; // [rsp+178h] [rbp+78h]
  _QWORD v66[4]; // [rsp+180h] [rbp+80h] BYREF
  char *v67; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v68; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 *v69[3]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int64 v70; // [rsp+378h] [rbp+278h]
  unsigned __int8 v71; // [rsp+400h] [rbp+300h]
  unsigned int v72; // [rsp+404h] [rbp+304h]
  _BYTE v73[752]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v74[8]; // [rsp+740h] [rbp+640h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+688h]

  Block = 0;
  v46 = 0;
  v43 = 0;
  if ( a1 && a2 && a3 )
  {
    v50 = &v46;
    v51 = 0;
    v52 = 1;
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     (struct DeclaredConfigurationScopeData *)a1,
                                     a2,
                                     &v51,
                                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v50);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey",
        &word_180142E98,
        EnrollmentIdSidStateDocIdKey);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
      return (unsigned int)EnrollmentIdSidStateDocIdKey;
    }
    p_Block = &Block;
    v60 = 1;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(
                                     v46,
                                     0,
                                     L"BulkTemplateVersion",
                                     (unsigned __int16 **)&Block);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v9 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v9,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DCCDNUtil_GetRegistryString",
        L"Get most recent version",
        EnrollmentIdSidStateDocIdKey);
LABEL_9:
      operator delete(Block);
      Block = 0;
      goto LABEL_6;
    }
    DCDocument::DCDocument((DCDocument *)v64);
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    std::wstring::_Assign<unsigned short>((char **)v64, a2, (char *)v11);
    v12 = a1[1];
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    std::wstring::_Assign<unsigned short>(&v67, v12, (char *)v13);
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)Block + v14) );
    std::wstring::_Assign<unsigned short>(&v68, Block, (char *)v14);
    DCDocument::DCDocument((DCDocument *)v73);
    PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(a1, v46, Block, 0, v64, 1);
    if ( PersistedDocument < 0 )
    {
      v16 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v16,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DeclaredConfigurationStore_GetPersistedDocument",
        &word_180142E98,
        PersistedDocument);
LABEL_18:
      DCDocument::~DCDocument((DCDocument *)v73);
      DCDocument::~DCDocument((DCDocument *)v64);
      operator delete(Block);
      Block = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
      return (unsigned int)PersistedDocument;
    }
    v45 = 0;
    PersistedDocument = CreateXmlParser(a3, &v45);
    if ( PersistedDocument < 0 )
    {
      v17 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v17,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"CreateXmlParser",
        &word_180142E98,
        PersistedDocument);
LABEL_21:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      goto LABEL_18;
    }
    std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v53);
    v48 = 0;
    v49 = 0;
    PersistedDocument = ParseBulkInstanceData(v45, v53, &v48, &v49);
    if ( PersistedDocument < 0 )
    {
      v18 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v18,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"ParseBulkInstanceData",
        &word_180142E98,
        PersistedDocument);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v53);
      goto LABEL_21;
    }
    v44 = 0;
    v50 = &v44;
    v51 = 0;
    v52 = 1;
    do
      ++v10;
    while ( a3[v10] );
    EnrollmentIdSidStateDocIdKey = GetResultChecksum((unsigned __int8 *)a3, 2 * (int)v10, (unsigned __int16 **)&v51);
    wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&v50);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      v19 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v19,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"GetResultChecksum",
        &word_180142E98,
        EnrollmentIdSidStateDocIdKey);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v44);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v53);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      DCDocument::~DCDocument((DCDocument *)v73);
      DCDocument::~DCDocument((DCDocument *)v64);
      goto LABEL_9;
    }
    v20 = v54;
    for ( i = (_QWORD *)*v54; i != v20; i = (_QWORD *)*i )
    {
      std::wstring::wstring((__int64)v61, i + 2);
      std::wstring::wstring((__int64)v62, i + 6);
      if ( v61[2] )
      {
        v22 = v62;
        if ( v62[3] > 7u )
          v22 = (_QWORD *)v62[0];
        v23 = v61;
        if ( v61[3] > 7u )
          v23 = (_QWORD *)v61[0];
        EnrollmentIdSidStateDocIdVersionRawKey = DMOrchestratorSetInstanceVariable(*a1, a2, v44, v23, v22);
        if ( EnrollmentIdSidStateDocIdVersionRawKey < 0 )
        {
          v25 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v25,
            L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
            L"DMOrchestratorSetInstanceVariable",
            &word_180142E98,
            EnrollmentIdSidStateDocIdVersionRawKey);
          std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v61);
          goto LABEL_74;
        }
      }
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v61);
    }
    v26 = v48;
    if ( (unsigned int)_o__itow_s(v48, v74, 3) )
    {
      v27 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v27,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"_itow_s",
        L"Bad Conversion",
        -2147024809);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v44);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v53);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      DCDocument::~DCDocument((DCDocument *)v73);
      DCDocument::~DCDocument((DCDocument *)v64);
      operator delete(Block);
      EnrollmentIdSidStateDocIdVersionRawKey = -2147024809;
LABEL_75:
      Block = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
      return (unsigned int)EnrollmentIdSidStateDocIdVersionRawKey;
    }
    EnrollmentIdSidStateDocIdVersionRawKey = DMOrchestratorSetInstanceVariable(*a1, a2, v44, L"@#InstanceAmount#", v74);
    if ( EnrollmentIdSidStateDocIdVersionRawKey < 0
      || (EnrollmentIdSidStateDocIdVersionRawKey = DMOrchestratorSetInstanceVariable(
                                                     *a1,
                                                     a2,
                                                     Block,
                                                     L"@#InstanceAmount#",
                                                     v74),
          EnrollmentIdSidStateDocIdVersionRawKey < 0) )
    {
      v28 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v28,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DMOrchestratorSetInstanceVariable",
        &word_180142E98,
        EnrollmentIdSidStateDocIdVersionRawKey);
LABEL_74:
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v44);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v53);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      DCDocument::~DCDocument((DCDocument *)v73);
      DCDocument::~DCDocument((DCDocument *)v64);
      operator delete(Block);
      goto LABEL_75;
    }
    v50 = &v43;
    LOBYTE(v51) = 1;
    if ( DCCDNUtil_GetRegistryString(v46, 0, L"MostRecentVersion", &v43) >= 0
      && (EnrollmentIdSidStateDocIdVersionRawKey = DCCDNUtil_SetRegistryString(v46, 0, L"PreviousVersion", v43, 0),
          EnrollmentIdSidStateDocIdVersionRawKey < 0)
      || (EnrollmentIdSidStateDocIdVersionRawKey = DCCDNUtil_SetRegistryString(v46, 0, L"MostRecentVersion", v44, 0),
          EnrollmentIdSidStateDocIdVersionRawKey < 0) )
    {
      v29 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v29,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DCCDNUtil_SetRegistryString",
        &word_180142E98,
        EnrollmentIdSidStateDocIdVersionRawKey);
      goto LABEL_73;
    }
    v63 = 0;
    v30 = v69;
    if ( v70 > 7 )
      v30 = (unsigned __int16 **)v69[0];
    if ( (unsigned int)getStateMachineTypeFromDefinedScenario(v30) == 63 )
    {
      v31 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v31,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"getStateMachineTypeFromDefinedScenario",
        &word_180142E98,
        -2147024809);
LABEL_73:
      operator delete(v43);
      v43 = 0;
      goto LABEL_74;
    }
    v47 = 0;
    v56 = &v47;
    v57 = 0;
    v58 = 1;
    v32 = v64;
    if ( v65 > 7 )
      LODWORD(v32) = v64[0];
    EnrollmentIdSidStateDocIdVersionRawKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                               (_DWORD)a1,
                                               (_DWORD)v32,
                                               (_DWORD)v44,
                                               (unsigned int)&v57,
                                               1);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v56);
    if ( EnrollmentIdSidStateDocIdVersionRawKey < 0 )
    {
      v33 = CDeclaredConfigurationLogger::GetLogger();
      v34 = L"GetEnrollmentIdSidStateDocIdVersionRawKey";
LABEL_56:
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v33,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        v34,
        &word_180142E98,
        EnrollmentIdSidStateDocIdVersionRawKey);
LABEL_72:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
      goto LABEL_73;
    }
    v35 = (const unsigned __int16 *)v69;
    if ( v70 > 7 )
      v35 = v69[0];
    EnrollmentIdSidStateDocIdVersionRawKey = DCCDNUtil_SetRegistryString(v47, 0, L"osdefinedscenario", v35, 0);
    if ( EnrollmentIdSidStateDocIdVersionRawKey < 0
      || (EnrollmentIdSidStateDocIdVersionRawKey = DCCDNUtil_SetRegistryDWORD(v47, 0, L"downloadRequest", v71),
          EnrollmentIdSidStateDocIdVersionRawKey < 0)
      || (EnrollmentIdSidStateDocIdVersionRawKey = DCCDNUtil_SetRegistryDWORD(v47, 0, L"behavior", v72),
          EnrollmentIdSidStateDocIdVersionRawKey < 0) )
    {
      v33 = CDeclaredConfigurationLogger::GetLogger();
      v34 = L"DCCDNUtil_SetRegistryString";
      goto LABEL_56;
    }
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 2;
    v36 = (const unsigned __int16 *)v64;
    if ( v65 > 7 )
      v36 = v64[0];
    EnrollmentIdSidStateDocIdVersionRawKey = DeclaredConfigurationStore_WriteResultData(
                                               (struct DeclaredConfigurationScopeData *)a1,
                                               v36,
                                               v44,
                                               0,
                                               0,
                                               0,
                                               L"state",
                                               &pvarg);
    if ( EnrollmentIdSidStateDocIdVersionRawKey < 0 )
    {
      v37 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v37,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DeclaredConfigurationStore_WriteResultData",
        L"state",
        EnrollmentIdSidStateDocIdVersionRawKey);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49AC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)EnrollmentIdSidStateDocIdVersionRawKey,
        v41);
LABEL_71:
      VariantClear(&pvarg);
      goto LABEL_72;
    }
    v38 = v66;
    if ( v66[3] > 7u )
      v38 = (_QWORD *)v66[0];
    EnrollmentIdSidStateDocIdVersionRawKey = DMOrchestratorConfig(*a1, v38);
    if ( EnrollmentIdSidStateDocIdVersionRawKey < 0 )
    {
      v39 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v39,
        L"DeclaredConfigurationStore_ProcessTemplateBulkVariable",
        L"DMOrchestratorConfig",
        &word_180142E98,
        EnrollmentIdSidStateDocIdVersionRawKey);
      goto LABEL_71;
    }
    v40 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogDeclaredConfigurationEndBulkInstanceDataParsingFromCSPEvent(
      v40,
      a2,
      (const unsigned __int16 *)Block,
      *a1,
      a1[1],
      v26,
      v49);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
    operator delete(v43);
    v43 = 0;
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v44);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v53);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    DCDocument::~DCDocument((DCDocument *)v73);
    DCDocument::~DCDocument((DCDocument *)v64);
    operator delete(Block);
    Block = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
    return 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180080e90  mov     [rsp-8+arg_18], rbx
0x180080e95  push    rbp
0x180080e96  push    rsi
0x180080e97  push    rdi
0x180080e98  push    r12
0x180080e9a  push    r13
0x180080e9c  push    r14
0x180080e9e  push    r15
0x180080ea0  lea     rbp, [rsp-650h]
0x180080ea8  sub     rsp, 750h
0x180080eaf  mov     rax, cs:__security_cookie
0x180080eb6  xor     rax, rsp
0x180080eb9  mov     [rbp+680h+var_38], rax
0x180080ec0  mov     rsi, r8
0x180080ec3  mov     r15, rdx
0x180080ec6  mov     r14, rcx
0x180080ec9  xor     r12d, r12d
0x180080ecc  mov     [rsp+780h+Block], r12
0x180080ed1  mov     [rsp+780h+var_720], r12
0x180080ed6  mov     [rsp+780h+var_738], r12
0x180080edb  test    rcx, rcx
0x180080ede  jz      loc_1800817E9
0x180080ee4  test    rdx, rdx
0x180080ee7  jz      loc_1800817E9
0x180080eed  test    r8, r8
0x180080ef0  jz      loc_1800817E9
0x180080ef6  lea     rax, [rsp+780h+var_720]
0x180080efb  mov     [rsp+780h+var_708], rax
0x180080f00  mov     [rbp+680h+var_700], r12
0x180080f04  lea     r13d, [r12+1]
0x180080f09  mov     [rbp+680h+var_6F8], r13b
0x180080f0d  xor     r9d, r9d; int
0x180080f10  lea     r8, [rbp+680h+var_700]; HKEY *
0x180080f14  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180080f19  mov     ebx, eax
0x180080f1b  lea     rcx, [rsp+780h+var_708]
0x180080f20  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180080f25  test    ebx, ebx
0x180080f27  jns     short loc_180080F61
0x180080f29  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180080f2e  mov     dword ptr [rsp+780h+var_760], ebx; int
0x180080f32  lea     r9, word_180142E98; unsigned __int16 *
0x180080f39  lea     r8, aDeclaredconfig_208; "DeclaredConfigurationStore_GetEnrollmen"...
0x180080f40  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x180080f47  mov     rcx, rax; this
0x180080f4a  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180080f4f  nop
0x180080f50  lea     rcx, [rsp+780h+var_720]
0x180080f55  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180080f5a  mov     eax, ebx
0x180080f5c  jmp     loc_1800817F8
0x180080f61  lea     rax, [rsp+780h+Block]
0x180080f66  mov     [rbp+680h+var_680], rax
0x180080f6a  mov     [rbp+680h+var_678], r13b
0x180080f6e  lea     r9, [rsp+780h+Block]; unsigned __int16 **
0x180080f73  lea     r8, aBulktemplateve; "BulkTemplateVersion"
0x180080f7a  xor     edx, edx; unsigned __int16 *
0x180080f7c  mov     rcx, [rsp+780h+var_720]; HKEY
0x180080f81  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180080f86  mov     ebx, eax
0x180080f88  test    eax, eax
0x180080f8a  jns     short loc_180080FC4
0x180080f8c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180080f91  mov     dword ptr [rsp+780h+var_760], ebx; int
0x180080f95  lea     r9, aGetMostRecentV; "Get most recent version"
0x180080f9c  lea     r8, aDccdnutilGetre_9; "DCCDNUtil_GetRegistryString"
0x180080fa3  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x180080faa  mov     rcx, rax; this
0x180080fad  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180080fb2  nop
0x180080fb3  mov     rcx, [rsp+780h+Block]; Block
0x180080fb8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180080fbd  mov     [rsp+780h+Block], r12
0x180080fc2  jmp     short loc_180080F50
0x180080fc4  lea     rcx, [rbp+680h+var_620]; this
0x180080fc8  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x180080fcd  nop
0x180080fce  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180080fd2  mov     r8, rbx
0x180080fd5  inc     r8
0x180080fd8  cmp     [r15+r8*2], r12w
0x180080fdd  jnz     short loc_180080FD5
0x180080fdf  mov     rdx, r15
0x180080fe2  lea     rcx, [rbp+680h+var_620]
0x180080fe6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180080feb  mov     rdx, [r14+8]
0x180080fef  mov     r8, rbx
0x180080ff2  inc     r8
0x180080ff5  cmp     [rdx+r8*2], r12w
0x180080ffa  jnz     short loc_180080FF2
0x180080ffc  lea     rcx, [rbp+680h+var_5E0]
0x180081003  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180081008  mov     rdx, [rsp+780h+Block]
0x18008100d  mov     r8, rbx
0x180081010  inc     r8
0x180081013  cmp     [rdx+r8*2], r12w
0x180081018  jnz     short loc_180081010
0x18008101a  lea     rcx, [rbp+680h+var_5C0]
0x180081021  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180081026  lea     rcx, [rbp+680h+var_330]; this
0x18008102d  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x180081032  nop
0x180081033  mov     dword ptr [rsp+780h+var_758], r13d
0x180081038  lea     rax, [rbp+680h+var_620]
0x18008103c  mov     [rsp+780h+var_760], rax
0x180081041  xor     r9d, r9d
0x180081044  mov     r8, [rsp+780h+Block]
0x180081049  mov     rdx, [rsp+780h+var_720]
0x18008104e  mov     rcx, r14
0x180081051  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x180081056  mov     edi, eax
0x180081058  test    eax, eax
0x18008105a  jns     short loc_1800810BA
0x18008105c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180081061  mov     dword ptr [rsp+780h+var_760], edi; int
0x180081065  lea     r9, word_180142E98; unsigned __int16 *
0x18008106c  lea     r8, aDeclaredconfig_143; "DeclaredConfigurationStore_GetPersisted"...
0x180081073  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x18008107a  mov     rcx, rax; this
0x18008107d  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180081082  nop
0x180081083  lea     rcx, [rbp+680h+var_330]; this
0x18008108a  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18008108f  nop
0x180081090  lea     rcx, [rbp+680h+var_620]; this
0x180081094  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180081099  nop
0x18008109a  mov     rcx, [rsp+780h+Block]; Block
0x18008109f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800810a4  mov     [rsp+780h+Block], r12
0x1800810a9  lea     rcx, [rsp+780h+var_720]
0x1800810ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800810b3  mov     eax, edi
0x1800810b5  jmp     loc_1800817F8
0x1800810ba  mov     [rsp+780h+var_728], r12
0x1800810bf  lea     rdx, [rsp+780h+var_728]; struct IXmlReader **
0x1800810c4  mov     rcx, rsi; unsigned __int16 *
0x1800810c7  call    ?CreateXmlParser@@YAJPEBGPEAPEAUIXmlReader@@@Z; CreateXmlParser(ushort const *,IXmlReader * *)
0x1800810cc  mov     edi, eax
0x1800810ce  test    eax, eax
0x1800810d0  jns     short loc_180081108
0x1800810d2  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800810d7  mov     dword ptr [rsp+780h+var_760], edi; int
0x1800810db  lea     r9, word_180142E98; unsigned __int16 *
0x1800810e2  lea     r8, aCreatexmlparse; "CreateXmlParser"
0x1800810e9  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x1800810f0  mov     rcx, rax; this
0x1800810f3  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800810f8  nop
0x1800810f9  lea     rcx, [rsp+780h+var_728]
0x1800810fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081103  jmp     loc_180081083
0x180081108  lea     rcx, [rbp+680h+var_6F0]
0x18008110c  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x180081111  nop
0x180081112  mov     [rsp+780h+var_710], r12d
0x180081117  mov     [rsp+780h+var_70C], r12d
0x18008111c  lea     r9, [rsp+780h+var_70C]
0x180081121  lea     r8, [rsp+780h+var_710]
0x180081126  lea     rdx, [rbp+680h+var_6F0]
0x18008112a  mov     rcx, [rsp+780h+var_728]
0x18008112f  call    ?ParseBulkInstanceData@@YAJPEAUIXmlReader@@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEAK2@Z; ParseBulkInstanceData(IXmlReader *,std::unordered_map<std::wstring,std::wstring> *,ulong *,ulong *)
0x180081134  mov     edi, eax
0x180081136  test    eax, eax
0x180081138  jns     short loc_18008116C
0x18008113a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18008113f  mov     dword ptr [rsp+780h+var_760], edi; int
0x180081143  lea     r9, word_180142E98; unsigned __int16 *
0x18008114a  lea     r8, aParsebulkinsta; "ParseBulkInstanceData"
0x180081151  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x180081158  mov     rcx, rax; this
0x18008115b  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180081160  nop
0x180081161  lea     rcx, [rbp+680h+var_6F0]
0x180081165  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18008116a  jmp     short loc_1800810F9
0x18008116c  mov     [rsp+780h+var_730], r12
0x180081171  lea     rax, [rsp+780h+var_730]
0x180081176  mov     [rsp+780h+var_708], rax
0x18008117b  mov     [rbp+680h+var_700], r12
0x18008117f  mov     [rbp+680h+var_6F8], r13b
0x180081183  inc     rbx
0x180081186  cmp     [rsi+rbx*2], r12w
0x18008118b  jnz     short loc_180081183
0x18008118d  lea     edx, [rbx+rbx]; unsigned int
0x180081190  lea     r8, [rbp+680h+var_700]; unsigned __int16 **
0x180081194  mov     rcx, rsi; unsigned __int8 *
0x180081197  call    ?GetResultChecksum@@YAJPEAEKPEAPEAG@Z; GetResultChecksum(uchar *,ulong,ushort * *)
0x18008119c  mov     ebx, eax
0x18008119e  lea     rcx, [rsp+780h+var_708]
0x1800811a3  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<uchar [0]>>::~out_param_t<std::unique_ptr<uchar [0]>>(void)
0x1800811a8  test    ebx, ebx
0x1800811aa  jns     short loc_18008120E
0x1800811ac  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800811b1  mov     dword ptr [rsp+780h+var_760], ebx; int
0x1800811b5  lea     r9, word_180142E98; unsigned __int16 *
0x1800811bc  lea     r8, aGetresultcheck; "GetResultChecksum"
0x1800811c3  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x1800811ca  mov     rcx, rax; this
0x1800811cd  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800811d2  nop
0x1800811d3  lea     rcx, [rsp+780h+var_730]
0x1800811d8  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800811dd  nop
0x1800811de  lea     rcx, [rbp+680h+var_6F0]
0x1800811e2  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800811e7  nop
0x1800811e8  lea     rcx, [rsp+780h+var_728]
0x1800811ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800811f2  nop
0x1800811f3  lea     rcx, [rbp+680h+var_330]; this
0x1800811fa  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800811ff  nop
0x180081200  lea     rcx, [rbp+680h+var_620]; this
0x180081204  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180081209  jmp     loc_180080FB3
0x18008120e  mov     rdi, [rbp+680h+var_6E8]
0x180081212  mov     rbx, [rdi]
0x180081215  cmp     rbx, rdi
0x180081218  jz      loc_1800812BB
0x18008121e  lea     rdx, [rbx+10h]
0x180081222  lea     rcx, [rbp+680h+var_670]
0x180081226  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008122b  nop
0x18008122c  lea     rdx, [rbx+30h]
0x180081230  lea     rcx, [rbp+680h+var_650]
0x180081234  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180081239  nop
0x18008123a  cmp     [rbp+680h+var_660], r12
0x18008123e  jz      short loc_180081278
0x180081240  lea     rax, [rbp+680h+var_650]
0x180081244  cmp     [rbp+680h+var_638], 7
0x180081249  cmova   rax, [rbp+680h+var_650]
0x18008124e  lea     r9, [rbp+680h+var_670]
0x180081252  cmp     [rbp+680h+var_658], 7
0x180081257  cmova   r9, [rbp+680h+var_670]
0x18008125c  mov     [rsp+780h+var_760], rax
0x180081261  mov     r8, [rsp+780h+var_730]
0x180081266  mov     rdx, r15
0x180081269  mov     rcx, [r14]
0x18008126c  call    cs:__imp_DMOrchestratorSetInstanceVariable
0x180081272  mov     esi, eax
0x180081274  test    eax, eax
0x180081276  js      short loc_180081286
0x180081278  lea     rcx, [rbp+680h+var_670]
0x18008127c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x180081281  mov     rbx, [rbx]
0x180081284  jmp     short loc_180081215
0x180081286  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18008128b  mov     dword ptr [rsp+780h+var_760], esi; int
0x18008128f  lea     r9, word_180142E98; unsigned __int16 *
0x180081296  lea     r8, aDmorchestrator; "DMOrchestratorSetInstanceVariable"
0x18008129d  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x1800812a4  mov     rcx, rax; this
0x1800812a7  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800812ac  nop
0x1800812ad  lea     rcx, [rbp+680h+var_670]
0x1800812b1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800812b6  jmp     loc_1800816EB
0x1800812bb  mov     r9d, 0Ah
0x1800812c1  lea     r8d, [r9-7]
0x1800812c5  lea     rdx, [rbp+680h+var_40]
0x1800812cc  mov     edi, [rsp+780h+var_710]
0x1800812d0  mov     ecx, edi
0x1800812d2  call    cs:__imp__o__itow_s
0x1800812d8  test    eax, eax
0x1800812da  jz      short loc_180081352
0x1800812dc  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800812e1  mov     dword ptr [rsp+780h+var_760], 80070057h; int
0x1800812e9  lea     r9, aBadConversion_0; "Bad Conversion"
0x1800812f0  lea     r8, aItowS; "_itow_s"
0x1800812f7  lea     rdx, aDeclaredconfig_166; "DeclaredConfigurationStore_ProcessTempl"...
0x1800812fe  mov     rcx, rax; this
0x180081301  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180081306  nop
0x180081307  lea     rcx, [rsp+780h+var_730]
0x18008130c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180081311  nop
0x180081312  lea     rcx, [rbp+680h+var_6F0]
0x180081316  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18008131b  nop
0x18008131c  lea     rcx, [rsp+780h+var_728]
0x180081321  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081326  nop
0x180081327  lea     rcx, [rbp+680h+var_330]; this
0x18008132e  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180081333  nop
0x180081334  lea     rcx, [rbp+680h+var_620]; this
0x180081338  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18008133d  nop
0x18008133e  mov     rcx, [rsp+780h+Block]; Block
0x180081343  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180081348  mov     esi, 80070057h
0x18008134d  jmp     loc_18008172C
0x180081352  lea     rax, [rbp+680h+var_40]
0x180081359  mov     [rsp+780h+var_760], rax
0x18008135e  lea     r9, aInstanceamount; "@#InstanceAmount#"
0x180081365  mov     r8, [rsp+780h+var_730]
0x18008136a  mov     rdx, r15
0x18008136d  mov     rcx, [r14]
  ... truncated ...
```
