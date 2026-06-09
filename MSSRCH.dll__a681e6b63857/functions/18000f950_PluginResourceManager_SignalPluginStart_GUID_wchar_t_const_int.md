# PluginResourceManager::SignalPluginStart(_GUID,wchar_t const *,int)

- ea: `0x18000f950`
- end: `0x180010343`
- name: `?SignalPluginStart@PluginResourceManager@@UEAAJU_GUID@@PEB_WH@Z`
- size: `2547`
- prototype: `__int64 __fastcall(PluginResourceManager *__hidden this, IID *rclsid, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ef00`
- `0x18000efcc`
- `0x18000eff8`
- `0x18000f42c`
- `0x18000f880`
- `0x18000f950`
- `0x180010994`
- `0x1800110b8`
- `0x180012120`
- `0x180012190`
- `0x18002bf00`
- `0x18006d080`
- `0x18006ed00`
- `0x1800771ac`
- `0x18009b43c`
- `0x1800adcf4`
- `0x1800fc1f8`
- `0x1801244c0`
- `0x1801244f0`
- `0x1801249b0`
- `0x1801b4358`
- `0x180241010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800102c9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800102c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fefb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fefb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fa29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fa29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbc5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f9c5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f9c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010124`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010124`

## string_xrefs

- `0x18000ff16`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x18001005d`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800100b1`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800101ea`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x18001029b`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall PluginResourceManager::SignalPluginStart(
        PluginResourceManager *this,
        IID *rclsid,
        wchar_t *a3,
        unsigned int a4)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  __int64 v10; // r8
  void **v11; // r9
  __int64 v12; // rcx
  unsigned __int64 i; // rdx
  __int64 v14; // rax
  void **v15; // rcx
  _QWORD *v16; // rdi
  void **v17; // rdx
  _QWORD *v18; // r14
  _QWORD *v19; // rdx
  char v20; // r14
  int FilterHostProcessPoolManager; // eax
  __int64 v22; // r8
  unsigned int v23; // edi
  struct IFilterHostProcessPoolManager *v24; // rdi
  int v25; // eax
  unsigned int v26; // r14d
  struct _GUID v27; // xmm6
  void *v28; // rax
  int v29; // eax
  unsigned int v30; // r14d
  char *v31; // r13
  void **v32; // rdx
  __int64 v33; // r9
  __int64 v34; // r14
  unsigned __int64 j; // rcx
  __int64 v36; // rcx
  _QWORD *v37; // r15
  _QWORD *v38; // r12
  _QWORD *v39; // r12
  _QWORD *v40; // rdx
  void **v41; // rcx
  void **v42; // rdx
  unsigned __int64 k; // rcx
  _QWORD *v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r14
  __int64 v47; // r15
  _QWORD *v48; // rdx
  void **v49; // rcx
  struct IPluginResourceManager *v50; // r14
  void *v51; // rcx
  int v53; // eax
  _QWORD *v54; // r15
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rdx
  float v58; // xmm0_4
  __int64 v59; // rcx
  float v60; // xmm1_4
  _QWORD *v61; // rcx
  __int64 v62; // r14
  __int64 v63; // rax
  _QWORD *v64; // rdx
  unsigned int v65; // eax
  unsigned int v66; // ecx
  int v67; // eax
  __int64 v68; // rax
  __int64 v69; // rdx
  int v70; // [rsp+20h] [rbp-118h]
  __int64 v72; // [rsp+38h] [rbp-100h] BYREF
  struct IFilterHostProcessPoolManager *v73; // [rsp+40h] [rbp-F8h] BYREF
  void *v74; // [rsp+48h] [rbp-F0h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-E8h] BYREF
  unsigned __int64 v76; // [rsp+58h] [rbp-E0h] BYREF
  ULONGLONG TickCount64; // [rsp+60h] [rbp-D8h]
  __int64 v78; // [rsp+68h] [rbp-D0h]
  ULONGLONG v79; // [rsp+70h] [rbp-C8h]
  char v80; // [rsp+78h] [rbp-C0h]
  int v81; // [rsp+79h] [rbp-BFh]
  __int16 v82; // [rsp+7Dh] [rbp-BBh]
  char v83; // [rsp+7Fh] [rbp-B9h]
  struct IPluginResourceManager *v84; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v85; // [rsp+88h] [rbp-B0h]
  char *v86; // [rsp+90h] [rbp-A8h]
  _QWORD *v87; // [rsp+98h] [rbp-A0h]
  struct _GUID v88; // [rsp+A0h] [rbp-98h] BYREF
  __int128 v89; // [rsp+B0h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v90; // [rsp+C0h] [rbp-78h]
  void *Block[2]; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v92; // [rsp+D8h] [rbp-60h]
  unsigned __int64 v93; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v76 = (unsigned __int64)a3;
  *(_QWORD *)&v89 = rclsid;
  v74 = a3;
  if ( !g_pGatheringService )
  {
    v7 = -2147215342;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)0x80041812LL,
      v70);
    return v7;
  }
  SearchIndexerPluginIsolationTelemetry::SignalPluginStart<_GUID &,wchar_t const * &>(rclsid, &v74);
  lpsz = 0;
  v6 = StringFromCLSID(rclsid, &lpsz);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)(unsigned int)v6,
      v70);
LABEL_126:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    return v7;
  }
  *(_OWORD *)Block = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct_empty(Block);
  v8 = -1;
  do
    ++v8;
  while ( lpsz[v8] );
  try
  {
    std::wstring::_Assign<wchar_t>(Block);
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v10 = v92;
    v74 = this;
    v11 = (void **)Block[0];
    if ( v93 <= 7 )
      v11 = Block;
    v12 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * v92; ++i )
      v12 = 0x100000001B3LL * (*((unsigned __int8 *)v11 + i) ^ (unsigned __int64)v12);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      448,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx");
  }
  v14 = 2 * (v12 & *((_QWORD *)this + 17));
  v15 = (void **)*((_QWORD *)this + 14);
  v16 = v15[v14 + 1];
  v17 = (void **)((char *)this + 96);
  v86 = (char *)this + 96;
  if ( v16 != *((_QWORD **)this + 12) )
  {
    v18 = v15[v14];
    while ( 1 )
    {
      v19 = v16 + 2;
      if ( v16[5] > 7u )
        v19 = (_QWORD *)*v19;
      v15 = Block;
      if ( v93 > 7 )
        v15 = (void **)Block[0];
      if ( v10 == v16[4] )
      {
        if ( !v10 || !(unsigned int)std::_WChar_traits<wchar_t>::compare(v15, v19, v10) )
        {
          v17 = (void **)((char *)this + 96);
          goto LABEL_20;
        }
        v10 = v92;
      }
      if ( v16 == v18 )
        break;
      v16 = (_QWORD *)v16[1];
    }
    v17 = (void **)((char *)this + 96);
  }
  v16 = 0;
LABEL_20:
  if ( v16 && v16 != *v17 )
  {
    v20 = 0;
    ++*((_DWORD *)v16 + 14);
  }
  else
  {
    v20 = 1;
  }
  if ( v9 )
    LeaveCriticalSection(v9);
  if ( !v20 )
    goto LABEL_71;
  v73 = 0;
  FilterHostProcessPoolManager = CGatheringService::GetFilterHostProcessPoolManager((CGatheringService *)v15, &v73);
  v23 = FilterHostProcessPoolManager;
  if ( FilterHostProcessPoolManager < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)(unsigned int)FilterHostProcessPoolManager,
      v70);
    if ( v73 )
      winrt::com_ptr<IDatabase>::unconditional_release_ref(&v73);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)Block);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return v23;
  }
  v72 = 0;
  v24 = v73;
  LOBYTE(v22) = a4 != 0;
  v25 = (*(__int64 (__fastcall **)(struct IFilterHostProcessPoolManager *, unsigned __int64, __int64, __int64 *))(*(_QWORD *)v73 + 40LL))(
          v73,
          v76,
          v22,
          &v72);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)(unsigned int)v25,
      v70);
    if ( v72 )
      winrt::com_ptr<IDatabase>::unconditional_release_ref(&v72);
    if ( v24 )
      winrt::com_ptr<IDatabase>::unconditional_release_ref(&v73);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)Block);
    v7 = v26;
    goto LABEL_126;
  }
  EnterCriticalSection(v9);
  v90 = v9;
  v78 = 1;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  TickCount64 = GetTickCount64();
  v79 = TickCount64;
  v27 = *rclsid;
  v28 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 40LL))(v72);
  v88 = v27;
  v29 = CreateSinglePluginResourceHandler(v28, &v88, this, &v84);
  v30 = v29;
  if ( v29 >= 0 )
  {
    *(_QWORD *)&v88.Data1 = v72;
    v85 = v72;
    v31 = (char *)this + 88;
    v32 = Block;
    if ( v93 > 7 )
      v32 = (void **)Block[0];
    v33 = 0xCBF29CE484222325uLL;
    v34 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 2 * v92; ++j )
      v34 = 0x100000001B3LL * (*((unsigned __int8 *)v32 + j) ^ (unsigned __int64)v34);
    v36 = *((_QWORD *)v31 + 3);
    v37 = *(_QWORD **)(v36 + 16 * (*((_QWORD *)v31 + 6) & v34) + 8);
    v38 = (_QWORD *)*((_QWORD *)v31 + 1);
    if ( v37 != v38 )
    {
      v39 = *(_QWORD **)(v36 + 16 * (*((_QWORD *)v31 + 6) & v34));
      while ( 1 )
      {
        v40 = v37 + 2;
        if ( v37[5] > 7u )
          v40 = (_QWORD *)*v40;
        v41 = Block;
        if ( v93 > 7 )
          v41 = (void **)Block[0];
        if ( v92 == v37[4] )
        {
          if ( !v92 )
            goto LABEL_46;
          v53 = std::_WChar_traits<wchar_t>::compare(v41, v40, v92);
          v33 = 0xCBF29CE484222325uLL;
          if ( !v53 )
            goto LABEL_46;
        }
        if ( v37 == v39 )
        {
          v38 = v37;
          break;
        }
        v37 = (_QWORD *)v37[1];
      }
    }
    if ( *((_QWORD *)v31 + 2) == 0x2AAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v87 = 0;
    v54 = operator new(0x60u);
    v87 = v54;
    std::wstring::wstring(v54 + 2, Block, v55, v56);
    v54[6] = TickCount64;
    *((_DWORD *)v54 + 14) = v78;
    v54[8] = v79;
    *((_BYTE *)v54 + 72) = v80;
    v54[10] = v84;
    Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(v54 + 10);
    v54[11] = *(_QWORD *)&v88.Data1;
    v57 = *((_QWORD *)v31 + 2) + 1LL;
    if ( v57 < 0 )
      v58 = (float)(v57 & 1 | (unsigned int)((unsigned __int64)v57 >> 1))
          + (float)(v57 & 1 | (unsigned int)((unsigned __int64)v57 >> 1));
    else
      v58 = (float)(int)v57;
    v59 = *((_QWORD *)v31 + 7);
    if ( v59 < 0 )
    {
      v68 = *((_QWORD *)v31 + 7) & 1LL | ((unsigned __int64)v59 >> 1);
      v60 = (float)(int)v68 + (float)(int)v68;
    }
    else
    {
      v60 = (float)(int)v59;
    }
    if ( (float)(v58 / v60) > *(float *)v31 )
    {
      v69 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(v31);
      std::_Hash<std::_Umap_traits<std::wstring,PluginResourceManager::PluginAckInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,PluginResourceManager::PluginAckInfo>>,0>>::_Forced_rehash(
        v31,
        v69);
      v38 = *(_QWORD **)std::_Hash<std::_Umap_traits<std::wstring,PluginResourceManager::PluginAckInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,PluginResourceManager::PluginAckInfo>>,0>>::_Find_last<std::wstring>(
                          v31,
                          &v88,
                          v54 + 2,
                          v34);
    }
    v61 = (_QWORD *)v38[1];
    ++*((_QWORD *)v31 + 2);
    *v54 = v38;
    v54[1] = v61;
    *v61 = v54;
    v38[1] = v54;
    v62 = 2 * (*((_QWORD *)v31 + 6) & v34);
    v63 = *((_QWORD *)v31 + 3);
    v64 = *(_QWORD **)(v63 + 8 * v62);
    if ( v64 == *((_QWORD **)v31 + 1) )
    {
      *(_QWORD *)(v63 + 8 * v62) = v54;
    }
    else
    {
      if ( v64 == v38 )
      {
        *(_QWORD *)(v63 + 8 * v62) = v54;
        goto LABEL_92;
      }
      if ( *(_QWORD **)(v63 + 8 * v62 + 8) != v61 )
        goto LABEL_92;
    }
    *(_QWORD *)(v63 + 8 * v62 + 8) = v54;
LABEL_92:
    v33 = 0xCBF29CE484222325uLL;
LABEL_46:
    v42 = Block;
    if ( v93 > 7 )
      v42 = (void **)Block[0];
    for ( k = 0; k < 2 * v92; ++k )
      v33 = 0x100000001B3LL * (*((unsigned __int8 *)v42 + k) ^ (unsigned __int64)v33);
    v44 = v74;
    v45 = *((_QWORD *)v74 + 6);
    v46 = *(_QWORD *)(v45 + 16 * (v33 & *((_QWORD *)v74 + 9)) + 8);
    if ( v46 != *((_QWORD *)v74 + 4) )
    {
      v47 = *(_QWORD *)(v45 + 16 * (v33 & *((_QWORD *)v74 + 9)));
      while ( 1 )
      {
        v48 = (_QWORD *)(v46 + 16);
        if ( *(_QWORD *)(v46 + 40) > 7u )
          v48 = (_QWORD *)*v48;
        v49 = Block;
        if ( v93 > 7 )
          v49 = (void **)Block[0];
        if ( v92 == *(_QWORD *)(v46 + 32)
          && (!v92 || !(unsigned int)std::_WChar_traits<wchar_t>::compare(v49, v48, v92)) )
        {
          v44 = v74;
          goto LABEL_62;
        }
        if ( v46 == v47 )
          break;
        v46 = *(_QWORD *)(v46 + 8);
      }
      v44 = v74;
    }
    v46 = 0;
LABEL_62:
    if ( v46 && v46 != v44[4] )
    {
      v65 = *(_DWORD *)(v46 + 68);
      v66 = v65 + 1;
      if ( v65 + 1 < v65 )
      {
        v66 = *(_DWORD *)(v46 + 68);
        v67 = *(_DWORD *)(v46 + 60);
        *(_OWORD *)(v46 + 48) = 0;
        *(_QWORD *)(v46 + 64) = 0;
        *(_DWORD *)(v46 + 60) = v67;
      }
      *(_DWORD *)(v46 + 68) = v66;
    }
    v50 = v84;
    v89 = *(_OWORD *)v89;
    (*(void (__fastcall **)(struct IPluginResourceManager *, __int128 *, unsigned __int64, _QWORD))(*(_QWORD *)v84 + 80LL))(
      v84,
      &v89,
      v76,
      a4);
    if ( v50 )
      winrt::com_ptr<IDatabase>::unconditional_release_ref(&v84);
    if ( v9 )
      LeaveCriticalSection(v9);
    if ( v72 )
      winrt::com_ptr<IDatabase>::unconditional_release_ref(&v72);
    if ( v24 )
      winrt::com_ptr<IDatabase>::unconditional_release_ref(&v73);
LABEL_71:
    if ( v93 > 7 )
    {
      v76 = 2 * v93 + 2;
      v51 = Block[0];
      v74 = Block[0];
      if ( v76 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v74, &v76);
        v51 = v74;
      }
      operator delete(v51);
    }
    v92 = 0;
    v93 = 7;
    LOWORD(Block[0]) = 0;
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E5,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
    (const char *)(unsigned int)v29,
    v70);
  if ( v84 )
    winrt::com_ptr<IDatabase>::unconditional_release_ref(&v84);
  if ( v9 )
    LeaveCriticalSection(v9);
  if ( v72 )
    winrt::com_ptr<IDatabase>::unconditional_release_ref(&v72);
  if ( v24 )
    winrt::com_ptr<IDatabase>::unconditional_release_ref(&v73);
  ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)Block);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v30;
}

```

