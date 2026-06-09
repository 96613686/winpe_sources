# CPersistedTableRegistryStore::SaveItemInfo(ushort const *,IShellItem *,ushort const *,ushort const *,ulong,Windows::Storage::AccessCache::RecentStorageItemVisibility)

- ea: `0x180120030`
- end: `0x18012087b`
- name: `?SaveItemInfo@CPersistedTableRegistryStore@@UEAAJPEBGPEAUIShellItem@@00KW4RecentStorageItemVisibility@AccessCache@Storage@Windows@@@Z`
- size: `2123`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180493540`

## callees

- `0x18000d6cc`
- `0x180010110`
- `0x180010220`
- `0x1800144c4`
- `0x1800432f0`
- `0x18004a030`
- `0x18005f240`
- `0x18006c2e4`
- `0x18006d038`
- `0x18006e148`
- `0x18006e168`
- `0x1800dd190`
- `0x18011d990`
- `0x18011f47c`
- `0x180120030`
- `0x180120884`
- `0x180120c90`
- `0x180120d70`
- `0x180121178`
- `0x1801211d0`
- `0x18012a358`
- `0x180148460`
- `0x180206074`
- `0x1802321c0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180120688`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180120688`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120444`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120444`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18012038f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18012038f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012029f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801202e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801202f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801203d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801203e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801204f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012052a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012029f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801202e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801202f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801203d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801203e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801204f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012052a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012082b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012082b`

## string_xrefs

- `0x180120725`: `FilePath`
- `0x18012039f`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801203bc`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x18012050e`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x18012059f`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801205bf`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801206be`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180120752`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180120774`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801207a1`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801207d9`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x18012084b`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180120864`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CPersistedTableRegistryStore::SaveItemInfo(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        int a7)
{
  int TableRegKey; // eax
  unsigned int v12; // ebx
  void *v13; // rax
  int LinkFromShellItemWithConditionalLinkTracking; // eax
  __int64 v15; // rax
  __int64 v16; // r8
  void *v17; // rdx
  int ItemStream; // eax
  void *v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int UnaliasedIDList; // eax
  void *v24; // rcx
  int v25; // eax
  ITEMIDLIST *v26; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v27; // rcx
  void *v28; // rdx
  struct IStream *v29; // rcx
  struct IUnknown *v30; // rcx
  ITEMIDLIST *v32; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v33; // rcx
  void *v34; // rdx
  struct IStream *v35; // rcx
  struct IUnknown *v36; // rcx
  int v37; // eax
  __int64 v38; // rdi
  int (__fastcall *v39)(__int64, LPVOID, LPVOID *, _QWORD); // rbx
  LPVOID v40; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v41; // rcx
  void *v42; // rdx
  struct IStream *v43; // rcx
  struct IUnknown *v44; // rcx
  void *v45; // rdx
  struct IStream *v46; // rcx
  struct IUnknown *v47; // rcx
  LPVOID v48; // rdi
  __int64 (__fastcall *v49)(LPVOID, LPCWCH *); // rbx
  int v50; // eax
  wil::details::in1diag3 *v51; // rcx
  __int64 v52; // rdx
  HRESULT v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  struct IStream *pstm; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v61; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v63; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-98h] BYREF
  __int64 v66; // [rsp+70h] [rbp-90h]
  __int64 v67; // [rsp+78h] [rbp-88h]
  LPVOID v68[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v69[192]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  WinRTStorageTelemetry::WatchCurrentThread(v69, "SaveItemInfo", 0);
  if ( (unsigned int)IsEffectiveLowIL() != 1 )
  {
    v12 = -2147024891;
    RoOriginateError(2147942405LL, 0);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)0x80070005LL,
      bIgnoreCase);
    goto LABEL_31;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  TableRegKey = CPersistedTableRegistryStore::_GetTableRegKey((CPersistedTableRegistryStore *)a1, 0x20006u, &hKey);
  v12 = TableRegKey;
  if ( TableRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)TableRegKey,
      bIgnoreCase);
    goto LABEL_39;
  }
  v61 = 0;
  pv = (LPVOID)-1LL;
  v13 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 120LL))(*(_QWORD *)(a1 + 24));
  LinkFromShellItemWithConditionalLinkTracking = wil::impersonate_token_nothrow(v13);
  v12 = LinkFromShellItemWithConditionalLinkTracking;
  if ( LinkFromShellItemWithConditionalLinkTracking < 0 )
  {
    v54 = 300;
LABEL_75:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v54,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)LinkFromShellItemWithConditionalLinkTracking,
      bIgnoreCase);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&pv);
