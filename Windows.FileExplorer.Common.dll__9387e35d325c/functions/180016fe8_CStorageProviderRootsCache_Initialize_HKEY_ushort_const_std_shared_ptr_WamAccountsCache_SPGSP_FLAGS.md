# CStorageProviderRootsCache::Initialize(HKEY__ *,ushort const *,std::shared_ptr<WamAccountsCache>,SPGSP_FLAGS)

- ea: `0x180016fe8`
- end: `0x180017a92`
- name: `?Initialize@CStorageProviderRootsCache@@QEAAJPEAUHKEY__@@PEBGV?$shared_ptr@VWamAccountsCache@@@std@@W4SPGSP_FLAGS@@@Z`
- size: `2730`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, __int64, char)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800165bc`

## callees

- `0x180007900`
- `0x18000a5b0`
- `0x18000b178`
- `0x18000b9b0`
- `0x18000bc30`
- `0x18000c450`
- `0x180016fe8`
- `0x180018074`
- `0x18001ca98`
- `0x18001cc20`
- `0x18001cda4`
- `0x18001f52c`
- `0x1800207b4`
- `0x180020d54`
- `0x180020e2c`
- `0x1800222ec`
- `0x1800280d4`
- `0x180037780`
- `0x18006c318`
- `0x180083410`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x18001718c`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800171f7`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800172d6`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017341`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800173b6`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017421`
- `SHCORE!__imp_GUIDFromStringW` at `0x18001748c`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800174f7`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017562`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800175cd`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017649`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800176c9`
- `SHCORE!__imp_GUIDFromStringW` at `0x18001718c`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800171f7`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800172d6`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017341`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800173b6`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017421`
- `SHCORE!__imp_GUIDFromStringW` at `0x18001748c`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800174f7`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017562`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800175cd`
- `SHCORE!__imp_GUIDFromStringW` at `0x180017649`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800176c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001785f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800178fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800179bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001785f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800178fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800179bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017054`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017054`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017161`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800171d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017246`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800172b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001731b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017390`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800173fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017466`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001753c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800175a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017623`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800176a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001771b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017161`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800171d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017246`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800172b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001731b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017390`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800173fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017466`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001753c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800175a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017623`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800176a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001771b`

## string_xrefs

- `0x1800173ed`: `UriHandler`
- `0x180017615`: `StorageProviderShareLinkSource`
- `0x18001752e`: `NamespaceCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CStorageProviderRootsCache::Initialize(__int64 a1, HKEY a2, const WCHAR *a3, __int64 a4, char a5)
{
  char v8; // r15
  LSTATUS v9; // eax
  signed int CopyHookClsid; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // r8
  int ValueW; // eax
  LSTATUS v16; // eax
  bool v17; // sf
  LSTATUS v18; // eax
  bool v19; // sf
  LSTATUS v20; // eax
  bool v21; // sf
  LSTATUS v22; // eax
  bool v23; // sf
  LSTATUS v24; // eax
  bool v25; // sf
  LSTATUS v26; // eax
  bool v27; // sf
  LSTATUS v28; // eax
  bool v29; // sf
  LSTATUS v30; // eax
  bool v31; // sf
  LSTATUS v32; // eax
  bool v33; // sf
  LSTATUS v34; // eax
  bool v35; // sf
  LSTATUS v36; // eax
  bool v37; // sf
  LSTATUS v38; // eax
  bool v39; // sf
  LSTATUS v40; // eax
  bool v41; // sf
  char v42; // si
  char v43; // r14
  __int64 v44; // r14
  void *v45; // rcx
  char v46; // r14
  __int64 v47; // r14
  void *v48; // rcx
  char v49; // r14
  __int64 v50; // r14
  void *v51; // rcx
  __int64 v52; // rsi
  void *v53; // rcx
  std::_Ref_count_base *v54; // rcx
  unsigned int *pvData; // [rsp+28h] [rbp-D8h]
  unsigned int *pvDataa; // [rsp+28h] [rbp-D8h]
  unsigned int *pvDatab; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v61; // [rsp+50h] [rbp-B0h] BYREF
  void *v62; // [rsp+58h] [rbp-A8h] BYREF
  char v63; // [rsp+60h] [rbp-A0h]
  __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v67[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v68[40]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v69[56]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v70[2088]; // [rsp+150h] [rbp+50h] BYREF

  v67[1] = a4;
  v8 = 0;
  pcbData = 0;
  hkey = 0;
  v9 = RegOpenKeyExW(a2, a3, 0, 0x20119u, &hkey);
  CopyHookClsid = v9;
  if ( v9 > 0 )
    CopyHookClsid = (unsigned __int16)v9 | 0x80070000;
  if ( CopyHookClsid >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    *(_QWORD *)(a1 + 8) = -1;
    *(_QWORD *)(a1 + 16) = -1;
    CopyHookClsid = _AllocString<CTCoAllocPolicy>(v12, v11, a3, a1);
    if ( CopyHookClsid < 0 )
      goto LABEL_140;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1 + 24);
    *(_QWORD *)(a1 + 32) = -1;
    *(_QWORD *)(a1 + 40) = -1;
    CopyHookClsid = SHRegAllocData(hkey, 0, L"DisplayNameResource", 268435462, (void **)(a1 + 24), pvData);
    if ( CopyHookClsid < 0
      || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1 + 48),
          *(_QWORD *)(a1 + 56) = -1,
          *(_QWORD *)(a1 + 64) = -1,
          CopyHookClsid = SHRegAllocData(hkey, 0, L"IconResource", 268435462, (void **)(a1 + 48), pvDataa),
          CopyHookClsid < 0) )
    {
LABEL_140:
      RegCloseKey(hkey);
      goto LABEL_141;
    }
    SHRegGetDWORD(hkey, v13, v14, (unsigned int *)(a1 + 544));
    pcbData = 78;
    ValueW = RegGetValueW(hkey, 0, L"Handler", 2u, 0, v68, &pcbData);
    if ( ValueW )
    {
      v68[0] = 0;
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    if ( ValueW >= 0 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 336) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v16 = RegGetValueW(hkey, 0, L"BannerNotificationHandler", 2u, 0, v68, &pcbData);
    v17 = v16 < 0;
    if ( v16 )
    {
      v68[0] = 0;
      if ( v16 > 0 )
        v17 = 1;
    }
    if ( !v17 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 352) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 100;
    v18 = RegGetValueW(hkey, 0, L"ProtectionMode", 2u, 0, v69, &pcbData);
    v19 = v18 < 0;
    if ( v18 )
    {
      v69[0] = 0;
      if ( v18 > 0 )
        v19 = 1;
    }
    if ( !v19 )
      CopyHookClsid = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                        a1 + 72,
                        v69,
                        -1);
    if ( CopyHookClsid < 0 )
    {
LABEL_72:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl)
        && CopyHookClsid >= 0 )
      {
        pcbData = 78;
        v36 = RegGetValueW(hkey, 0, L"StorageProviderShareLinkSource", 2u, 0, v68, &pcbData);
        v37 = v36 < 0;
        if ( v36 )
        {
          v68[0] = 0;
          if ( v36 > 0 )
            v37 = 1;
        }
        if ( !v37 )
          CopyHookClsid = (unsigned int)GUIDFromStringW(v68, a1 + 512) == 0 ? 0x8007065E : 0;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
      {
        if ( CopyHookClsid >= 0 )
        {
          pcbData = 78;
          v38 = RegGetValueW(hkey, 0, L"SearchHandlerFactory", 2u, 0, v68, &pcbData);
          v39 = v38 < 0;
          if ( v38 )
          {
            v68[0] = 0;
            if ( v38 > 0 )
              v39 = 1;
          }
          if ( v39 )
            goto LABEL_90;
          if ( (unsigned int)GUIDFromStringW(v68, a1 + 528) )
          {
            CopyHookClsid = 0;
            goto LABEL_90;
          }
          CopyHookClsid = -2147023266;
        }
      }
      else if ( CopyHookClsid >= 0 )
      {
LABEL_90:
        pcbData = 4168;
        v40 = RegGetValueW(hkey, 0, L"RecycleBinUrl", 2u, 0, v70, &pcbData);
        v41 = v40 < 0;
        if ( v40 )
        {
          v70[0] = 0;
          if ( v40 > 0 )
            v41 = 1;
        }
        if ( !v41 )
          CopyHookClsid = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                            a1 + 96,
                            v70,
                            -1);
      }
      v67[0] = 0;
      v42 = 1;
      if ( CopyHookClsid < 0
        || (v61 = v67, v62 = 0, v63 = 1, v8 = 1, v43 = 1, SHRegAllocData(hkey, 0, L"Cid", 2, &v62, pvDatab) < 0) )
      {
        v43 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v8 &= ~1u;
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v61);
      }
      if ( v43 )
      {
        v44 = v67[0];
        v67[0] = 0;
        v45 = *(void **)(a1 + 216);
        if ( v45 )
          CoTaskMemFree(v45);
        *(_QWORD *)(a1 + 216) = v44;
        *(_QWORD *)(a1 + 232) = -1;
        *(_QWORD *)(a1 + 224) = -1;
      }
      v66 = 0;
      if ( CopyHookClsid < 0
        || (v61 = &v66, v62 = 0,
                        v63 = 1,
                        v8 |= 2u,
                        v46 = 1,
                        SHRegAllocData(hkey, 0, L"TenantName", 2, &v62, pvDatab) < 0) )
      {
        v46 = 0;
      }
      if ( (v8 & 2) != 0 )
      {
        v8 &= ~2u;
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v61);
      }
      if ( v46 )
      {
        v47 = v66;
        v66 = 0;
        v48 = *(void **)(a1 + 240);
        if ( v48 )
          CoTaskMemFree(v48);
        *(_QWORD *)(a1 + 240) = v47;
        *(_QWORD *)(a1 + 256) = -1;
        *(_QWORD *)(a1 + 248) = -1;
      }
      v65 = 0;
      if ( CopyHookClsid < 0
        || (v61 = &v65,
            v62 = 0,
            v63 = 1,
            v8 |= 4u,
            v49 = 1,
            SHRegAllocData(hkey, 0, L"UserFirstName", 2, &v62, pvDatab) < 0) )
      {
        v49 = 0;
      }
      if ( (v8 & 4) != 0 )
      {
        v8 &= ~4u;
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v61);
      }
      if ( v49 )
      {
        v50 = v65;
        v65 = 0;
        v51 = *(void **)(a1 + 264);
        if ( v51 )
          CoTaskMemFree(v51);
        *(_QWORD *)(a1 + 264) = v50;
        *(_QWORD *)(a1 + 280) = -1;
        *(_QWORD *)(a1 + 272) = -1;
      }
      std::shared_ptr<WamAccountsCache>::operator=(a1 + 664, a4);
      CStorageProviderRootsCache::CalculateUserIdentity((CStorageProviderRootsCache *)a1);
      if ( CopyHookClsid >= 0 )
        CopyHookClsid = CStorageProviderRootsCache::InitializeIconOverlayHandlers(
                          (CStorageProviderRootsCache *)a1,
                          hkey);
      v64 = 0;
      if ( CopyHookClsid < 0
        || (v61 = &v64, v62 = 0, v63 = 1, v8 |= 8u, SHRegAllocData(hkey, 0, L"AUMID", 2, &v62, pvDatab) < 0) )
      {
        v42 = 0;
      }
      if ( (v8 & 8) != 0 )
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v61);
      if ( v42 )
      {
        v52 = v64;
        v64 = 0;
        v53 = *(void **)(a1 + 120);
        if ( v53 )
          CoTaskMemFree(v53);
        *(_QWORD *)(a1 + 120) = v52;
        *(_QWORD *)(a1 + 136) = -1;
        *(_QWORD *)(a1 + 128) = -1;
      }
      if ( CopyHookClsid >= 0 )
      {
        CopyHookClsid = CStorageProviderRootsCache::InitializeExplorerCommandVerbHandlers(
                          (CStorageProviderRootsCache *)a1,
                          hkey);
        if ( CopyHookClsid >= 0 )
        {
          if ( (a5 & 3) != 3
            || (CopyHookClsid = CStorageProviderRootsCache::GetHandlersFromStateRepoHelper((CStorageProviderRootsCache *)a1),
                CopyHookClsid >= 0) )
          {
            CopyHookClsid = CStorageProviderRootsCache::LoadCopyHookClsid((CStorageProviderRootsCache *)a1, hkey);
            if ( CopyHookClsid >= 0 )
              CopyHookClsid = CStorageProviderRootsCache::_InitializeUserRoots((CStorageProviderRootsCache *)a1, hkey);
          }
        }
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v64);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v66);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v67);
      goto LABEL_140;
    }
    pcbData = 78;
    v20 = RegGetValueW(hkey, 0, L"CustomStateHandler", 2u, 0, v68, &pcbData);
    v21 = v20 < 0;
    if ( v20 )
    {
      v68[0] = 0;
      if ( v20 > 0 )
        v21 = 1;
    }
    if ( !v21 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 368) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v22 = RegGetValueW(hkey, 0, L"ThumbnailProvider", 2u, 0, v68, &pcbData);
    v23 = v22 < 0;
    if ( v22 )
    {
      v68[0] = 0;
      if ( v22 > 0 )
        v23 = 1;
    }
    if ( !v23 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 384) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v24 = RegGetValueW(hkey, 0, L"ExtendedPropertiesHandler", 2u, 0, v68, &pcbData);
    v25 = v24 < 0;
    if ( v24 )
    {
      v68[0] = 0;
      if ( v24 > 0 )
        v25 = 1;
    }
    if ( !v25 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 400) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v26 = RegGetValueW(hkey, 0, L"UriHandler", 2u, 0, v68, &pcbData);
    v27 = v26 < 0;
    if ( v26 )
    {
      v68[0] = 0;
      if ( v26 > 0 )
        v27 = 1;
    }
    if ( !v27 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 416) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v28 = RegGetValueW(hkey, 0, L"HandlerFactory", 2u, 0, v68, &pcbData);
    v29 = v28 < 0;
    if ( v28 )
    {
      v68[0] = 0;
      if ( v28 > 0 )
        v29 = 1;
    }
    if ( !v29 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 448) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v30 = RegGetValueW(hkey, 0, L"StorageProviderStatusUISourceFactory", 2u, 0, v68, &pcbData);
    v31 = v30 < 0;
    if ( v30 )
    {
      v68[0] = 0;
      if ( v30 > 0 )
        v31 = 1;
    }
    if ( !v31 )
    {
      if ( !(unsigned int)GUIDFromStringW(v68, a1 + 464) )
        goto LABEL_87;
      CopyHookClsid = 0;
    }
    pcbData = 78;
    v32 = RegGetValueW(hkey, 0, L"NamespaceCLSID", 2u, 0, v68, &pcbData);
    v33 = v32 < 0;
    if ( v32 )
    {
      v68[0] = 0;
      if ( v32 > 0 )
        v33 = 1;
    }
    if ( v33 )
      goto LABEL_67;
    if ( (unsigned int)GUIDFromStringW(v68, a1 + 432) )
    {
      CopyHookClsid = 0;
LABEL_67:
      pcbData = 78;
      v34 = RegGetValueW(hkey, 0, L"ShareHandler", 2u, 0, v68, &pcbData);
      v35 = v34 < 0;
      if ( v34 )
      {
        v68[0] = 0;
        if ( v34 > 0 )
          v35 = 1;
      }
      if ( !v35 )
        CopyHookClsid = (unsigned int)GUIDFromStringW(v68, a1 + 496) == 0 ? 0x8007065E : 0;
      goto LABEL_72;
    }