## disassembly

```asm
0x18000f950  mov     rax, rsp
0x18000f953  push    rbx
0x18000f954  push    rsi
0x18000f955  push    rdi
0x18000f956  push    r12
0x18000f958  push    r13
0x18000f95a  push    r14
0x18000f95c  push    r15
0x18000f95e  sub     rsp, 100h
0x18000f965  movaps  xmmword ptr [rax-48h], xmm6
0x18000f969  mov     rax, cs:__security_cookie
0x18000f970  xor     rax, rsp
0x18000f973  mov     [rsp+138h+var_50], rax
0x18000f97b  mov     [rsp+138h+var_108], r9d
0x18000f980  mov     rax, r8
0x18000f983  mov     [rsp+138h+var_E0], rax
0x18000f988  mov     r12, rdx
0x18000f98b  mov     qword ptr [rsp+138h+var_88], rdx
0x18000f993  mov     r13, rcx
0x18000f996  mov     [rsp+138h+var_F0], rax
0x18000f99b  xor     esi, esi
0x18000f99d  cmp     cs:?g_pGatheringService@@3PEAVCGatheringService@@EA, rsi; CGatheringService * g_pGatheringService
0x18000f9a4  jz      loc_18000FF06
0x18000f9aa  lea     rdx, [rsp+138h+var_F0]
0x18000f9af  mov     rcx, r12
0x18000f9b2  call    ??$SignalPluginStart@AEAU_GUID@@AEAPEB_W@SearchIndexerPluginIsolationTelemetry@@SAXAEAU_GUID@@AEAPEB_W@Z; SearchIndexerPluginIsolationTelemetry::SignalPluginStart<_GUID &,wchar_t const * &>(_GUID &,wchar_t const * &)
0x18000f9b7  nop
0x18000f9b8  mov     [rsp+138h+lpsz], rsi
0x18000f9bd  lea     rdx, [rsp+138h+lpsz]; lplpsz
0x18000f9c2  mov     rcx, r12; rclsid
0x18000f9c5  call    cs:__imp_StringFromCLSID
0x18000f9cb  mov     ebx, eax
0x18000f9cd  test    eax, eax
0x18000f9cf  js      loc_180010290
0x18000f9d5  xorps   xmm0, xmm0
0x18000f9d8  movups  xmmword ptr [rsp+138h+Block], xmm0
0x18000f9e0  mov     [rsp+138h+var_60], rsi
0x18000f9e8  mov     [rsp+138h+var_58], rsi
0x18000f9f0  lea     rcx, [rsp+138h+Block]
0x18000f9f8  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000f9fd  nop
0x18000f9fe  mov     rdx, [rsp+138h+lpsz]
0x18000fa03  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fa07  inc     r8
0x18000fa0a  cmp     [rdx+r8*2], si
0x18000fa0f  jnz     short loc_18000FA07
0x18000fa11  lea     rcx, [rsp+138h+Block]
0x18000fa19  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000fa1e  nop
0x18000fa1f  lea     rbx, [r13+98h]
0x18000fa26  mov     rcx, rbx; lpCriticalSection
0x18000fa29  call    cs:__imp_EnterCriticalSection
0x18000fa2f  mov     r8, [rsp+138h+var_60]
0x18000fa37  mov     [rsp+138h+var_F0], r13
0x18000fa3c  cmp     [rsp+138h+var_58], 7
0x18000fa45  mov     r9, [rsp+138h+Block]
0x18000fa4d  ja      short loc_18000FA57
0x18000fa4f  lea     r9, [rsp+138h+Block]
0x18000fa57  mov     rcx, 0CBF29CE484222325h
0x18000fa61  lea     r10, [r8+r8]
0x18000fa65  mov     rdx, rsi
0x18000fa68  mov     r15, 100000001B3h
0x18000fa72  test    r10, r10
0x18000fa75  jz      short loc_18000FA8B
0x18000fa77  movzx   eax, byte ptr [r9+rdx]
0x18000fa7c  xor     rcx, rax
0x18000fa7f  imul    rcx, r15
0x18000fa83  inc     rdx
0x18000fa86  cmp     rdx, r10
0x18000fa89  jb      short loc_18000FA77
0x18000fa8b  mov     rax, [r13+88h]
0x18000fa92  and     rax, rcx
0x18000fa95  add     rax, rax
0x18000fa98  mov     rcx, [r13+70h]
0x18000fa9c  mov     rdi, [rcx+rax*8+8]
0x18000faa1  lea     rdx, [r13+60h]
0x18000faa5  mov     [rsp+138h+var_A8], rdx
0x18000faad  cmp     rdi, [rdx]
0x18000fab0  jz      loc_1800102B2
0x18000fab6  mov     r14, [rcx+rax*8]
0x18000faba  lea     rdx, [rdi+10h]
0x18000fabe  cmp     qword ptr [rdi+28h], 7
0x18000fac3  jbe     short loc_18000FAC8
0x18000fac5  mov     rdx, [rdx]
0x18000fac8  lea     rcx, [rsp+138h+Block]
0x18000fad0  cmp     [rsp+138h+var_58], 7
0x18000fad9  cmova   rcx, [rsp+138h+Block]; this
0x18000fae2  cmp     r8, [rdi+20h]
0x18000fae6  jnz     short loc_18000FB11
0x18000fae8  test    r8, r8
0x18000faeb  jnz     short loc_18000FB00
0x18000faed  lea     rdx, [r13+60h]
0x18000faf1  test    rdi, rdi
0x18000faf4  jz      short loc_18000FAFB
0x18000faf6  cmp     rdi, [rdx]
0x18000faf9  jnz     short loc_18000FB20
0x18000fafb  mov     r14b, 1
0x18000fafe  jmp     short loc_18000FB26
0x18000fb00  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x18000fb05  test    eax, eax
0x18000fb07  jz      short loc_18000FAED
0x18000fb09  mov     r8, [rsp+138h+var_60]
0x18000fb11  cmp     rdi, r14
0x18000fb14  jz      loc_1800102AE
0x18000fb1a  mov     rdi, [rdi+8]
0x18000fb1e  jmp     short loc_18000FABA
0x18000fb20  mov     r14b, sil
0x18000fb23  inc     dword ptr [rdi+38h]
0x18000fb26  test    rbx, rbx
0x18000fb29  jnz     loc_18000FEF8
0x18000fb2f  test    r14b, r14b
0x18000fb32  jz      loc_18000FE3C
0x18000fb38  mov     [rsp+138h+var_F8], rsi
0x18000fb3d  lea     rdx, [rsp+138h+var_F8]; struct IFilterHostProcessPoolManager **
0x18000fb42  call    ?GetFilterHostProcessPoolManager@CGatheringService@@QEBAJPEAPEAUIFilterHostProcessPoolManager@@@Z; CGatheringService::GetFilterHostProcessPoolManager(IFilterHostProcessPoolManager * *)
0x18000fb47  mov     edi, eax
0x18000fb49  test    eax, eax
0x18000fb4b  js      loc_180010052
0x18000fb51  mov     [rsp+138h+var_100], rsi
0x18000fb56  mov     rdi, [rsp+138h+var_F8]
0x18000fb5b  mov     rax, [rdi]
0x18000fb5e  cmp     [rsp+138h+var_108], esi
0x18000fb62  setnz   r8b
0x18000fb66  lea     r9, [rsp+138h+var_100]
0x18000fb6b  mov     rdx, [rsp+138h+var_E0]
0x18000fb70  mov     rcx, rdi
0x18000fb73  mov     rax, [rax+28h]
0x18000fb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb7c  mov     r14d, eax
0x18000fb7f  test    eax, eax
0x18000fb81  js      loc_1800101DF
0x18000fb87  mov     rcx, rbx; lpCriticalSection
0x18000fb8a  call    cs:__imp_EnterCriticalSection
0x18000fb90  mov     [rsp+138h+var_78], rbx
0x18000fb98  mov     [rsp+138h+var_D0], 1
0x18000fba1  mov     [rsp+138h+var_C0], sil
0x18000fba6  xor     eax, eax
0x18000fba8  mov     [rsp+138h+var_BF], eax
0x18000fbac  mov     [rsp+138h+var_BB], ax
0x18000fbb1  mov     [rsp+138h+var_B9], al
0x18000fbb5  mov     [rsp+138h+var_B8], rsi
0x18000fbbd  mov     [rsp+138h+var_B0], rax
0x18000fbc5  call    cs:__imp_GetTickCount64
0x18000fbcb  mov     [rsp+138h+var_D8], rax
0x18000fbd0  mov     [rsp+138h+var_C8], rax
0x18000fbd5  movups  xmm6, xmmword ptr [r12]
0x18000fbda  mov     rcx, [rsp+138h+var_100]
0x18000fbdf  mov     rax, [rcx]
0x18000fbe2  mov     rax, [rax+28h]
0x18000fbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbeb  movdqu  xmmword ptr [rsp+138h+var_98.Data1], xmm6
0x18000fbf4  lea     r9, [rsp+138h+var_B8]; struct IPluginResourceManager **
0x18000fbfc  mov     r8, r13; struct IPluginResourceManager *
0x18000fbff  lea     rdx, [rsp+138h+var_98]; struct _GUID
0x18000fc07  mov     rcx, rax; void *
0x18000fc0a  call    ?CreateSinglePluginResourceHandler@@YAJPEAXU_GUID@@PEAUIPluginResourceManager@@PEAPEAU2@@Z; CreateSinglePluginResourceHandler(void *,_GUID,IPluginResourceManager *,IPluginResourceManager * *)
0x18000fc0f  mov     r14d, eax
0x18000fc12  test    eax, eax
0x18000fc14  js      loc_1800100A6
0x18000fc1a  mov     rax, [rsp+138h+var_100]
0x18000fc1f  mov     qword ptr [rsp+138h+var_98.Data1], rax
0x18000fc27  mov     [rsp+138h+var_B0], rax
0x18000fc2f  add     r13, 58h ; 'X'
0x18000fc33  mov     rax, [rsp+138h+var_60]
0x18000fc3b  lea     rdx, [rsp+138h+Block]
0x18000fc43  cmp     [rsp+138h+var_58], 7
0x18000fc4c  cmova   rdx, [rsp+138h+Block]
0x18000fc55  mov     r9, 0CBF29CE484222325h
0x18000fc5f  mov     r14, r9
0x18000fc62  lea     r8, [rax+rax]
0x18000fc66  mov     rcx, rsi
0x18000fc69  test    r8, r8
0x18000fc6c  jz      short loc_18000FC81
0x18000fc6e  movzx   eax, byte ptr [rcx+rdx]
0x18000fc72  xor     r14, rax
0x18000fc75  imul    r14, r15
0x18000fc79  inc     rcx
0x18000fc7c  cmp     rcx, r8
0x18000fc7f  jb      short loc_18000FC6E
0x18000fc81  mov     rax, r14
0x18000fc84  and     rax, [r13+30h]
0x18000fc88  add     rax, rax
0x18000fc8b  mov     rcx, [r13+18h]
0x18000fc8f  mov     r15, [rcx+rax*8+8]
0x18000fc94  mov     r12, [r13+8]
0x18000fc98  cmp     r15, r12
0x18000fc9b  jz      loc_18000FF2E
0x18000fca1  mov     r12, [rcx+rax*8]
0x18000fca5  lea     rdx, [r15+10h]
0x18000fca9  cmp     qword ptr [r15+28h], 7
0x18000fcae  jbe     short loc_18000FCB3
0x18000fcb0  mov     rdx, [rdx]
0x18000fcb3  mov     r8, [rsp+138h+var_60]
0x18000fcbb  lea     rcx, [rsp+138h+Block]
0x18000fcc3  cmp     [rsp+138h+var_58], 7
0x18000fccc  cmova   rcx, [rsp+138h+Block]
0x18000fcd5  cmp     r8, [r15+20h]
0x18000fcd9  jnz     loc_18000FEE6
0x18000fcdf  test    r8, r8
0x18000fce2  jnz     loc_18000FECF
0x18000fce8  mov     rax, [rsp+138h+var_60]
0x18000fcf0  lea     rdx, [rsp+138h+Block]
0x18000fcf8  cmp     [rsp+138h+var_58], 7
0x18000fd01  cmova   rdx, [rsp+138h+Block]
0x18000fd0a  lea     r8, [rax+rax]
0x18000fd0e  mov     rcx, rsi
0x18000fd11  test    r8, r8
0x18000fd14  jz      short loc_18000FD33
0x18000fd16  mov     r10, 100000001B3h
0x18000fd20  movzx   eax, byte ptr [rcx+rdx]
0x18000fd24  xor     r9, rax
0x18000fd27  imul    r9, r10
0x18000fd2b  inc     rcx
0x18000fd2e  cmp     rcx, r8
0x18000fd31  jb      short loc_18000FD20
0x18000fd33  mov     rdx, [rsp+138h+var_F0]
0x18000fd38  mov     rax, [rdx+48h]
0x18000fd3c  and     rax, r9
0x18000fd3f  add     rax, rax
0x18000fd42  mov     rcx, [rdx+30h]
0x18000fd46  mov     r14, [rcx+rax*8+8]
0x18000fd4b  cmp     r14, [rdx+20h]
0x18000fd4f  jz      loc_18001004A
0x18000fd55  mov     r15, [rcx+rax*8]
0x18000fd59  lea     rdx, [r14+10h]
0x18000fd5d  cmp     qword ptr [r14+28h], 7
0x18000fd62  jbe     short loc_18000FD67
0x18000fd64  mov     rdx, [rdx]
0x18000fd67  mov     r8, [rsp+138h+var_60]
0x18000fd6f  lea     rcx, [rsp+138h+Block]
0x18000fd77  cmp     [rsp+138h+var_58], 7
0x18000fd80  cmova   rcx, [rsp+138h+Block]
0x18000fd89  cmp     r8, [r14+20h]
0x18000fd8d  jnz     short loc_18000FD9D
0x18000fd8f  test    r8, r8
0x18000fd92  jz      short loc_18000FDAC
0x18000fd94  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x18000fd99  test    eax, eax
0x18000fd9b  jz      short loc_18000FDAC
0x18000fd9d  cmp     r14, r15
0x18000fda0  jz      loc_180010045
0x18000fda6  mov     r14, [r14+8]
0x18000fdaa  jmp     short loc_18000FD59
0x18000fdac  mov     rdx, [rsp+138h+var_F0]
0x18000fdb1  test    r14, r14
0x18000fdb4  jnz     loc_180010132
0x18000fdba  mov     r14, [rsp+138h+var_B8]
0x18000fdc2  mov     rax, qword ptr [rsp+138h+var_88]
0x18000fdca  movups  xmm0, xmmword ptr [rax]
0x18000fdcd  movdqu  [rsp+138h+var_88], xmm0
0x18000fdd6  mov     rax, [r14]
0x18000fdd9  mov     r9d, [rsp+138h+var_108]
0x18000fdde  mov     r8, [rsp+138h+var_E0]
0x18000fde3  lea     rdx, [rsp+138h+var_88]
0x18000fdeb  mov     rcx, r14
0x18000fdee  mov     rax, [rax+50h]
0x18000fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdf7  nop
0x18000fdf8  test    r14, r14
0x18000fdfb  jz      short loc_18000FE0B
0x18000fdfd  lea     rcx, [rsp+138h+var_B8]
0x18000fe05  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x18000fe0a  nop
0x18000fe0b  test    rbx, rbx
0x18000fe0e  jz      short loc_18000FE1A
0x18000fe10  mov     rcx, rbx; lpCriticalSection
0x18000fe13  call    cs:__imp_LeaveCriticalSection
0x18000fe19  nop
0x18000fe1a  cmp     [rsp+138h+var_100], rsi
0x18000fe1f  jz      short loc_18000FE2C
0x18000fe21  lea     rcx, [rsp+138h+var_100]
0x18000fe26  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x18000fe2b  nop
0x18000fe2c  test    rdi, rdi
0x18000fe2f  jz      short loc_18000FE3C
0x18000fe31  lea     rcx, [rsp+138h+var_F8]
0x18000fe36  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x18000fe3b  nop
0x18000fe3c  mov     rdx, [rsp+138h+var_58]
0x18000fe44  cmp     rdx, 7
0x18000fe48  jbe     short loc_18000FE76
0x18000fe4a  lea     rdx, ds:2[rdx*2]
0x18000fe52  mov     [rsp+138h+var_E0], rdx
0x18000fe57  mov     rcx, [rsp+138h+Block]; Block
0x18000fe5f  mov     [rsp+138h+var_F0], rcx
0x18000fe64  cmp     rdx, 1000h
0x18000fe6b  jnb     loc_18001017A
0x18000fe71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fe76  mov     [rsp+138h+var_60], rsi
0x18000fe7e  mov     [rsp+138h+var_58], 7
0x18000fe8a  mov     word ptr [rsp+138h+Block], si
0x18000fe92  mov     rcx, [rsp+138h+lpsz]; pv
0x18000fe97  test    rcx, rcx
0x18000fe9a  jz      short loc_18000FEA2
0x18000fe9c  call    cs:__imp_CoTaskMemFree
0x18000fea2  xor     eax, eax
0x18000fea4  mov     rcx, [rsp+138h+var_50]
0x18000feac  xor     rcx, rsp; StackCookie
0x18000feaf  call    __security_check_cookie
0x18000feb4  movaps  xmm6, [rsp+138h+var_48]
  ... truncated ...
```