LABEL_78:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    goto LABEL_39;
  }
  v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v61);
  LinkFromShellItemWithConditionalLinkTracking = _CreateLinkFromShellItemWithConditionalLinkTracking(0, a3, v16, v15);
  v12 = LinkFromShellItemWithConditionalLinkTracking;
  if ( LinkFromShellItemWithConditionalLinkTracking < 0 )
  {
    v54 = 302;
    goto LABEL_75;
  }
  if ( pv != (LPVOID)-1LL )
    wil::details::RevertImpersonateToken(pv, v17);
  pstm = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
  ItemStream = CPersistedTableRegistryStore::GetItemStream(
                 (CPersistedTableRegistryStore *)a1,
                 a2,
                 *(_BYTE *)(a1 + 40) == 0,
                 1u,
                 &pstm);
  v12 = ItemStream;
  if ( ItemStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)ItemStream,
      bIgnoreCasea);
LABEL_77:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
    goto LABEL_78;
  }
  Token = (HANDLE)-1LL;
  v19 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 120LL))(*(_QWORD *)(a1 + 24));
  v20 = wil::impersonate_token_nothrow(v19);
  v12 = v20;
  if ( v20 < 0 )
  {
    v55 = 314;
LABEL_81:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCasea);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&Token);
    goto LABEL_77;
  }
  v20 = IUnknown_SaveKnownImplToStream(pstm, (const struct _GUID *const *)&off_1806710A0, 1u, v61);
  v12 = v20;
  if ( v20 < 0 )
  {
    v55 = 316;
    goto LABEL_81;
  }
  v20 = SHRegSetString(hKey, a2, L"Metadata", a4);
  v12 = v20;
  if ( v20 < 0 )
  {
    v55 = 318;
    goto LABEL_81;
  }
  if ( a5 )
  {
    v20 = SHRegSetString(hKey, a2, L"PackageFamilyName", a5);
    v12 = v20;
    if ( v20 < 0 )
    {
      v55 = 319;
      goto LABEL_81;
    }
  }
  v21 = SHRegSetDWORD(hKey, a2, L"Flags", a6);
  v12 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCasea);
    if ( Token != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(Token, v45);
    v46 = pstm;
    if ( pstm )
    {
      pstm = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
    }
    goto LABEL_39;
  }
  v63 = 0;
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, struct _ITEMIDLIST_ABSOLUTE **))v61->lpVtbl[1].AddRef)(v61, &v63);
  v12 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v22,
      bIgnoreCasea);
    v41 = v63;
    v63 = 0;
    CoTaskMemFree(v41);
    if ( Token != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(Token, v42);
    v43 = pstm;
    if ( pstm )
    {
      pstm = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IUnknown *))v44->lpVtbl->Release)(v44);
    }
    goto LABEL_39;
  }
  if ( *(_BYTE *)(a1 + 40) )
    goto LABEL_16;
  v68[0] = 0;
  v68[1] = (LPVOID)-1LL;
  v68[2] = (LPVOID)-1LL;
  v37 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a3 + 40LL))(a3, 2147647488LL, v68);
  if ( v37 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v37,
      bIgnoreCasea);
  }
  else if ( *(_QWORD *)(a1 + 32)
         || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 32),
             CoCreateInstance(
               &CLSID_SyncRootManager,
               0,
               1u,
               &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
               (LPVOID *)(a1 + 32)) >= 0) )
  {
    pv = 0;
    v38 = *(_QWORD *)(a1 + 32);
    v39 = *(int (__fastcall **)(__int64, LPVOID, LPVOID *, _QWORD))(*(_QWORD *)v38 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    bIgnoreCasea = 0;
    if ( v39(v38, v68[0], &pv, 0) < 0 )
      goto LABEL_44;
    lpString1 = 0;
    v66 = 0;
    v67 = 0;
    v48 = pv;
    v49 = *(__int64 (__fastcall **)(LPVOID, LPCWCH *))(*(_QWORD *)pv + 40LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    v66 = -1;
    v67 = -1;
    v50 = v49(v48, &lpString1);
    v51 = retaddr;
    if ( v50 < 0 )
    {
      v52 = 340;
    }
    else
    {
      if ( CompareStringOrdinal(lpString1, -1, L"SkyDrive", -1, 1) != 2 )
        goto LABEL_68;
      v50 = SHRegSetBOOL(hKey, a2, L"Roamable", 1);
      v51 = retaddr;
      if ( v50 >= 0 )
        goto LABEL_68;
      v52 = 341;
    }
    wil::details::in1diag3::_Log_Hr(
      v51,
      (void *)v52,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v50,
      bIgnoreCasea);
LABEL_68:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
LABEL_44:
    v40 = pv;
    if ( pv )
    {
      pv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
    }
  }
  if ( v68[0] )
    CoTaskMemFree(v68[0]);
LABEL_16:
  pidl = 0;
  UnaliasedIDList = GetUnaliasedIDList(v63, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
  if ( UnaliasedIDList < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)UnaliasedIDList,
      bIgnoreCasea);
  }
  else
  {
    pv = 0;
    if ( (int)RebaseOnVolumeID(pidl, (LPITEMIDLIST *)&pv) >= 0 )
    {
      lpString1 = 0;
      v66 = 0;
      v67 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      v66 = -1;
      v67 = -1;
      v53 = SHGetNameFromIDList((LPCITEMIDLIST)pv, SIGDN_FILESYSPATH, (PWSTR *)&lpString1);
      if ( v53 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
          (const char *)(unsigned int)v53,
          bIgnoreCasea);
      else
        SHRegSetString(hKey, a2, L"FilePath", lpString1);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    }
    v24 = pv;
    pv = 0;
    CoTaskMemFree(v24);
  }
  v25 = SHRegSetBOOL(hKey, a2, L"SystemVisible", a7 == 1);
  v12 = v25;
  if ( v25 >= 0 )
  {
    if ( a7 == 1 )
      CPersistedTableRegistryStore::AddToSystemRecentDocs((CPersistedTableRegistryStore *)a1, v63);
    v26 = (ITEMIDLIST *)pidl;
    pidl = 0;
    CoTaskMemFree(v26);
    v27 = v63;
    v63 = 0;
    CoTaskMemFree(v27);
    if ( Token != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(Token, v28);
    v29 = pstm;
    if ( pstm )
    {
      pstm = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v61;
    if ( v61 )
    {
      v61 = 0;
      ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
    }
    if ( hKey )
      RegCloseKey(hKey);
    v12 = 0;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16F,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
    (const char *)(unsigned int)v25,
    bIgnoreCasea);
  v32 = (ITEMIDLIST *)pidl;
  pidl = 0;
  CoTaskMemFree(v32);
  v33 = v63;
  v63 = 0;
  CoTaskMemFree(v33);
  if ( Token != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(Token, v34);
  v35 = pstm;
  if ( pstm )
  {
    pstm = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v61;
  if ( v61 )
  {
    v61 = 0;
    ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_31:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v69);
  return v12;
}

```

## disassembly

```asm
0x180120030  push    rbp
0x180120032  push    rbx
0x180120033  push    rsi
0x180120034  push    rdi
0x180120035  push    r12
0x180120037  push    r13
0x180120039  push    r14
0x18012003b  push    r15
0x18012003d  lea     rbp, [rsp-78h]
0x180120042  sub     rsp, 178h
0x180120049  mov     rax, cs:__security_cookie
0x180120050  xor     rax, rsp
0x180120053  mov     [rbp+0B0h+var_50], rax
0x180120057  mov     r12, r9
0x18012005a  mov     r15, r8
0x18012005d  mov     r14, rdx
0x180120060  mov     rsi, rcx
0x180120063  mov     rdi, [rbp+0B0h+arg_20]
0x18012006a  xor     r8d, r8d
0x18012006d  lea     rdx, aSaveiteminfo; "SaveItemInfo"
0x180120074  lea     rcx, [rbp+0B0h+var_110]
0x180120078  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x18012007d  nop
0x18012007e  call    ?IsEffectiveLowIL@@YAJXZ; IsEffectiveLowIL(void)
0x180120083  cmp     eax, 1
0x180120086  jnz     loc_180120386
0x18012008c  xor     r13d, r13d
0x18012008f  mov     [rsp+1B0h+hKey], r13
0x180120094  xor     edx, edx
0x180120096  lea     rcx, [rsp+1B0h+hKey]
0x18012009b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801200a0  lea     r8, [rsp+1B0h+hKey]; HKEY *
0x1801200a5  mov     edx, 20006h; unsigned int
0x1801200aa  mov     rcx, rsi; this
0x1801200ad  call    ?_GetTableRegKey@CPersistedTableRegistryStore@@AEAAJKPEAPEAUHKEY__@@@Z; CPersistedTableRegistryStore::_GetTableRegKey(ulong,HKEY__ * *)
0x1801200b2  mov     ebx, eax
0x1801200b4  test    eax, eax
0x1801200b6  js      loc_180120748
0x1801200bc  mov     [rsp+1B0h+var_168], r13
0x1801200c1  mov     [rsp+1B0h+pv], 0FFFFFFFFFFFFFFFFh
0x1801200ca  mov     rcx, [rsi+18h]
0x1801200ce  mov     rax, [rcx]
0x1801200d1  mov     rax, [rax+78h]
0x1801200d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801200da  mov     rcx, rax; Token
0x1801200dd  lea     rdx, [rsp+1B0h+pv]
0x1801200e2  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1801200e7  mov     ebx, eax
0x1801200e9  test    eax, eax
0x1801200eb  js      loc_180120768
0x1801200f1  lea     rcx, [rsp+1B0h+var_168]
0x1801200f6  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x1801200fb  mov     r9, rax
0x1801200fe  mov     rdx, r15
0x180120101  xor     ecx, ecx
0x180120103  call    ?_CreateLinkFromShellItemWithConditionalLinkTracking@@YAJW4CLFITFLAGS@@PEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; _CreateLinkFromShellItemWithConditionalLinkTracking(CLFITFLAGS,IShellItem *,_GUID const &,void * *)
0x180120108  mov     ebx, eax
0x18012010a  test    eax, eax
0x18012010c  js      loc_18012076F
0x180120112  mov     rcx, [rsp+1B0h+pv]; Token
0x180120117  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012011b  jz      short loc_180120122
0x18012011d  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180120122  mov     [rsp+1B0h+pstm], r13
0x180120127  lea     rcx, [rsp+1B0h+pstm]
0x18012012c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180120131  mov     r8d, r13d
0x180120134  cmp     [rsi+28h], r13b
0x180120138  setz    r8b; int
0x18012013c  lea     rax, [rsp+1B0h+pstm]
0x180120141  mov     qword ptr [rsp+1B0h+bIgnoreCase], rax; int
0x180120146  mov     r9d, 1; unsigned int
0x18012014c  mov     rdx, r14; unsigned __int16 *
0x18012014f  mov     rcx, rsi; this
0x180120152  call    ?GetItemStream@CPersistedTableRegistryStore@@UEAAJPEBGHKPEAPEAUIStream@@@Z; CPersistedTableRegistryStore::GetItemStream(ushort const *,int,ulong,IStream * *)
0x180120157  mov     ebx, eax
0x180120159  test    eax, eax
0x18012015b  js      loc_180120797
0x180120161  mov     [rsp+1B0h+Token], 0FFFFFFFFFFFFFFFFh
0x18012016a  mov     rcx, [rsi+18h]
0x18012016e  mov     rax, [rcx]
0x180120171  mov     rax, [rax+78h]
0x180120175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012017a  mov     rcx, rax; Token
0x18012017d  lea     rdx, [rsp+1B0h+Token]
0x180120182  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x180120187  mov     ebx, eax
0x180120189  test    eax, eax
0x18012018b  js      loc_1801207CD
0x180120191  mov     r9, [rsp+1B0h+var_168]; struct IUnknown *
0x180120196  mov     r8d, 1; unsigned int
0x18012019c  lea     rdx, off_1806710A0; struct _GUID **
0x1801201a3  mov     rcx, [rsp+1B0h+pstm]; pstm
0x1801201a8  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1801201ad  mov     ebx, eax
0x1801201af  test    eax, eax
0x1801201b1  js      loc_1801207FC
0x1801201b7  mov     r9, r12; unsigned __int16 *
0x1801201ba  lea     r8, aMetadata; "Metadata"
0x1801201c1  mov     rdx, r14; unsigned __int16 *
0x1801201c4  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801201c9  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801201ce  mov     ebx, eax
0x1801201d0  test    eax, eax
0x1801201d2  js      loc_180120803
0x1801201d8  test    rdi, rdi
0x1801201db  jz      short loc_1801201FE
0x1801201dd  mov     r9, rdi; unsigned __int16 *
0x1801201e0  lea     r8, aPackagefamilyn_0; "PackageFamilyName"
0x1801201e7  mov     rdx, r14; unsigned __int16 *
0x1801201ea  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801201ef  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801201f4  mov     ebx, eax
0x1801201f6  test    eax, eax
0x1801201f8  js      loc_1801207D4
0x1801201fe  mov     r9d, [rbp+0B0h+arg_28]; unsigned int
0x180120205  lea     r8, aFlags; "Flags"
0x18012020c  mov     rdx, r14; unsigned __int16 *
0x18012020f  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x180120214  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180120219  mov     ebx, eax
0x18012021b  test    eax, eax
0x18012021d  js      loc_1801205B5
0x180120223  mov     [rsp+1B0h+var_158], r13
0x180120228  mov     rcx, [rsp+1B0h+var_168]
0x18012022d  mov     rax, [rcx]
0x180120230  lea     rdx, [rsp+1B0h+var_158]
0x180120235  mov     rax, [rax+20h]
0x180120239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012023e  mov     ebx, eax
0x180120240  test    eax, eax
0x180120242  js      loc_180120504
0x180120248  cmp     [rsi+28h], r13b
0x18012024c  jz      loc_18012044F
0x180120252  or      r12, 0FFFFFFFFFFFFFFFFh
0x180120256  mov     [rsp+1B0h+pidl], r13
0x18012025b  lea     rdx, [rsp+1B0h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180120260  mov     rcx, [rsp+1B0h+var_158]; struct _ITEMIDLIST_ABSOLUTE *
0x180120265  call    ?GetUnaliasedIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; GetUnaliasedIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18012026a  mov     rcx, [rbp+0B8h]; this
0x180120271  test    eax, eax
0x180120273  js      loc_180120848
0x180120279  mov     [rsp+1B0h+pv], r13
0x18012027e  lea     rdx, [rsp+1B0h+pv]; ppidl
0x180120283  mov     rcx, [rsp+1B0h+pidl]; pidl
0x180120288  call    RebaseOnVolumeID
0x18012028d  test    eax, eax
0x18012028f  jns     loc_1801206DA
0x180120295  mov     rcx, [rsp+1B0h+pv]; pv
0x18012029a  mov     [rsp+1B0h+pv], r13
0x18012029f  call    cs:__imp_CoTaskMemFree
0x1801202a5  mov     r9d, r13d
0x1801202a8  cmp     [rbp+0B0h+arg_30], 1
0x1801202af  setz    r9b; int
0x1801202b3  lea     r8, aSystemvisible; "SystemVisible"
0x1801202ba  mov     rdx, r14; unsigned __int16 *
0x1801202bd  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801202c2  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1801202c7  mov     ebx, eax
0x1801202c9  test    eax, eax
0x1801202cb  js      loc_1801203B2
0x1801202d1  cmp     [rbp+0B0h+arg_30], 1
0x1801202d8  jz      loc_180120583
0x1801202de  mov     rcx, [rsp+1B0h+pidl]; pv
0x1801202e3  mov     [rsp+1B0h+pidl], r13
0x1801202e8  call    cs:__imp_CoTaskMemFree
0x1801202ee  nop
0x1801202ef  mov     rcx, [rsp+1B0h+var_158]; pv
0x1801202f4  mov     [rsp+1B0h+var_158], r13
0x1801202f9  call    cs:__imp_CoTaskMemFree
0x1801202ff  nop
0x180120300  mov     rcx, [rsp+1B0h+Token]; Token
0x180120305  cmp     rcx, r12
0x180120308  jz      short loc_180120310
0x18012030a  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18012030f  nop
0x180120310  mov     rcx, [rsp+1B0h+pstm]
0x180120315  test    rcx, rcx
0x180120318  jz      short loc_18012032C
0x18012031a  mov     [rsp+1B0h+pstm], r13
0x18012031f  mov     rax, [rcx]
0x180120322  mov     rax, [rax+10h]
0x180120326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012032b  nop
0x18012032c  mov     rcx, [rsp+1B0h+var_168]
0x180120331  test    rcx, rcx
0x180120334  jz      short loc_180120348
0x180120336  mov     [rsp+1B0h+var_168], r13
0x18012033b  mov     rax, [rcx]
0x18012033e  mov     rax, [rax+10h]
0x180120342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120347  nop
0x180120348  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18012034d  test    rcx, rcx
0x180120350  jz      short loc_180120358
0x180120352  call    cs:__imp_RegCloseKey
0x180120358  mov     ebx, r13d
0x18012035b  lea     rcx, [rbp+0B0h+var_110]; this
0x18012035f  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x180120364  mov     eax, ebx
0x180120366  mov     rcx, [rbp+0B0h+var_50]
0x18012036a  xor     rcx, rsp; StackCookie
0x18012036d  call    __security_check_cookie
0x180120372  add     rsp, 178h
0x180120379  pop     r15
0x18012037b  pop     r14
0x18012037d  pop     r13
0x18012037f  pop     r12
0x180120381  pop     rdi
0x180120382  pop     rsi
0x180120383  pop     rbx
0x180120384  pop     rbp
0x180120385  retn
0x180120386  xor     edx, edx
0x180120388  mov     ebx, 80070005h
0x18012038d  mov     ecx, ebx
0x18012038f  call    cs:__imp_RoOriginateError
0x180120395  mov     rcx, [rbp+0B8h]; this
0x18012039c  mov     r9d, ebx; char *
0x18012039f  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801203a6  mov     edx, 122h; void *
0x1801203ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801203b0  jmp     short loc_18012035B
0x1801203b2  mov     rcx, [rbp+0B8h]; this
0x1801203b9  mov     r9d, eax; char *
0x1801203bc  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801203c3  mov     edx, 16Fh; void *
0x1801203c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801203cd  nop
0x1801203ce  mov     rcx, [rsp+1B0h+pidl]; pv
0x1801203d3  mov     [rsp+1B0h+pidl], r13
0x1801203d8  call    cs:__imp_CoTaskMemFree
0x1801203de  nop
0x1801203df  mov     rcx, [rsp+1B0h+var_158]; pv
0x1801203e4  mov     [rsp+1B0h+var_158], r13
0x1801203e9  call    cs:__imp_CoTaskMemFree
0x1801203ef  nop
0x1801203f0  mov     rcx, [rsp+1B0h+Token]; Token
0x1801203f5  cmp     rcx, r12
0x1801203f8  jnz     loc_180120579
0x1801203fe  mov     rcx, [rsp+1B0h+pstm]
0x180120403  test    rcx, rcx
0x180120406  jz      short loc_18012041A
0x180120408  mov     [rsp+1B0h+pstm], r13
0x18012040d  mov     rax, [rcx]
0x180120410  mov     rax, [rax+10h]
0x180120414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120419  nop
0x18012041a  mov     rcx, [rsp+1B0h+var_168]
0x18012041f  test    rcx, rcx
0x180120422  jz      short loc_180120436
0x180120424  mov     [rsp+1B0h+var_168], r13
0x180120429  mov     rax, [rcx]
0x18012042c  mov     rax, [rax+10h]
0x180120430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120435  nop
0x180120436  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18012043b  test    rcx, rcx
0x18012043e  jz      loc_18012035B
0x180120444  call    cs:__imp_RegCloseKey
0x18012044a  jmp     loc_18012035B
0x18012044f  mov     [rbp+0B0h+var_130], r13
0x180120453  or      r12, 0FFFFFFFFFFFFFFFFh
0x180120457  mov     [rbp+0B0h+var_128], r12
0x18012045b  mov     [rbp+0B0h+var_120], r12
0x18012045f  mov     rax, [r15]
0x180120462  lea     r8, [rbp+0B0h+var_130]
0x180120466  mov     edx, 80028000h
0x18012046b  mov     rcx, r15
0x18012046e  mov     rax, [rax+28h]
0x180120472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120477  mov     rcx, [rbp+0B8h]; this
0x18012047e  test    eax, eax
0x180120480  js      loc_18012059C
0x180120486  lea     rdi, [rsi+20h]
0x18012048a  cmp     [rdi], r13
0x18012048d  jz      loc_18012080A
0x180120493  mov     [rsp+1B0h+pv], r13
0x180120498  mov     rdi, [rdi]
0x18012049b  mov     rax, [rdi]
0x18012049e  mov     rbx, [rax+20h]
0x1801204a2  lea     rcx, [rsp+1B0h+pv]
0x1801204a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801204ac  mov     qword ptr [rsp+1B0h+bIgnoreCase], r13
0x1801204b1  xor     r9d, r9d
0x1801204b4  lea     r8, [rsp+1B0h+pv]
0x1801204b9  mov     rdx, [rbp+0B0h+var_130]
0x1801204bd  mov     rcx, rdi
0x1801204c0  mov     rax, rbx
0x1801204c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801204c8  test    eax, eax
0x1801204ca  jns     loc_180120620
0x1801204d0  mov     rcx, [rsp+1B0h+pv]
0x1801204d5  test    rcx, rcx
0x1801204d8  jz      short loc_1801204EC
0x1801204da  mov     [rsp+1B0h+pv], r13
0x1801204df  mov     rax, [rcx]
0x1801204e2  mov     rax, [rax+10h]
0x1801204e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801204eb  nop
  ... truncated ...
```
