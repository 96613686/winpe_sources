# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal::InstallApps(std::vector<std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal::TileInstallItem>,std::allocator<std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal::TileInstallItem>>> const &,std::unordered_set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1801f9790`
- end: `0x1801f9f19`
- name: `?InstallApps@PlaceholderInstallerInternal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJAEBV?$vector@V?$shared_ptr@UTileInstallItem@PlaceholderInstallerInternal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@V?$allocator@V?$shared_ptr@UTileInstallItem@PlaceholderInstallerInternal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@2@@std@@AEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@7@@Z`
- size: `1929`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f93c0`

## callees

- `0x18001ac50`
- `0x18001aca4`
- `0x18002dde0`
- `0x18002f1fc`
- `0x18003153c`
- `0x18004ffc0`
- `0x18006fe30`
- `0x18007a0ac`
- `0x1800e5fe8`
- `0x1800f0854`
- `0x180161204`
- `0x18017dc34`
- `0x1801d04f4`
- `0x1801e0604`
- `0x1801f9790`
- `0x1801f9f20`
- `0x1801f9f44`
- `0x1801fac54`
- `0x1801fac74`
- `0x1801fac94`
- `0x180201e50`
- `0x18020e780`
- `0x18020ec5c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9c58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9d3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9ecf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9c58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9d3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9ecf`

## string_xrefs

- `0x1801f97fd`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f982d`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9b41`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9ba3`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9bfa`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9c7a`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9d1d`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9d87`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9dd6`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9e64`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`
- `0x1801f9ead`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholdertileinstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal::InstallApps(
        __int64 a1,
        const unsigned __int16 ***a2,
        __int64 a3)
{
  int v4; // r12d
  int v6; // eax
  __int64 v7; // rcx
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  const unsigned __int16 **v11; // r13
  const unsigned __int16 **v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rsi
  __int64 *v15; // r15
  __int64 v16; // rcx
  char *ProductId; // rax
  std::_Ref_count_base *v18; // r14
  int v19; // eax
  __int64 v20; // rbx
  UINT32 v21; // r8d
  __int64 v22; // rax
  int v23; // r15d
  __int64 (__fastcall *v24)(__int64, _QWORD); // r15
  const WCHAR *v25; // rdx
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64, _QWORD); // r15
  const WCHAR *v28; // rdx
  __int64 v29; // rax
  const unsigned __int16 *v30; // rcx
  unsigned __int64 v31; // rcx
  const unsigned __int16 *v32; // r9
  unsigned int v33; // r8d
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // r15
  __int64 (__fastcall *v39)(__int64, __int64, HSTRING, __int64); // r14
  HSTRING v40; // rbx
  int v41; // eax
  void *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r12
  const unsigned __int16 ***v45; // r15
  __int64 v46; // r14
  int v47; // eax
  int v48; // eax
  __int64 v49; // r14
  __int64 (__fastcall *v50)(__int64, __int64, HSTRING, __int64); // rdi
  HSTRING v51; // rbx
  int v52; // eax
  __int64 v53; // rax
  int v54; // eax
  int v55; // [rsp+20h] [rbp-E0h]
  unsigned int v56[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v57[2]; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v58; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v59; // [rsp+58h] [rbp-A8h] BYREF
  int v60; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 **v61; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h]
  int v64[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v68; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 ***v69; // [rsp+A8h] [rbp-58h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  char v71; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v72; // [rsp+C0h] [rbp-40h]
  __int64 *v73; // [rsp+C8h] [rbp-38h]
  std::_Ref_count_base *v74; // [rsp+D0h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-10h]
  HSTRING_HEADER v77; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v70 = a3;
  v69 = a2;
  v63 = a1;
  v4 = 0;
  v56[0] = 0;
  if ( a2[1] == *a2 )
    return 0;
  *(_QWORD *)v64 = 0;
  v6 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(
         a1,
         v64);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\plac"
                    "eholdertileinstaller.cpp",
      (const char *)(unsigned int)v6,
      v55);
    goto LABEL_93;
  }
  *(_QWORD *)v57 = 0;
  v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
         v7,
         v57);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = 338;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\plac"
                    "eholdertileinstaller.cpp",
      (const char *)(unsigned int)v9,
      v55);
    goto LABEL_8;
  }
  v11 = *a2;
  v12 = a2[1];
  v61 = v12;
  v13 = *(_QWORD *)v64;
  v14 = *(_QWORD *)v57;
  v15 = 0;
  while ( 1 )
  {
    if ( v11 == v12 )
    {
      v60 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 56LL))(v13, &v60);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = 373;
        goto LABEL_7;
      }
      v58 = 0;
      WindowsDeleteString(0);
      v58 = 0;
      v37 = Cortana::Common::CorrelationVectorHelper::CreateCorrelationVector(&v58);
      v8 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholdertileinstaller.cpp",
          (const char *)(unsigned int)v37,
          v55);
        WindowsDeleteString(v58);
        v58 = 0;
        goto LABEL_8;
      }
      if ( v60 )
      {
        v59 = 0;
        v38 = *(_QWORD *)(v63 + 48);
        v39 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v38 + 80LL);
        v59 = 0;
        v40 = v58;
        v76 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          (PCWSTR)"p\x00l\x00a\x00c\x00e\x00h\x00o\x00l\x00d\x00e\x00r\x00T\x00i\x00l\x00e\x00I\x00n\x00s\x00t\x00a\x00l\x00l\x00e\x00r\x00_\x00B\x00a\x00c\x00k\x00g\x00r\x00o\x00u\x00n\x00d",
          0x24u,
          0x23u);
        v55 = v13;
        v41 = v39(v38, v76, v40, 1);
        v8 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x185,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib"
                          "\\placeholdertileinstaller.cpp",
            (const char *)(unsigned int)v41,
            v13);
          v42 = &v59;
LABEL_78:
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v42);
LABEL_79:
          WindowsDeleteString(v58);
          v58 = 0;
          goto LABEL_8;
        }
        v43 = wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IInitialCollectionPostProcessor,wil::err_exception_policy>::com_ptr_t<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IInitialCollectionPostProcessor,wil::err_exception_policy>(
                &v61,
                &v59);
        v44 = v70;
        v45 = v69;
        v46 = v63;
        v47 = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal::CheckInstallationResults(
                v63,
                v69,
                v43,
                v70);
        if ( v47 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x187,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib"
                          "\\placeholdertileinstaller.cpp",
            (const char *)(unsigned int)v47,
            v13);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v59);
      }
      else
      {
        v45 = v69;
        v46 = v63;
        v44 = v70;
      }
      v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 56LL))(v14, &v60);
      v8 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18A,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholdertileinstaller.cpp",
          (const char *)(unsigned int)v48,
          v55);
        goto LABEL_79;
      }
      if ( v60 )
      {
        *(_QWORD *)v56 = 0;
        v49 = *(_QWORD *)(v46 + 48);
        v50 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v49 + 88LL);
        *(_QWORD *)v56 = 0;
        v51 = v58;
        v76 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          (PCWSTR)"p\x00l\x00a\x00c\x00e\x00h\x00o\x00l\x00d\x00e\x00r\x00T\x00i\x00l\x00e\x00I\x00n\x00s\x00t\x00a\x00l\x00l\x00e\x00r\x00_\x00B\x00a\x00c\x00k\x00g\x00r\x00o\x00u\x00n\x00d",
          0x24u,
          0x23u);
        v52 = v50(v49, v76, v51, 1);
        v8 = v52;
        if ( v52 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x196,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib"
                          "\\placeholdertileinstaller.cpp",
            (const char *)(unsigned int)v52,
            v14);
          v42 = v56;
          goto LABEL_78;
        }
        v53 = wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IInitialCollectionPostProcessor,wil::err_exception_policy>::com_ptr_t<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IInitialCollectionPostProcessor,wil::err_exception_policy>(
                &v61,
                v56);
        v54 = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal::CheckInstallationResults(
                v63,
                v45,
                v53,
                v44);
        if ( v54 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x198,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib"
                          "\\placeholdertileinstaller.cpp",
            (const char *)(unsigned int)v54,
            v14);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v56);
      }
      WindowsDeleteString(v58);
      v58 = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v57);
      v8 = 0;
      goto LABEL_93;
    }
    v16 = *((_QWORD *)*v11 + 16);
    if ( v16 )
    {
      ProductId = (char *)DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetProductId(v16, &hstringHeader);
      v4 |= 1u;
      v15 = *(__int64 **)ProductId;
    }
    else
    {
      v72 = 0;
      ProductId = &v71;
      v4 |= 2u;
    }
    v73 = v15;
    v18 = (std::_Ref_count_base *)*((_QWORD *)ProductId + 1);
    v74 = v18;
    *(_QWORD *)ProductId = 0;
    *((_QWORD *)ProductId + 1) = 0;
    if ( (v4 & 2) != 0 )
    {
      v4 &= ~2u;
      if ( v72 )
        std::_Ref_count_base::_Decref(v72);
    }
    if ( (v4 & 1) != 0 )
    {
      v4 &= ~1u;
      if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
    }
    if ( !v15 || !v15[2] )
    {
      v15 = 0;
      v59 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v59,
        0);
      v30 = *v11;
      if ( *((_QWORD *)*v11 + 3) > 7u )
        v30 = *(const unsigned __int16 **)v30;
      if ( (int)ParseAppUserModelId(v30, &v59, 0) >= 0 )
      {
        string = 0;
        if ( v59 )
        {
          v56[0] = 0;
          v31 = -1;
          do
            ++v31;
          while ( v59[v31] );
          v8 = ULongLongToUInt(v31, v56);
          if ( v8 >= 0 )
          {
            v33 = v56[0];
            v34 = v32;
            goto LABEL_46;
          }
LABEL_70:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16E,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib"
                          "\\placeholdertileinstaller.cpp",
            (const char *)(unsigned int)v8,
            v55);
          WindowsDeleteString(string);
          string = 0;
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v59);
LABEL_68:
          if ( v18 )
            std::_Ref_count_base::_Decref(v18);
LABEL_8:
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v57);
          goto LABEL_93;
        }
        v33 = 0;
        v34 = &String1;
LABEL_46:
        v8 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v34, v33);
        if ( v8 < 0 )
          goto LABEL_70;
        (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 104LL))(v14, string);
        WindowsDeleteString(string);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v59);
      goto LABEL_49;
    }
    DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetSkuId(*((_QWORD *)*v11 + 16), &v67);
    DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetStoreCampaignId(*((_QWORD *)*v11 + 16), &v65);
    *(_QWORD *)v56 = 0;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<ContentManagement::AppInstallInfoRecordImpl,ContentManagement::IAppInstallInfoRecord,>(v56);
    v8 = v19;
    if ( v19 < 0 )
    {
      v35 = 350;
LABEL_64:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\pl"
                      "aceholdertileinstaller.cpp",
        (const char *)(unsigned int)v19,
        v55);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v56);
      if ( v66 )
        std::_Ref_count_base::_Decref(v66);
      if ( v68 )
        std::_Ref_count_base::_Decref(v68);
      goto LABEL_68;
    }
    v20 = *(_QWORD *)v56;
    v59 = *(unsigned __int16 **)(**(_QWORD **)v56 + 56LL);
    v21 = *((_DWORD *)v15 + 4);
    if ( (unsigned __int64)v15[3] > 7 )
      v15 = (__int64 *)*v15;
    v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v77, (PCWSTR)v15, v21);
    v23 = ((__int64 (__fastcall *)(__int64, _QWORD))v59)(v20, *(_QWORD *)(v22 + 24));
    if ( v23 < 0 )
      break;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 72LL);
    v25 = (const WCHAR *)v67;
    if ( *(_QWORD *)(v67 + 24) > 7u )
      v25 = *(const WCHAR **)v67;
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v77, v25, *(_DWORD *)(v67 + 16));
    v23 = v24(v20, *(_QWORD *)(v26 + 24));
    if ( v23 < 0 )
    {
      v36 = 353;
      goto LABEL_56;
    }
    v27 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 88LL);
    v28 = (const WCHAR *)v65;
    if ( *(_QWORD *)(v65 + 24) > 7u )
      v28 = *(const WCHAR **)v65;
    v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v77, v28, *(_DWORD *)(v65 + 16));
    v23 = v27(v20, *(_QWORD *)(v29 + 24));
    if ( v23 < 0 )
    {
      v36 = 354;
      goto LABEL_56;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 104LL))(v13, v20);
    v8 = v19;
    v15 = 0;
    if ( v19 < 0 )
    {
      v35 = 356;
      goto LABEL_64;
    }
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v56);
    if ( v66 )
      std::_Ref_count_base::_Decref(v66);
    if ( v68 )
      std::_Ref_count_base::_Decref(v68);
LABEL_49:
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    v11 += 2;
    v12 = v61;
  }
  v36 = 352;
LABEL_56:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v36,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\placeh"
                  "oldertileinstaller.cpp",
    (const char *)(unsigned int)v23,
    v55);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v56);
  if ( v66 )
    std::_Ref_count_base::_Decref(v66);
  if ( v68 )
    std::_Ref_count_base::_Decref(v68);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v57);
  v8 = v23;
LABEL_93:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(v64);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801f9790  mov     [rsp-8+arg_18], rbx
0x1801f9795  push    rbp
0x1801f9796  push    rsi
0x1801f9797  push    rdi
0x1801f9798  push    r12
0x1801f979a  push    r13
0x1801f979c  push    r14
0x1801f979e  push    r15
0x1801f97a0  lea     rbp, [rsp-20h]
0x1801f97a5  sub     rsp, 120h
0x1801f97ac  mov     rax, cs:__security_cookie
0x1801f97b3  xor     rax, rsp
0x1801f97b6  mov     [rbp+50h+var_38], rax
0x1801f97ba  mov     [rbp+50h+var_A0], r8
0x1801f97be  mov     r15, rdx
0x1801f97c1  mov     [rbp+50h+var_A8], rdx
0x1801f97c5  mov     [rsp+150h+var_D8], rcx
0x1801f97ca  xor     edi, edi
0x1801f97cc  mov     r12d, edi
0x1801f97cf  mov     [rsp+150h+var_110], edi
0x1801f97d3  mov     rax, [rdx+8]
0x1801f97d7  cmp     rax, [rdx]
0x1801f97da  jnz     short loc_1801F97E3
0x1801f97dc  xor     eax, eax
0x1801f97de  jmp     loc_1801F9EF2
0x1801f97e3  mov     qword ptr [rbp+50h+var_D0], rdi
0x1801f97e7  lea     rdx, [rbp+50h+var_D0]
0x1801f97eb  call    ??$CreateExternalObjectVector@VAppInstallInfoRecord@ContentManagement@@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<ContentManagement::AppInstallInfoRecord,Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0> * *)
0x1801f97f0  mov     ebx, eax
0x1801f97f2  test    eax, eax
0x1801f97f4  jns     short loc_1801F9813
0x1801f97f6  mov     rcx, [rbp+58h]; this
0x1801f97fa  mov     r9d, eax; char *
0x1801f97fd  lea     r8, aShellcommonShe_62; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801f9804  mov     edx, 14Fh; void *
0x1801f9809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f980e  jmp     loc_1801F9EE7
0x1801f9813  mov     qword ptr [rsp+150h+var_108], rdi
0x1801f9818  lea     rdx, [rsp+150h+var_108]
0x1801f981d  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x1801f9822  mov     ebx, eax
0x1801f9824  test    eax, eax
0x1801f9826  jns     short loc_1801F9850
0x1801f9828  mov     edx, 152h; void *
0x1801f982d  lea     r8, aShellcommonShe_62; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801f9834  mov     r9d, eax; char *
0x1801f9837  mov     rcx, [rbp+58h]; this
0x1801f983b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f9840  nop
0x1801f9841  lea     rcx, [rsp+150h+var_108]; void *
0x1801f9846  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801f984b  jmp     loc_1801F9EE7
0x1801f9850  mov     r13, [r15]
0x1801f9853  mov     rax, [r15+8]
0x1801f9857  mov     [rsp+150h+var_E8], rax
0x1801f985c  mov     rdi, qword ptr [rbp+50h+var_D0]
0x1801f9860  mov     rsi, qword ptr [rsp+150h+var_108]
0x1801f9865  xor     r15d, r15d
0x1801f9868  cmp     r13, rax
0x1801f986b  jz      loc_1801F9C28
0x1801f9871  mov     rax, [r13+0]
0x1801f9875  mov     rcx, [rax+80h]
0x1801f987c  test    rcx, rcx
0x1801f987f  jz      short loc_1801F9893
0x1801f9881  lea     rdx, [rbp+50h+hstringHeader]
0x1801f9885  call    ?GetProductId@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetProductId(void)
0x1801f988a  or      r12d, 1
0x1801f988e  mov     r15, [rax]
0x1801f9891  jmp     short loc_1801F989F
0x1801f9893  mov     [rbp+50h+var_90], r15
0x1801f9897  lea     rax, [rbp+50h+var_98]
0x1801f989b  or      r12d, 2
0x1801f989f  mov     [rbp+50h+var_88], r15
0x1801f98a3  mov     r14, [rax+8]
0x1801f98a7  mov     [rbp+50h+var_80], r14
0x1801f98ab  xor     ebx, ebx
0x1801f98ad  mov     [rax], rbx
0x1801f98b0  mov     [rax+8], rbx
0x1801f98b4  test    r12b, 2
0x1801f98b8  jz      short loc_1801F98CC
0x1801f98ba  and     r12d, 0FFFFFFFDh
0x1801f98be  mov     rcx, [rbp+50h+var_90]; this
0x1801f98c2  test    rcx, rcx
0x1801f98c5  jz      short loc_1801F98CC
0x1801f98c7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f98cc  test    r12b, 1
0x1801f98d0  jz      short loc_1801F98E4
0x1801f98d2  and     r12d, 0FFFFFFFEh
0x1801f98d6  mov     rcx, qword ptr [rbp+50h+hstringHeader.Reserved+8]; this
0x1801f98da  test    rcx, rcx
0x1801f98dd  jz      short loc_1801F98E4
0x1801f98df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f98e4  test    r15, r15
0x1801f98e7  jz      loc_1801F9A4C
0x1801f98ed  cmp     [r15+10h], rbx
0x1801f98f1  jz      loc_1801F9A4C
0x1801f98f7  mov     rcx, [r13+0]
0x1801f98fb  lea     rdx, [rbp+50h+var_B8]
0x1801f98ff  mov     rcx, [rcx+80h]
0x1801f9906  call    ?GetSkuId@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetSkuId(void)
0x1801f990b  nop
0x1801f990c  mov     rcx, [r13+0]
0x1801f9910  lea     rdx, [rbp+50h+var_C8]
0x1801f9914  mov     rcx, [rcx+80h]
0x1801f991b  call    ?GetStoreCampaignId@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetStoreCampaignId(void)
0x1801f9920  nop
0x1801f9921  mov     qword ptr [rsp+150h+var_110], rbx
0x1801f9926  lea     rcx, [rsp+150h+var_110]
0x1801f992b  call    ??$MakeAndInitialize@VAppInstallInfoRecordImpl@ContentManagement@@UIAppInstallInfoRecord@2@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAppInstallInfoRecord@ContentManagement@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ContentManagement::AppInstallInfoRecordImpl,ContentManagement::IAppInstallInfoRecord,>(ContentManagement::IAppInstallInfoRecord * *)
0x1801f9930  mov     ebx, eax
0x1801f9932  test    eax, eax
0x1801f9934  js      loc_1801F9B9B
0x1801f993a  mov     rbx, qword ptr [rsp+150h+var_110]
0x1801f993f  mov     rax, [rbx]
0x1801f9942  mov     rax, [rax+38h]
0x1801f9946  mov     [rsp+150h+var_F8], rax
0x1801f994b  mov     r8d, [r15+10h]; length
0x1801f994f  cmp     qword ptr [r15+18h], 7
0x1801f9954  jbe     short loc_1801F9959
0x1801f9956  mov     r15, [r15]
0x1801f9959  mov     rdx, r15; sourceString
0x1801f995c  lea     rcx, [rbp+50h+var_58]; hstringHeader
0x1801f9960  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x1801f9965  nop
0x1801f9966  mov     rdx, [rax+18h]
0x1801f996a  mov     rcx, rbx
0x1801f996d  mov     rax, [rsp+150h+var_F8]
0x1801f9972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9977  mov     r15d, eax
0x1801f997a  test    eax, eax
0x1801f997c  js      loc_1801F9B39
0x1801f9982  mov     rax, [rbx]
0x1801f9985  mov     r15, [rax+48h]
0x1801f9989  mov     rdx, [rbp+50h+var_B8]
0x1801f998d  mov     r8d, [rdx+10h]; length
0x1801f9991  cmp     qword ptr [rdx+18h], 7
0x1801f9996  jbe     short loc_1801F999B
0x1801f9998  mov     rdx, [rdx]; sourceString
0x1801f999b  lea     rcx, [rbp+50h+var_58]; hstringHeader
0x1801f999f  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x1801f99a4  nop
0x1801f99a5  mov     rdx, [rax+18h]
0x1801f99a9  mov     rcx, rbx
0x1801f99ac  mov     rax, r15
0x1801f99af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f99b4  mov     r15d, eax
0x1801f99b7  test    eax, eax
0x1801f99b9  js      loc_1801F9B32
0x1801f99bf  mov     rax, [rbx]
0x1801f99c2  mov     r15, [rax+58h]
0x1801f99c6  mov     rdx, [rbp+50h+var_C8]
0x1801f99ca  mov     r8d, [rdx+10h]; length
0x1801f99ce  cmp     qword ptr [rdx+18h], 7
0x1801f99d3  jbe     short loc_1801F99D8
0x1801f99d5  mov     rdx, [rdx]; sourceString
0x1801f99d8  lea     rcx, [rbp+50h+var_58]; hstringHeader
0x1801f99dc  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x1801f99e1  nop
0x1801f99e2  mov     rdx, [rax+18h]
0x1801f99e6  mov     rcx, rbx
0x1801f99e9  mov     rax, r15
0x1801f99ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f99f1  mov     r15d, eax
0x1801f99f4  test    eax, eax
0x1801f99f6  js      loc_1801F9B2B
0x1801f99fc  mov     rax, [rdi]
0x1801f99ff  mov     rdx, rbx
0x1801f9a02  mov     rcx, rdi
0x1801f9a05  mov     rax, [rax+68h]
0x1801f9a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9a0e  mov     ebx, eax
0x1801f9a10  xor     r15d, r15d
0x1801f9a13  test    eax, eax
0x1801f9a15  js      loc_1801F9B24
0x1801f9a1b  lea     rcx, [rsp+150h+var_110]; void *
0x1801f9a20  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801f9a25  nop
0x1801f9a26  mov     rcx, [rbp+50h+var_C0]; this
0x1801f9a2a  test    rcx, rcx
0x1801f9a2d  jz      short loc_1801F9A35
0x1801f9a2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9a34  nop
0x1801f9a35  mov     rcx, [rbp+50h+var_B0]; this
0x1801f9a39  test    rcx, rcx
0x1801f9a3c  jz      loc_1801F9B09
0x1801f9a42  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9a47  jmp     loc_1801F9B09
0x1801f9a4c  xor     r15d, r15d
0x1801f9a4f  mov     [rsp+150h+var_F8], r15
0x1801f9a54  xor     edx, edx
0x1801f9a56  lea     rcx, [rsp+150h+var_F8]
0x1801f9a5b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801f9a60  mov     rcx, [r13+0]
0x1801f9a64  cmp     qword ptr [rcx+18h], 7
0x1801f9a69  jbe     short loc_1801F9A6E
0x1801f9a6b  mov     rcx, [rcx]; unsigned __int16 *
0x1801f9a6e  xor     r8d, r8d; unsigned __int16 **
0x1801f9a71  lea     rdx, [rsp+150h+var_F8]; unsigned __int16 **
0x1801f9a76  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x1801f9a7b  test    eax, eax
0x1801f9a7d  js      short loc_1801F9AFE
0x1801f9a7f  mov     [rsp+150h+string], r15
0x1801f9a84  mov     r9, [rsp+150h+var_F8]
0x1801f9a89  test    r9, r9
0x1801f9a8c  jz      short loc_1801F9ABF
0x1801f9a8e  mov     [rsp+150h+var_110], r15d
0x1801f9a93  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801f9a97  inc     rcx; unsigned __int64
0x1801f9a9a  cmp     [r9+rcx*2], r15w
0x1801f9a9f  jnz     short loc_1801F9A97
0x1801f9aa1  lea     rdx, [rsp+150h+var_110]; unsigned int *
0x1801f9aa6  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1801f9aab  mov     ebx, eax
0x1801f9aad  test    eax, eax
0x1801f9aaf  js      loc_1801F9BF3
0x1801f9ab5  mov     r8d, [rsp+150h+var_110]
0x1801f9aba  mov     rdx, r9
0x1801f9abd  jmp     short loc_1801F9AC9
0x1801f9abf  xor     r8d, r8d; unsigned int
0x1801f9ac2  lea     rdx, String1; unsigned __int16 *
0x1801f9ac9  lea     rcx, [rsp+150h+string]; this
0x1801f9ace  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801f9ad3  mov     ebx, eax
0x1801f9ad5  test    eax, eax
0x1801f9ad7  js      loc_1801F9BF3
0x1801f9add  mov     rax, [rsi]
0x1801f9ae0  mov     rdx, [rsp+150h+string]
0x1801f9ae5  mov     rcx, rsi
0x1801f9ae8  mov     rax, [rax+68h]
0x1801f9aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9af1  nop
0x1801f9af2  mov     rcx, [rsp+150h+string]; string
0x1801f9af7  call    cs:__imp_WindowsDeleteString
0x1801f9afd  nop
0x1801f9afe  lea     rcx, [rsp+150h+var_F8]
0x1801f9b03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801f9b08  nop
0x1801f9b09  test    r14, r14
0x1801f9b0c  jz      short loc_1801F9B16
0x1801f9b0e  mov     rcx, r14; this
0x1801f9b11  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9b16  add     r13, 10h
0x1801f9b1a  mov     rax, [rsp+150h+var_E8]
0x1801f9b1f  jmp     loc_1801F9868
0x1801f9b24  mov     edx, 164h
0x1801f9b29  jmp     short loc_1801F9BA0
0x1801f9b2b  mov     edx, 162h
0x1801f9b30  jmp     short loc_1801F9B3E
0x1801f9b32  mov     edx, 161h
0x1801f9b37  jmp     short loc_1801F9B3E
0x1801f9b39  mov     edx, 160h; void *
0x1801f9b3e  mov     r9d, r15d; char *
0x1801f9b41  lea     r8, aShellcommonShe_62; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801f9b48  mov     rcx, [rbp+58h]; this
0x1801f9b4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f9b51  nop
0x1801f9b52  lea     rcx, [rsp+150h+var_110]; void *
0x1801f9b57  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801f9b5c  nop
0x1801f9b5d  mov     rcx, [rbp+50h+var_C0]; this
0x1801f9b61  test    rcx, rcx
0x1801f9b64  jz      short loc_1801F9B6C
0x1801f9b66  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9b6b  nop
0x1801f9b6c  mov     rcx, [rbp+50h+var_B0]; this
0x1801f9b70  test    rcx, rcx
0x1801f9b73  jz      short loc_1801F9B7B
0x1801f9b75  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9b7a  nop
0x1801f9b7b  test    r14, r14
0x1801f9b7e  jz      short loc_1801F9B89
0x1801f9b80  mov     rcx, r14; this
0x1801f9b83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9b88  nop
0x1801f9b89  lea     rcx, [rsp+150h+var_108]; void *
0x1801f9b8e  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801f9b93  mov     ebx, r15d
0x1801f9b96  jmp     loc_1801F9EE7
0x1801f9b9b  mov     edx, 15Eh; void *
0x1801f9ba0  mov     r9d, eax; char *
0x1801f9ba3  lea     r8, aShellcommonShe_62; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801f9baa  mov     rcx, [rbp+58h]; this
0x1801f9bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f9bb3  nop
0x1801f9bb4  lea     rcx, [rsp+150h+var_110]; void *
0x1801f9bb9  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801f9bbe  nop
0x1801f9bbf  mov     rcx, [rbp+50h+var_C0]; this
0x1801f9bc3  test    rcx, rcx
0x1801f9bc6  jz      short loc_1801F9BCE
0x1801f9bc8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9bcd  nop
0x1801f9bce  mov     rcx, [rbp+50h+var_B0]; this
0x1801f9bd2  test    rcx, rcx
0x1801f9bd5  jz      short loc_1801F9BDD
0x1801f9bd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f9bdc  nop
0x1801f9bdd  test    r14, r14
0x1801f9be0  jz      loc_1801F9841
0x1801f9be6  mov     rcx, r14; this
  ... truncated ...
```
