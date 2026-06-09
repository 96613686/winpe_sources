# CStorageProviderRootsCache::SetStorageProviderInfo(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,_GUID,_GUID,_GUID,_GUID,_GUID,_GUID,_GUID,_GUID,ulong,_GUID,std::shared_ptr<WamAccountsCache>)

- ea: `0x180069ec4`
- end: `0x18006aa3c`
- name: `?SetStorageProviderInfo@CStorageProviderRootsCache@@QEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@0000000U_GUID@@1111111K1V?$shared_ptr@VWamAccountsCache@@@std@@@Z`
- size: `2936`
- prototype: `__int64 __usercall@<rax>(CStorageProviderRootsCache *this@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006aa8c`

## callees

- `0x180003210`
- `0x180004d6c`
- `0x1800077c8`
- `0x180007900`
- `0x18000a5b0`
- `0x18000b9b0`
- `0x180018074`
- `0x180019680`
- `0x18001d028`
- `0x18002037c`
- `0x1800207b4`
- `0x1800222ec`
- `0x18002edcc`
- `0x180035694`
- `0x180035730`
- `0x180035848`
- `0x180037780`
- `0x180043c98`
- `0x180069a70`
- `0x180069b28`
- `0x180069ec4`
- `0x18006c318`
- `0x1800790fc`

## import_xrefs

- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x18006a9d2`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x18006a9d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006a2e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006a38c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006a2e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006a38c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a00a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a0a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a26d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a30f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a3b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a00a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a0a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a26d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a30f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a3b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a40f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a563`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a563`

## string_xrefs

- `0x18006a4cb`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a4f8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a577`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a5d5`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a88c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a96c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a98e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a9eb`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006a687`: `UriHandler`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStorageProviderRootsCache::SetStorageProviderInfo(
        CStorageProviderRootsCache *this,
        HKEY *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        const WCHAR **a8,
        const WCHAR **a9,
        struct _GUID *a10,
        struct _GUID *a11,
        struct _GUID *a12,
        struct _GUID *a13,
        struct _GUID *a14,
        struct _GUID *a15,
        __int64 a16,
        __int64 a17,
        unsigned int a18,
        __int64 a19,
        __int64 a20)
{
  unsigned int v24; // r15d
  HKEY v25; // rax
  __int64 v26; // r12
  void *v27; // rcx
  LPVOID *v28; // r12
  void *v29; // rsi
  LPVOID *v30; // r14
  void *v31; // rsi
  LPVOID *v32; // r14
  _QWORD *v33; // r12
  void *v34; // rsi
  const WCHAR **v35; // r14
  const WCHAR *v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rax
  const WCHAR *v39; // rcx
  const WCHAR *v40; // rsi
  void *v41; // rcx
  const WCHAR **v42; // r14
  const WCHAR *v43; // r8
  __int64 v44; // rdx
  __int64 v45; // rax
  const WCHAR *v46; // rcx
  const WCHAR *v47; // rsi
  void *v48; // rcx
  LPVOID *v49; // r14
  _QWORD *v50; // r12
  void *v51; // rsi
  unsigned __int16 **v52; // rdx
  int HandlersFromStateRepoHelper; // eax
  unsigned __int64 v54; // r8
  int SyncEngineRegPath; // eax
  int v56; // esi
  std::_Ref_count_base *v57; // rcx
  unsigned int v59; // eax
  unsigned int v60; // ebx
  std::_Ref_count_base *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // rdx
  const unsigned __int16 *v65; // rdx
  const unsigned __int16 *v66; // r8
  unsigned int v67; // r13d
  const struct _GUID *v68; // rsi
  const struct _GUID *v69; // r14
  int v70; // r12d
  unsigned int v71; // r12d
  const struct _GUID **v72; // rsi
  const struct _GUID **v73; // r13
  __int64 v74; // rdx
  std::_Ref_count_base *v75; // rcx
  int v76; // r14d
  int v77; // eax
  __int64 v78; // rdx
  std::_Ref_count_base *v79; // rcx
  int updated; // eax
  std::_Ref_count_base *v81; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID *v85; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v86; // [rsp+60h] [rbp-A0h]
  struct _GUID *v87; // [rsp+68h] [rbp-98h]
  struct _GUID *v88; // [rsp+70h] [rbp-90h]
  struct _GUID *v89; // [rsp+78h] [rbp-88h]
  struct _GUID *v90; // [rsp+80h] [rbp-80h]
  _QWORD *v91; // [rsp+88h] [rbp-78h]
  const WCHAR **v92; // [rsp+90h] [rbp-70h]
  const WCHAR **v93; // [rsp+98h] [rbp-68h]
  _QWORD *v94; // [rsp+A0h] [rbp-60h]
  __int64 v95; // [rsp+A8h] [rbp-58h]
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v94 = a7;
  v93 = a9;
  v92 = a8;
  v91 = a6;
  v85 = a10;
  v86 = a11;
  v87 = a12;
  v88 = a13;
  v89 = a14;
  v90 = a15;
  v95 = a20;
  v24 = 1;
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       this,
                       *a2,
                       -1) != 2 )
  {
    v24 = 0;
    v25 = *a2;
    phkResult = *a2;
    *a2 = 0;
    a2[2] = 0;
    a2[1] = 0;
    if ( *(_QWORD *)this )
    {
      CoTaskMemFree(*(LPVOID *)this);
      v25 = phkResult;
    }
    *(_QWORD *)this = v25;
    *((_QWORD *)this + 2) = -1;
    *((_QWORD *)this + 1) = -1;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       (char *)this + 24,
                       *a3,
                       -1) != 2 )
  {
    v24 = 0;
    v26 = *a3;
    *a3 = 0;
    a3[2] = 0;
    a3[1] = 0;
    v27 = (void *)*((_QWORD *)this + 3);
    if ( v27 )
      CoTaskMemFree(v27);
    *((_QWORD *)this + 3) = v26;
    *((_QWORD *)this + 5) = -1;
    *((_QWORD *)this + 4) = -1;
  }
  v28 = (LPVOID *)((char *)this + 48);
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       (char *)this + 48,
                       *a4,
                       -1) != 2 )
  {
    v24 = 0;
    v29 = (void *)*a4;
    *a4 = 0;
    a4[2] = 0;
    a4[1] = 0;
    if ( *v28 )
      CoTaskMemFree(*v28);
    *v28 = v29;
    *((_QWORD *)this + 8) = -1;
    *((_QWORD *)this + 7) = -1;
  }
  v30 = (LPVOID *)((char *)this + 72);
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       (char *)this + 72,
                       *a5,
                       -1) != 2 )
  {
    v24 = 0;
    v31 = (void *)*a5;
    *a5 = 0;
    a5[2] = 0;
    a5[1] = 0;
    if ( *v30 )
      CoTaskMemFree(*v30);
    *v30 = v31;
    *((_QWORD *)this + 11) = -1;
    *((_QWORD *)this + 10) = -1;
  }
  if ( *((_QWORD *)this + 42) != *(_QWORD *)&v85->Data1 || *((_QWORD *)this + 43) != *(_QWORD *)v85->Data4 )
  {
    v24 = 0;
    *((struct _GUID *)this + 21) = *v85;
  }
  if ( *((_QWORD *)this + 44) != *(_QWORD *)&v86->Data1 || *((_QWORD *)this + 45) != *(_QWORD *)v86->Data4 )
  {
    v24 = 0;
    *((struct _GUID *)this + 22) = *v86;
  }
  if ( *((_QWORD *)this + 46) != *(_QWORD *)&v87->Data1 || *((_QWORD *)this + 47) != *(_QWORD *)v87->Data4 )
  {
    v24 = 0;
    *((struct _GUID *)this + 23) = *v87;
  }
  if ( *((_QWORD *)this + 48) != *(_QWORD *)&v88->Data1 || *((_QWORD *)this + 49) != *(_QWORD *)v88->Data4 )
  {
    v24 = 0;
    *((struct _GUID *)this + 24) = *v88;
  }
  if ( *((_QWORD *)this + 62) != *(_QWORD *)a16 || *((_QWORD *)this + 63) != *(_QWORD *)(a16 + 8) )
  {
    v24 = 0;
    *((_OWORD *)this + 31) = *(_OWORD *)a16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
    && (*((_QWORD *)this + 66) != *(_QWORD *)a17 || *((_QWORD *)this + 67) != *(_QWORD *)(a17 + 8)) )
  {
    v24 = 0;
    *((_OWORD *)this + 33) = *(_OWORD *)a17;
  }
  if ( *((_QWORD *)this + 50) != *(_QWORD *)&v89->Data1 || *((_QWORD *)this + 51) != *(_QWORD *)v89->Data4 )
  {
    v24 = 0;
    *((struct _GUID *)this + 25) = *v89;
  }
  if ( *((_QWORD *)this + 52) != *(_QWORD *)&v90->Data1 || *((_QWORD *)this + 53) != *(_QWORD *)v90->Data4 )
  {
    v24 = 0;
    *((struct _GUID *)this + 26) = *v90;
  }
  v32 = (LPVOID *)((char *)this + 96);
  v33 = v91;
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       (char *)this + 96,
                       *v91,
                       -1) != 2 )
  {
    v24 = 0;
    v34 = (void *)*v91;
    *v91 = 0;
    v33[2] = 0;
    v33[1] = 0;
    if ( *v32 )
      CoTaskMemFree(*v32);
    *v32 = v34;
    *((_QWORD *)this + 14) = -1;
    *((_QWORD *)this + 13) = -1;
  }
  v35 = v92;
  v36 = &String1;
  if ( *v92 )
    v36 = *v92;
  v37 = *((_QWORD *)this + 31);
  if ( v37 != -1 )
  {
    v39 = (const WCHAR *)*((_QWORD *)this + 30);
    if ( v39 )
      goto LABEL_56;
    goto LABEL_55;
  }
  v38 = *((_QWORD *)this + 30);
  if ( !v38 )
  {
    LODWORD(v37) = 0;
LABEL_55:
    v39 = &String1;
    goto LABEL_56;
  }
  v37 = -1;
  do
    ++v37;
  while ( *(_WORD *)(v38 + 2 * v37) );
  v39 = (const WCHAR *)*((_QWORD *)this + 30);
LABEL_56:
  if ( CompareStringOrdinal(v39, v37, v36, -(*v92 != 0), 0) != 2 )
  {
    v24 = 0;
    v40 = *v92;
    *v92 = 0;
    v35[2] = 0;
    v35[1] = 0;
    v41 = (void *)*((_QWORD *)this + 30);
    if ( v41 )
      CoTaskMemFree(v41);
    *((_QWORD *)this + 30) = v40;
    *((_QWORD *)this + 32) = -1;
    *((_QWORD *)this + 31) = -1;
  }
  v42 = v93;
  v43 = &String1;
  if ( *v93 )
    v43 = *v93;
  v44 = *((_QWORD *)this + 34);
  if ( v44 != -1 )
  {
    v46 = (const WCHAR *)*((_QWORD *)this + 33);
    if ( v46 )
      goto LABEL_70;
    goto LABEL_69;
  }
  v45 = *((_QWORD *)this + 33);
  if ( !v45 )
  {
    LODWORD(v44) = 0;
LABEL_69:
    v46 = &String1;
    goto LABEL_70;
  }
  v44 = -1;
  do
    ++v44;
  while ( *(_WORD *)(v45 + 2 * v44) );
  v46 = (const WCHAR *)*((_QWORD *)this + 33);
LABEL_70:
  if ( CompareStringOrdinal(v46, v44, v43, -(*v93 != 0), 0) != 2 )
  {
    v24 = 0;
    v47 = *v93;
    *v93 = 0;
    v42[2] = 0;
    v42[1] = 0;
    v48 = (void *)*((_QWORD *)this + 33);
    if ( v48 )
      CoTaskMemFree(v48);
    *((_QWORD *)this + 33) = v47;
    *((_QWORD *)this + 35) = -1;
    *((_QWORD *)this + 34) = -1;
  }
  v49 = (LPVOID *)((char *)this + 216);
  v50 = v94;
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       (char *)this + 216,
                       *v94,
                       -1) != 2 )
  {
    v24 = 0;
    v51 = (void *)*v94;
    *v94 = 0;
    v50[2] = 0;
    v50[1] = 0;
    if ( *v49 )
      CoTaskMemFree(*v49);
    *v49 = v51;
    *((_QWORD *)this + 29) = -1;
    *((_QWORD *)this + 28) = -1;
    if ( !*((_QWORD *)this + 83) )
      std::shared_ptr<WamAccountsCache>::operator=((char *)this + 664, a20);
    CStorageProviderRootsCache::CalculateUserIdentity(this);
  }
  if ( *((_DWORD *)this + 136) != a18 )
  {
    v24 = 0;
    *((_DWORD *)this + 136) = a18;
  }
  if ( *((_QWORD *)this + 54) != *(_QWORD *)a19 || *((_QWORD *)this + 55) != *(_QWORD *)(a19 + 8) )
  {
    v24 = 0;
    *((_OWORD *)this + 27) = *(_OWORD *)a19;
  }
  if ( v24 )
    goto LABEL_155;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 120);
  *((_QWORD *)this + 16) = -1;
  *((_QWORD *)this + 17) = -1;
  CallerIdentity::GetCallingProcessAppId((CStorageProviderRootsCache *)((char *)this + 120), v52);
  HandlersFromStateRepoHelper = CStorageProviderRootsCache::GetHandlersFromStateRepoHelper(this);
  if ( HandlersFromStateRepoHelper < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC51,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)HandlersFromStateRepoHelper,
      bIgnoreCase);
  SyncEngineRegPath = CStorageProviderRootsCache::_GetSyncEngineRegPath(this, SubKey, v54);
  v56 = SyncEngineRegPath;
  if ( SyncEngineRegPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC59,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)SyncEngineRegPath,
      bIgnoreCase);
LABEL_90:
    v57 = *(std::_Ref_count_base **)(a20 + 8);
    if ( v57 )
      std::_Ref_count_base::_Decref(v57);
    return (unsigned int)v56;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v59 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
  if ( !v59 )
  {
    v56 = SetHandler(phkResult, L"Handler", v85);
    if ( v56 < 0 )
    {
      v62 = 3166;
LABEL_100:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v62,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v56,
        bIgnoreCasea);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      goto LABEL_90;
    }
    v56 = SetHandler(phkResult, L"BannerNotificationHandler", v86);
    if ( v56 < 0 )
    {
      v62 = 3167;
      goto LABEL_100;
    }
    v56 = SetHandler(phkResult, L"CustomStateHandler", v87);
    if ( v56 < 0 )
    {
      v62 = 3168;
      goto LABEL_100;
    }
    v56 = SetHandler(phkResult, L"ThumbnailProvider", v88);
    if ( v56 < 0 )
    {
      v62 = 3169;
      goto LABEL_100;
    }
    v56 = SetHandler(phkResult, L"ExtendedPropertiesHandler", v89);
    if ( v56 < 0 )
    {
      v62 = 3170;
      goto LABEL_100;
    }
    v56 = SetHandler(phkResult, L"UriHandler", v90);
    if ( v56 < 0 )
    {
      v62 = 3171;
      goto LABEL_100;
    }
    v56 = SHRegSetExpandStringW(phkResult, v63, L"DisplayNameResource", *((_QWORD *)this + 3));
    if ( v56 < 0 )
    {
      v62 = 3173;
      goto LABEL_100;
    }
    v56 = SHRegSetExpandStringW(phkResult, v64, L"IconResource", *((_QWORD *)this + 6));
    if ( v56 < 0 )
    {
      v62 = 3174;
      goto LABEL_100;
    }
    v56 = SHRegSetDWORD(phkResult, v65, v66, a18);
    v67 = 0;
    if ( v56 < 0 )
    {
      v62 = 3175;
      goto LABEL_100;
    }
    v56 = SetOptionalValue(phkResult, L"ProtectionMode", *((_QWORD *)this + 9));
    if ( v56 < 0 )
    {
      v62 = 3177;
      goto LABEL_100;
    }
    v56 = SetOptionalValue(phkResult, L"RecycleBinUrl", *((_QWORD *)this + 12));
    if ( v56 < 0 )
    {
      v62 = 3178;
      goto LABEL_100;
    }
    v56 = SetOptionalValue(phkResult, L"AUMID", *((_QWORD *)this + 15));
    if ( v56 < 0 )
    {
      v62 = 3179;
      goto LABEL_100;
    }
    v56 = SetOptionalValue(phkResult, L"Cid", *v49);
    if ( v56 < 0 )
    {
      v62 = 3180;
      goto LABEL_100;
    }
    v56 = SetOptionalValue(phkResult, L"TenantName", *((_QWORD *)this + 30));
    if ( v56 < 0 )
    {
      v62 = 3181;
      goto LABEL_100;
    }
    v56 = SetOptionalValue(phkResult, L"UserFirstName", *((_QWORD *)this + 33));
    if ( v56 < 0 )
    {
      v62 = 3182;
      goto LABEL_100;
    }
    v68 = (const struct _GUID *)*((_QWORD *)this + 78);
    v69 = &v68[*((_QWORD *)this + 79)];
    while ( v68 != v69 )
    {
      v85 = 0;
      v70 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v85,
              L"%s_%d",
              L"IconOverlayHandler",
              v67);
      if ( v70 < 0 )
      {
        v74 = 3188;
        goto LABEL_137;
      }
      v70 = SetHandler(phkResult, (const unsigned __int16 *)v85, v68);
      if ( v70 < 0 )
      {
        v74 = 3189;
LABEL_137:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v74,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v70,
          bIgnoreCasea);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v85);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v75 = *(std::_Ref_count_base **)(a20 + 8);
        if ( v75 )
          std::_Ref_count_base::_Decref(v75);
        return (unsigned int)v70;
      }
      ++v67;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v85);
      ++v68;
    }
    v71 = 0;
    v72 = (const struct _GUID **)*((_QWORD *)this + 74);
    v73 = &v72[*((_QWORD *)this + 75)];
    while ( v72 != v73 )
    {
      v85 = 0;
      v76 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v85,
              L"%s_%d",
              L"MenuVerbHandler",
              v71);
      if ( v76 < 0 )
      {
        v78 = 3197;
        goto LABEL_149;
      }
      v76 = SetHandler(phkResult, (const unsigned __int16 *)v85, *v72 + 1);
      if ( v76 < 0 )
      {
        v78 = 3198;
LABEL_149:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v78,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v76,
          bIgnoreCasea);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v85);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v79 = *(std::_Ref_count_base **)(a20 + 8);
        if ( v79 )
          std::_Ref_count_base::_Decref(v79);
        return (unsigned int)v76;
      }
      ++v71;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v85);
      ++v72;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
    {
      v77 = SetHandler(phkResult, L"SearchHandlerFactory", (const struct _GUID *)this + 33);
      v60 = v77;
      if ( v77 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC84,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v77,
          bIgnoreCasea);
        goto LABEL_95;
      }
    }
    SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
    updated = SetSyncRootManagerRegistryUpdateEvent();
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC8B,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)updated,
        bIgnoreCasea);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_155:
    v81 = *(std::_Ref_count_base **)(a20 + 8);
    if ( v81 )
      std::_Ref_count_base::_Decref(v81);
    return v24;
  }
  v60 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xC5C,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)v59,
          bIgnoreCasea);
LABEL_95:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  v61 = *(std::_Ref_count_base **)(a20 + 8);
  if ( v61 )
    std::_Ref_count_base::_Decref(v61);
  return v60;
}

```