LABEL_87:
    CopyHookClsid = -2147023266;
    goto LABEL_72;
  }
LABEL_141:
  v54 = *(std::_Ref_count_base **)(a4 + 8);
  if ( v54 )
    std::_Ref_count_base::_Decref(v54);
  return (unsigned int)CopyHookClsid;
}

```

## disassembly

```asm
0x180016fe8  push    rbp
0x180016fea  push    rbx
0x180016feb  push    rsi
0x180016fec  push    rdi
0x180016fed  push    r12
0x180016fef  push    r13
0x180016ff1  push    r14
0x180016ff3  push    r15
0x180016ff5  lea     rbp, [rsp-10B8h]
0x180016ffd  mov     eax, 11B8h
0x180017002  call    _alloca_probe
0x180017007  sub     rsp, rax
0x18001700a  mov     rax, cs:__security_cookie
0x180017011  xor     rax, rsp
0x180017014  mov     [rbp+10F0h+var_50], rax
0x18001701b  mov     r13, r9
0x18001701e  mov     rsi, r8
0x180017021  mov     rax, rdx
0x180017024  mov     rdi, rcx
0x180017027  mov     [rbp+10F0h+var_1168], r9
0x18001702b  xor     r12d, r12d
0x18001702e  mov     r15d, r12d
0x180017031  mov     [rsp+11F0h+var_11B0], r12d
0x180017036  mov     [rsp+11F0h+hkey], r12
0x18001703b  lea     rcx, [rsp+11F0h+hkey]
0x180017040  mov     [rsp+11F0h+phkResult], rcx; phkResult
0x180017045  mov     r9d, 20119h; samDesired
0x18001704b  xor     r8d, r8d; ulOptions
0x18001704e  mov     rdx, rsi; lpSubKey
0x180017051  mov     rcx, rax; hKey
0x180017054  call    cs:__imp_RegOpenKeyExW
0x18001705a  mov     ebx, eax
0x18001705c  mov     r14d, 80070000h
0x180017062  test    eax, eax
0x180017064  jle     short loc_18001706C
0x180017066  movzx   ebx, ax
0x180017069  or      ebx, r14d
0x18001706c  test    ebx, ebx
0x18001706e  js      loc_180017A5F
0x180017074  mov     rcx, rdi
0x180017077  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001707c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017080  mov     [rdi+8], rax
0x180017084  mov     [rdi+10h], rax
0x180017088  mov     r9, rdi
0x18001708b  mov     r8, rsi
0x18001708e  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180017093  mov     ebx, eax
0x180017095  test    eax, eax
0x180017097  js      loc_180017A53
0x18001709d  lea     rbx, [rdi+18h]
0x1800170a1  mov     rcx, rbx
0x1800170a4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800170a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800170ad  mov     [rbx+8], rax
0x1800170b1  mov     [rbx+10h], rax
0x1800170b5  mov     [rsp+11F0h+phkResult], rbx; void **
0x1800170ba  mov     esi, 10000006h
0x1800170bf  mov     r9d, esi; int
0x1800170c2  lea     r8, aDisplaynameres; "DisplayNameResource"
0x1800170c9  xor     edx, edx; unsigned __int16 *
0x1800170cb  mov     rcx, [rsp+11F0h+hkey]; HKEY
0x1800170d0  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800170d5  mov     ebx, eax
0x1800170d7  test    eax, eax
0x1800170d9  js      loc_180017A53
0x1800170df  lea     rbx, [rdi+30h]
0x1800170e3  mov     rcx, rbx
0x1800170e6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800170eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800170ef  mov     [rbx+8], rax
0x1800170f3  mov     [rbx+10h], rax
0x1800170f7  mov     [rsp+11F0h+phkResult], rbx; void **
0x1800170fc  mov     r9d, esi; int
0x1800170ff  lea     r8, aIconresource; "IconResource"
0x180017106  xor     edx, edx; unsigned __int16 *
0x180017108  mov     rcx, [rsp+11F0h+hkey]; HKEY
0x18001710d  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180017112  mov     ebx, eax
0x180017114  test    eax, eax
0x180017116  js      loc_180017A53
0x18001711c  lea     r9, [rdi+220h]; unsigned int *
0x180017123  mov     rcx, [rsp+11F0h+hkey]; HKEY
0x180017128  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001712d  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x180017135  lea     rax, [rsp+11F0h+var_11B0]
0x18001713a  mov     [rsp+11F0h+pcbData], rax; pcbData
0x18001713f  lea     rax, [rbp+10F0h+var_1160]
0x180017143  mov     [rsp+11F0h+pvData], rax; pvData
0x180017148  mov     [rsp+11F0h+phkResult], r12; pdwType
0x18001714d  mov     r9d, 2; dwFlags
0x180017153  lea     r8, Value; "Handler"
0x18001715a  xor     edx, edx; lpSubKey
0x18001715c  mov     rcx, [rsp+11F0h+hkey]; hkey
0x180017161  call    cs:__imp_RegGetValueW
0x180017167  test    eax, eax
0x180017169  jz      short loc_180017178
0x18001716b  mov     [rbp+10F0h+var_1160], r12w
0x180017170  jle     short loc_180017178
0x180017172  movzx   eax, ax
0x180017175  or      eax, r14d
0x180017178  mov     esi, 8007065Eh
0x18001717d  test    eax, eax
0x18001717f  js      short loc_18001719D
0x180017181  lea     rdx, [rdi+150h]
0x180017188  lea     rcx, [rbp+10F0h+var_1160]
0x18001718c  call    cs:__imp_GUIDFromStringW
0x180017192  test    eax, eax
0x180017194  jz      loc_1800176D8
0x18001719a  mov     ebx, r12d
0x18001719d  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x1800171a5  lea     rax, [rsp+11F0h+var_11B0]
0x1800171aa  mov     [rsp+11F0h+pcbData], rax; pcbData
0x1800171af  lea     rax, [rbp+10F0h+var_1160]
0x1800171b3  mov     [rsp+11F0h+pvData], rax; pvData
0x1800171b8  mov     [rsp+11F0h+phkResult], r12; pdwType
0x1800171bd  mov     r9d, 2; dwFlags
0x1800171c3  lea     r8, aBannernotifica; "BannerNotificationHandler"
0x1800171ca  xor     edx, edx; lpSubKey
0x1800171cc  mov     rcx, [rsp+11F0h+hkey]; hkey
0x1800171d1  call    cs:__imp_RegGetValueW
0x1800171d7  test    eax, eax
0x1800171d9  jz      short loc_1800171EA
0x1800171db  mov     [rbp+10F0h+var_1160], r12w
0x1800171e0  jle     short loc_1800171EA
0x1800171e2  movzx   eax, ax
0x1800171e5  or      eax, r14d
0x1800171e8  test    eax, eax
0x1800171ea  js      short loc_18001720A
0x1800171ec  lea     rdx, [rdi+160h]
0x1800171f3  lea     rcx, [rbp+10F0h+var_1160]
0x1800171f7  call    cs:__imp_GUIDFromStringW
0x1800171fd  test    eax, eax
0x1800171ff  jz      loc_1800176D8
0x180017205  mov     ebx, r12d
0x180017208  jmp     short loc_180017212
0x18001720a  test    ebx, ebx
0x18001720c  js      loc_1800175DB
0x180017212  mov     [rsp+11F0h+var_11B0], 64h ; 'd'
0x18001721a  lea     rax, [rsp+11F0h+var_11B0]
0x18001721f  mov     [rsp+11F0h+pcbData], rax; pcbData
0x180017224  lea     rax, [rbp+10F0h+var_1110]
0x180017228  mov     [rsp+11F0h+pvData], rax; pvData
0x18001722d  mov     [rsp+11F0h+phkResult], r12; pdwType
0x180017232  mov     r9d, 2; dwFlags
0x180017238  lea     r8, aProtectionmode; "ProtectionMode"
0x18001723f  xor     edx, edx; lpSubKey
0x180017241  mov     rcx, [rsp+11F0h+hkey]; hkey
0x180017246  call    cs:__imp_RegGetValueW
0x18001724c  test    eax, eax
0x18001724e  jz      short loc_18001725F
0x180017250  mov     [rbp+10F0h+var_1110], r12w
0x180017255  jle     short loc_18001725F
0x180017257  movzx   eax, ax
0x18001725a  or      eax, r14d
0x18001725d  test    eax, eax
0x18001725f  js      short loc_180017274
0x180017261  lea     rcx, [rdi+48h]
0x180017265  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017269  lea     rdx, [rbp+10F0h+var_1110]
0x18001726d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180017272  mov     ebx, eax
0x180017274  test    ebx, ebx
0x180017276  js      loc_1800175DB
0x18001727c  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x180017284  lea     rax, [rsp+11F0h+var_11B0]
0x180017289  mov     [rsp+11F0h+pcbData], rax; pcbData
0x18001728e  lea     rax, [rbp+10F0h+var_1160]
0x180017292  mov     [rsp+11F0h+pvData], rax; pvData
0x180017297  mov     [rsp+11F0h+phkResult], r12; pdwType
0x18001729c  mov     r9d, 2; dwFlags
0x1800172a2  lea     r8, aCustomstatehan; "CustomStateHandler"
0x1800172a9  xor     edx, edx; lpSubKey
0x1800172ab  mov     rcx, [rsp+11F0h+hkey]; hkey
0x1800172b0  call    cs:__imp_RegGetValueW
0x1800172b6  test    eax, eax
0x1800172b8  jz      short loc_1800172C9
0x1800172ba  mov     [rbp+10F0h+var_1160], r12w
0x1800172bf  jle     short loc_1800172C9
0x1800172c1  movzx   eax, ax
0x1800172c4  or      eax, r14d
0x1800172c7  test    eax, eax
0x1800172c9  js      short loc_1800172E7
0x1800172cb  lea     rdx, [rdi+170h]
0x1800172d2  lea     rcx, [rbp+10F0h+var_1160]
0x1800172d6  call    cs:__imp_GUIDFromStringW
0x1800172dc  test    eax, eax
0x1800172de  jz      loc_1800176D8
0x1800172e4  mov     ebx, r12d
0x1800172e7  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x1800172ef  lea     rax, [rsp+11F0h+var_11B0]
0x1800172f4  mov     [rsp+11F0h+pcbData], rax; pcbData
0x1800172f9  lea     rax, [rbp+10F0h+var_1160]
0x1800172fd  mov     [rsp+11F0h+pvData], rax; pvData
0x180017302  mov     [rsp+11F0h+phkResult], r12; pdwType
0x180017307  mov     r9d, 2; dwFlags
0x18001730d  lea     r8, aThumbnailprovi; "ThumbnailProvider"
0x180017314  xor     edx, edx; lpSubKey
0x180017316  mov     rcx, [rsp+11F0h+hkey]; hkey
0x18001731b  call    cs:__imp_RegGetValueW
0x180017321  test    eax, eax
0x180017323  jz      short loc_180017334
0x180017325  mov     [rbp+10F0h+var_1160], r12w
0x18001732a  jle     short loc_180017334
0x18001732c  movzx   eax, ax
0x18001732f  or      eax, r14d
0x180017332  test    eax, eax
0x180017334  js      short loc_180017354
0x180017336  lea     rdx, [rdi+180h]
0x18001733d  lea     rcx, [rbp+10F0h+var_1160]
0x180017341  call    cs:__imp_GUIDFromStringW
0x180017347  test    eax, eax
0x180017349  jz      loc_1800176D8
0x18001734f  mov     ebx, r12d
0x180017352  jmp     short loc_18001735C
0x180017354  test    ebx, ebx
0x180017356  js      loc_1800175DB
0x18001735c  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x180017364  lea     rax, [rsp+11F0h+var_11B0]
0x180017369  mov     [rsp+11F0h+pcbData], rax; pcbData
0x18001736e  lea     rax, [rbp+10F0h+var_1160]
0x180017372  mov     [rsp+11F0h+pvData], rax; pvData
0x180017377  mov     [rsp+11F0h+phkResult], r12; pdwType
0x18001737c  mov     r9d, 2; dwFlags
0x180017382  lea     r8, aExtendedproper; "ExtendedPropertiesHandler"
0x180017389  xor     edx, edx; lpSubKey
0x18001738b  mov     rcx, [rsp+11F0h+hkey]; hkey
0x180017390  call    cs:__imp_RegGetValueW
0x180017396  test    eax, eax
0x180017398  jz      short loc_1800173A9
0x18001739a  mov     [rbp+10F0h+var_1160], r12w
0x18001739f  jle     short loc_1800173A9
0x1800173a1  movzx   eax, ax
0x1800173a4  or      eax, r14d
0x1800173a7  test    eax, eax
0x1800173a9  js      short loc_1800173C7
0x1800173ab  lea     rdx, [rdi+190h]
0x1800173b2  lea     rcx, [rbp+10F0h+var_1160]
0x1800173b6  call    cs:__imp_GUIDFromStringW
0x1800173bc  test    eax, eax
0x1800173be  jz      loc_1800176D8
0x1800173c4  mov     ebx, r12d
0x1800173c7  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x1800173cf  lea     rax, [rsp+11F0h+var_11B0]
0x1800173d4  mov     [rsp+11F0h+pcbData], rax; pcbData
0x1800173d9  lea     rax, [rbp+10F0h+var_1160]
0x1800173dd  mov     [rsp+11F0h+pvData], rax; pvData
0x1800173e2  mov     [rsp+11F0h+phkResult], r12; pdwType
0x1800173e7  mov     r9d, 2; dwFlags
0x1800173ed  lea     r8, aUrihandler; "UriHandler"
0x1800173f4  xor     edx, edx; lpSubKey
0x1800173f6  mov     rcx, [rsp+11F0h+hkey]; hkey
0x1800173fb  call    cs:__imp_RegGetValueW
0x180017401  test    eax, eax
0x180017403  jz      short loc_180017414
0x180017405  mov     [rbp+10F0h+var_1160], r12w
0x18001740a  jle     short loc_180017414
0x18001740c  movzx   eax, ax
0x18001740f  or      eax, r14d
0x180017412  test    eax, eax
0x180017414  js      short loc_180017432
0x180017416  lea     rdx, [rdi+1A0h]
0x18001741d  lea     rcx, [rbp+10F0h+var_1160]
0x180017421  call    cs:__imp_GUIDFromStringW
0x180017427  test    eax, eax
0x180017429  jz      loc_1800176D8
0x18001742f  mov     ebx, r12d
0x180017432  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x18001743a  lea     rax, [rsp+11F0h+var_11B0]
0x18001743f  mov     [rsp+11F0h+pcbData], rax; pcbData
0x180017444  lea     rax, [rbp+10F0h+var_1160]
0x180017448  mov     [rsp+11F0h+pvData], rax; pvData
0x18001744d  mov     [rsp+11F0h+phkResult], r12; pdwType
0x180017452  mov     r9d, 2; dwFlags
0x180017458  lea     r8, aHandlerfactory; "HandlerFactory"
0x18001745f  xor     edx, edx; lpSubKey
0x180017461  mov     rcx, [rsp+11F0h+hkey]; hkey
0x180017466  call    cs:__imp_RegGetValueW
0x18001746c  test    eax, eax
0x18001746e  jz      short loc_18001747F
0x180017470  mov     [rbp+10F0h+var_1160], r12w
0x180017475  jle     short loc_18001747F
0x180017477  movzx   eax, ax
0x18001747a  or      eax, r14d
0x18001747d  test    eax, eax
0x18001747f  js      short loc_18001749D
0x180017481  lea     rdx, [rdi+1C0h]
0x180017488  lea     rcx, [rbp+10F0h+var_1160]
0x18001748c  call    cs:__imp_GUIDFromStringW
0x180017492  test    eax, eax
0x180017494  jz      loc_1800176D8
0x18001749a  mov     ebx, r12d
0x18001749d  mov     [rsp+11F0h+var_11B0], 4Eh ; 'N'
0x1800174a5  lea     rax, [rsp+11F0h+var_11B0]
0x1800174aa  mov     [rsp+11F0h+pcbData], rax; pcbData
0x1800174af  lea     rax, [rbp+10F0h+var_1160]
0x1800174b3  mov     [rsp+11F0h+pvData], rax; pvData
0x1800174b8  mov     [rsp+11F0h+phkResult], r12; pdwType
0x1800174bd  mov     r9d, 2; dwFlags
0x1800174c3  lea     r8, aStorageprovide_1; "StorageProviderStatusUISourceFactory"
  ... truncated ...
```