## disassembly

```asm
0x180069ec4  push    rbp
0x180069ec6  push    rbx
0x180069ec7  push    rsi
0x180069ec8  push    rdi
0x180069ec9  push    r12
0x180069ecb  push    r13
0x180069ecd  push    r14
0x180069ecf  push    r15
0x180069ed1  lea     rbp, [rsp-1D8h]
0x180069ed9  sub     rsp, 2D8h
0x180069ee0  mov     rax, cs:__security_cookie
0x180069ee7  xor     rax, rsp
0x180069eea  mov     [rbp+210h+var_50], rax
0x180069ef1  mov     r14, r9
0x180069ef4  mov     rsi, r8
0x180069ef7  mov     r12, rdx
0x180069efa  mov     rbx, rcx
0x180069efd  mov     rax, [rbp+210h+arg_30]
0x180069f04  mov     [rbp+210h+var_270], rax
0x180069f08  mov     rax, [rbp+210h+arg_40]
0x180069f0f  mov     [rbp+210h+var_278], rax
0x180069f13  mov     rax, [rbp+210h+arg_38]
0x180069f1a  mov     [rbp+210h+var_280], rax
0x180069f1e  mov     rax, [rbp+210h+arg_28]
0x180069f25  mov     [rbp+210h+var_288], rax
0x180069f29  mov     r13, [rbp+210h+arg_20]
0x180069f30  mov     r8, [rbp+210h+arg_48]
0x180069f37  mov     [rsp+310h+var_2B8], r8
0x180069f3c  mov     r8, [rbp+210h+arg_50]
0x180069f43  mov     [rsp+310h+var_2B0], r8
0x180069f48  mov     r8, [rbp+210h+arg_58]
0x180069f4f  mov     [rsp+310h+var_2A8], r8
0x180069f54  mov     r8, [rbp+210h+arg_60]
0x180069f5b  mov     [rsp+310h+var_2A0], r8
0x180069f60  mov     r8, [rbp+210h+arg_68]
0x180069f67  mov     [rsp+310h+var_298], r8
0x180069f6c  mov     r8, [rbp+210h+arg_70]
0x180069f73  mov     [rbp+210h+var_290], r8
0x180069f77  mov     rdi, [rbp+210h+arg_98]
0x180069f7e  mov     [rbp+210h+var_268], rdi
0x180069f82  mov     r15d, 1
0x180069f88  or      r8, 0FFFFFFFFFFFFFFFFh
0x180069f8c  mov     rdx, [rdx]
0x180069f8f  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180069f94  xor     edx, edx
0x180069f96  cmp     eax, 2
0x180069f99  jz      short loc_180069FD9
0x180069f9b  mov     r15d, edx
0x180069f9e  mov     rax, [r12]
0x180069fa2  mov     [rsp+310h+var_2C0], rax
0x180069fa7  mov     [r12], rdx
0x180069fab  mov     [r12+10h], rdx
0x180069fb0  mov     [r12+8], rdx
0x180069fb5  mov     rcx, [rbx]; pv
0x180069fb8  test    rcx, rcx
0x180069fbb  jz      short loc_180069FC8
0x180069fbd  call    cs:__imp_CoTaskMemFree
0x180069fc3  mov     rax, [rsp+310h+var_2C0]
0x180069fc8  mov     [rbx], rax
0x180069fcb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180069fcf  mov     [rbx+10h], r8
0x180069fd3  mov     [rbx+8], r8
0x180069fd7  jmp     short loc_180069FDD
0x180069fd9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180069fdd  lea     rcx, [rbx+18h]
0x180069fe1  mov     rdx, [rsi]
0x180069fe4  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180069fe9  cmp     eax, 2
0x180069fec  jz      short loc_18006A020
0x180069fee  xor     eax, eax
0x180069ff0  mov     r15d, eax
0x180069ff3  mov     r12, [rsi]
0x180069ff6  mov     [rsi], rax
0x180069ff9  mov     [rsi+10h], rax
0x180069ffd  mov     [rsi+8], rax
0x18006a001  mov     rcx, [rbx+18h]; pv
0x18006a005  test    rcx, rcx
0x18006a008  jz      short loc_18006A010
0x18006a00a  call    cs:__imp_CoTaskMemFree
0x18006a010  mov     [rbx+18h], r12
0x18006a014  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006a018  mov     [rbx+28h], rax
0x18006a01c  mov     [rbx+20h], rax
0x18006a020  lea     r12, [rbx+30h]
0x18006a024  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a028  mov     r8, rsi
0x18006a02b  mov     rdx, [r14]
0x18006a02e  mov     rcx, r12
0x18006a031  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x18006a036  cmp     eax, 2
0x18006a039  jz      short loc_18006A06F
0x18006a03b  xor     eax, eax
0x18006a03d  mov     r15d, eax
0x18006a040  mov     rsi, [r14]
0x18006a043  mov     [r14], rax
0x18006a046  mov     [r14+10h], rax
0x18006a04a  mov     [r14+8], rax
0x18006a04e  mov     rcx, [r12]; pv
0x18006a052  test    rcx, rcx
0x18006a055  jz      short loc_18006A05D
0x18006a057  call    cs:__imp_CoTaskMemFree
0x18006a05d  mov     [r12], rsi
0x18006a061  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a065  mov     [r12+10h], rsi
0x18006a06a  mov     [r12+8], rsi
0x18006a06f  lea     r14, [rbx+48h]
0x18006a073  mov     r8, rsi
0x18006a076  mov     rdx, [r13+0]
0x18006a07a  mov     rcx, r14
0x18006a07d  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x18006a082  cmp     eax, 2
0x18006a085  jz      short loc_18006A0BE
0x18006a087  xor     eax, eax
0x18006a089  mov     r15d, eax
0x18006a08c  mov     rsi, [r13+0]
0x18006a090  mov     [r13+0], rax
0x18006a094  mov     [r13+10h], rax
0x18006a098  mov     [r13+8], rax
0x18006a09c  mov     rcx, [r14]; pv
0x18006a09f  xor     r13d, r13d
0x18006a0a2  test    rcx, rcx
0x18006a0a5  jz      short loc_18006A0AD
0x18006a0a7  call    cs:__imp_CoTaskMemFree
0x18006a0ad  mov     [r14], rsi
0x18006a0b0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a0b4  mov     [r14+10h], rsi
0x18006a0b8  mov     [r14+8], rsi
0x18006a0bc  jmp     short loc_18006A0C1
0x18006a0be  xor     r13d, r13d
0x18006a0c1  mov     rax, [rbx+150h]
0x18006a0c8  mov     rcx, [rsp+310h+var_2B8]
0x18006a0cd  cmp     rax, [rcx]
0x18006a0d0  jnz     short loc_18006A0DF
0x18006a0d2  mov     rax, [rbx+158h]
0x18006a0d9  cmp     rax, [rcx+8]
0x18006a0dd  jz      short loc_18006A0ED
0x18006a0df  mov     r15d, r13d
0x18006a0e2  movaps  xmm0, xmmword ptr [rcx]
0x18006a0e5  movdqu  xmmword ptr [rbx+150h], xmm0
0x18006a0ed  mov     rax, [rbx+160h]
0x18006a0f4  mov     rcx, [rsp+310h+var_2B0]
0x18006a0f9  cmp     rax, [rcx]
0x18006a0fc  jnz     short loc_18006A10B
0x18006a0fe  mov     rax, [rbx+168h]
0x18006a105  cmp     rax, [rcx+8]
0x18006a109  jz      short loc_18006A119
0x18006a10b  mov     r15d, r13d
0x18006a10e  movaps  xmm0, xmmword ptr [rcx]
0x18006a111  movdqu  xmmword ptr [rbx+160h], xmm0
0x18006a119  mov     rax, [rbx+170h]
0x18006a120  mov     rcx, [rsp+310h+var_2A8]
0x18006a125  cmp     rax, [rcx]
0x18006a128  jnz     short loc_18006A137
0x18006a12a  mov     rax, [rbx+178h]
0x18006a131  cmp     rax, [rcx+8]
0x18006a135  jz      short loc_18006A145
0x18006a137  mov     r15d, r13d
0x18006a13a  movaps  xmm0, xmmword ptr [rcx]
0x18006a13d  movdqu  xmmword ptr [rbx+170h], xmm0
0x18006a145  mov     rax, [rbx+180h]
0x18006a14c  mov     rcx, [rsp+310h+var_2A0]
0x18006a151  cmp     rax, [rcx]
0x18006a154  jnz     short loc_18006A163
0x18006a156  mov     rax, [rbx+188h]
0x18006a15d  cmp     rax, [rcx+8]
0x18006a161  jz      short loc_18006A171
0x18006a163  mov     r15d, r13d
0x18006a166  movaps  xmm0, xmmword ptr [rcx]
0x18006a169  movdqu  xmmword ptr [rbx+180h], xmm0
0x18006a171  mov     rcx, [rbp+210h+arg_78]
0x18006a178  mov     rax, [rbx+1F0h]
0x18006a17f  cmp     rax, [rcx]
0x18006a182  jnz     short loc_18006A191
0x18006a184  mov     rax, [rbx+1F8h]
0x18006a18b  cmp     rax, [rcx+8]
0x18006a18f  jz      short loc_18006A19F
0x18006a191  mov     r15d, r13d
0x18006a194  movaps  xmm0, xmmword ptr [rcx]
0x18006a197  movdqu  xmmword ptr [rbx+1F0h], xmm0
0x18006a19f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x18006a1a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x18006a1ab  test    al, al
0x18006a1ad  jz      short loc_18006A1DD
0x18006a1af  mov     rcx, [rbp+210h+arg_80]
0x18006a1b6  mov     rax, [rbx+210h]
0x18006a1bd  cmp     rax, [rcx]
0x18006a1c0  jnz     short loc_18006A1CF
0x18006a1c2  mov     rax, [rbx+218h]
0x18006a1c9  cmp     rax, [rcx+8]
0x18006a1cd  jz      short loc_18006A1DD
0x18006a1cf  mov     r15d, r13d
0x18006a1d2  movaps  xmm0, xmmword ptr [rcx]
0x18006a1d5  movdqu  xmmword ptr [rbx+210h], xmm0
0x18006a1dd  mov     rax, [rbx+190h]
0x18006a1e4  mov     rcx, [rsp+310h+var_298]
0x18006a1e9  cmp     rax, [rcx]
0x18006a1ec  jnz     short loc_18006A1FB
0x18006a1ee  mov     rax, [rbx+198h]
0x18006a1f5  cmp     rax, [rcx+8]
0x18006a1f9  jz      short loc_18006A209
0x18006a1fb  mov     r15d, r13d
0x18006a1fe  movaps  xmm0, xmmword ptr [rcx]
0x18006a201  movdqu  xmmword ptr [rbx+190h], xmm0
0x18006a209  mov     rax, [rbx+1A0h]
0x18006a210  mov     rcx, [rbp+210h+var_290]
0x18006a214  cmp     rax, [rcx]
0x18006a217  jnz     short loc_18006A226
0x18006a219  mov     rax, [rbx+1A8h]
0x18006a220  cmp     rax, [rcx+8]
0x18006a224  jz      short loc_18006A234
0x18006a226  mov     r15d, r13d
0x18006a229  movaps  xmm0, xmmword ptr [rcx]
0x18006a22c  movdqu  xmmword ptr [rbx+1A0h], xmm0
0x18006a234  lea     r14, [rbx+60h]
0x18006a238  mov     r8, rsi
0x18006a23b  mov     r12, [rbp+210h+var_288]
0x18006a23f  mov     rdx, [r12]
0x18006a243  mov     rcx, r14
0x18006a246  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x18006a24b  cmp     eax, 2
0x18006a24e  jz      short loc_18006A282
0x18006a250  mov     r15d, r13d
0x18006a253  mov     rsi, [r12]
0x18006a257  mov     [r12], r13
0x18006a25b  mov     [r12+10h], r13
0x18006a260  mov     [r12+8], r13
0x18006a265  mov     rcx, [r14]; pv
0x18006a268  test    rcx, rcx
0x18006a26b  jz      short loc_18006A273
0x18006a26d  call    cs:__imp_CoTaskMemFree
0x18006a273  mov     [r14], rsi
0x18006a276  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a27a  mov     [r14+10h], rsi
0x18006a27e  mov     [r14+8], rsi
0x18006a282  mov     r14, [rbp+210h+var_280]
0x18006a286  mov     rax, [r14]
0x18006a289  neg     rax
0x18006a28c  sbb     r9d, r9d; cchCount2
0x18006a28f  lea     r12, String1
0x18006a296  mov     r8, r12
0x18006a299  cmp     [r14], r13
0x18006a29c  cmovnz  r8, [r14]; lpString2
0x18006a2a0  mov     rdx, [rbx+0F8h]; cchCount1
0x18006a2a7  cmp     rdx, rsi
0x18006a2aa  jnz     short loc_18006A2D3
0x18006a2ac  mov     rax, [rbx+0F0h]
0x18006a2b3  test    rax, rax
0x18006a2b6  jz      short loc_18006A2CE
0x18006a2b8  mov     rdx, rsi
0x18006a2bb  inc     rdx
0x18006a2be  cmp     [rax+rdx*2], r13w
0x18006a2c3  jnz     short loc_18006A2BB
0x18006a2c5  mov     rcx, [rbx+0F0h]
0x18006a2cc  jmp     short loc_18006A2E2
0x18006a2ce  mov     rdx, r13
0x18006a2d1  jmp     short loc_18006A2DF
0x18006a2d3  mov     rcx, [rbx+0F0h]
0x18006a2da  test    rcx, rcx
0x18006a2dd  jnz     short loc_18006A2E2
0x18006a2df  mov     rcx, r12; lpString1
0x18006a2e2  mov     [rsp+310h+bIgnoreCase], r13d; bIgnoreCase
0x18006a2e7  call    cs:__imp_CompareStringOrdinal
0x18006a2ed  cmp     eax, 2
0x18006a2f0  jz      short loc_18006A32E
0x18006a2f2  mov     r15d, r13d
0x18006a2f5  mov     rsi, [r14]
0x18006a2f8  mov     [r14], r13
0x18006a2fb  mov     [r14+10h], r13
0x18006a2ff  mov     [r14+8], r13
0x18006a303  mov     rcx, [rbx+0F0h]; pv
0x18006a30a  test    rcx, rcx
0x18006a30d  jz      short loc_18006A315
0x18006a30f  call    cs:__imp_CoTaskMemFree
0x18006a315  mov     [rbx+0F0h], rsi
0x18006a31c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a320  mov     [rbx+100h], rsi
0x18006a327  mov     [rbx+0F8h], rsi
0x18006a32e  mov     r14, [rbp+210h+var_278]
0x18006a332  mov     rax, [r14]
0x18006a335  neg     rax
0x18006a338  sbb     r9d, r9d; cchCount2
0x18006a33b  mov     r8, r12
0x18006a33e  cmp     [r14], r13
0x18006a341  cmovnz  r8, [r14]; lpString2
0x18006a345  mov     rdx, [rbx+110h]; cchCount1
0x18006a34c  cmp     rdx, rsi
0x18006a34f  jnz     short loc_18006A378
0x18006a351  mov     rax, [rbx+108h]
0x18006a358  test    rax, rax
0x18006a35b  jz      short loc_18006A373
0x18006a35d  mov     rdx, rsi
0x18006a360  inc     rdx
0x18006a363  cmp     [rax+rdx*2], r13w
0x18006a368  jnz     short loc_18006A360
0x18006a36a  mov     rcx, [rbx+108h]
0x18006a371  jmp     short loc_18006A387
0x18006a373  mov     rdx, r13
0x18006a376  jmp     short loc_18006A384
0x18006a378  mov     rcx, [rbx+108h]
0x18006a37f  test    rcx, rcx
  ... truncated ...
```
