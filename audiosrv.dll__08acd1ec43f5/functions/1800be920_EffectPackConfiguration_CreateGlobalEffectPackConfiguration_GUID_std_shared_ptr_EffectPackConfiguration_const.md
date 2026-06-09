# EffectPackConfiguration::CreateGlobalEffectPackConfiguration(_GUID,std::shared_ptr<EffectPackConfiguration const> &)

- ea: `0x1800be920`
- end: `0x1800bef9f`
- name: `?CreateGlobalEffectPackConfiguration@EffectPackConfiguration@@SAJU_GUID@@AEAV?$shared_ptr@$$CBUEffectPackConfiguration@@@std@@@Z`
- size: `1663`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801112bc`

## callees

- `0x18000ae1c`
- `0x18000cba0`
- `0x18000e284`
- `0x18001280c`
- `0x1800237e0`
- `0x180025e34`
- `0x18002a1ec`
- `0x18002addc`
- `0x180032600`
- `0x180042610`
- `0x18006a734`
- `0x1800be920`
- `0x1800befa8`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x18013a6c8`
- `0x18013a850`
- `0x18013a8f0`
- `0x18013aa8c`
- `0x18014d12c`
- `0x18016c010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800bee39`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800bee39`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800beb4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bebc6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bec04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800beb4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bebc6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bec04`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800beb98`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800beb98`

## string_xrefs

- `0x1800be986`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800be9d2`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800bea37`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800beaa7`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800beb33`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800bebaf`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800bec55`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800bed15`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800bed8e`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800bee6c`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800beeda`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall EffectPackConfiguration::CreateGlobalEffectPackConfiguration(struct _GUID *a1, __int64 a2)
{
  int EffectPackDevNodeId; // eax
  unsigned int v5; // ebx
  int EffectPackDevNodeRegistryRoot; // eax
  unsigned int v8; // ebx
  int EffectPackPropertyStore; // eax
  unsigned int v10; // ebx
  int EffectPackFxPropertyStore; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  HRESULT v15; // eax
  unsigned int v16; // ebx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbx
  int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // esi
  _DWORD *v22; // rax
  int Configuration; // eax
  int v24; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+20h] [rbp-98h]
  DEVINSTID_W pDeviceID; // [rsp+30h] [rbp-88h] BYREF
  HKEY phkDevice; // [rsp+38h] [rbp-80h] BYREF
  struct IPropertyStore *v28; // [rsp+40h] [rbp-78h] BYREF
  struct IPropertyStore *v29; // [rsp+48h] [rbp-70h] BYREF
  struct _GUID v30; // [rsp+50h] [rbp-68h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v32; // [rsp+70h] [rbp-48h]
  unsigned __int16 *v33; // [rsp+80h] [rbp-38h]
  GUID pclsid; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  pDeviceID = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pDeviceID,
    0);
  v30 = *a1;
  EffectPackDevNodeId = GetEffectPackDevNodeId(&v30, &pDeviceID);
  v5 = EffectPackDevNodeId;
  if ( EffectPackDevNodeId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x324,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)EffectPackDevNodeId,
      v24);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return v5;
  }
  phkDevice = 0;
  EffectPackDevNodeRegistryRoot = GetEffectPackDevNodeRegistryRoot(pDeviceID, &phkDevice);
  v8 = EffectPackDevNodeRegistryRoot;
  if ( EffectPackDevNodeRegistryRoot < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)EffectPackDevNodeRegistryRoot,
      v24);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return v8;
  }
  v28 = 0;
  v30 = *a1;
  EffectPackPropertyStore = GetEffectPackPropertyStore(phkDevice, &v30, &v28);
  v10 = EffectPackPropertyStore;
  if ( EffectPackPropertyStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)EffectPackPropertyStore,
      v24);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return v10;
  }
  v29 = 0;
  v30 = *a1;
  EffectPackFxPropertyStore = GetEffectPackFxPropertyStore(phkDevice, &v30, &v29);
  v12 = EffectPackFxPropertyStore;
  if ( EffectPackFxPropertyStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x360,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)EffectPackFxPropertyStore,
      v24);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return v12;
  }
  pclsid = 0;
  *(_OWORD *)pvar = 0;
  v32 = 0;
  v13 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v28->lpVtbl->GetValue)(
          v28,
          PKEY_FX_EffectPackSchema_Version,
          pvar);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x367,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)v13,
      v24);
    PropVariantClear(pvar);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return v14;
  }
  if ( LOWORD(pvar[0]) == 31 )
  {
    v15 = CLSIDFromString((LPCOLESTR)pvar[1], &pclsid);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36B,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
        (const char *)(unsigned int)v15,
        v24);
      PropVariantClear(pvar);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
      return v16;
    }
  }
  PropVariantClear(pvar);
  if ( memcmp_0(&PKEY_FX_EffectPack_Schema_V1, &pclsid, 0x10u)
    && memcmp_0(&PKEY_FX_EffectPack_Schema_Internal_V1, &pclsid, 0x10u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)0x80070057LL,
      v24);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return 2147942487LL;
  }
  v30 = 0;
  v17 = (unsigned __int16 *)operator new(0x818u);
  v18 = v17;
  v33 = v17;
  if ( v17 )
  {
    *(_OWORD *)v17 = 0;
    *((_DWORD *)v17 + 2) = 1;
    *((_DWORD *)v17 + 3) = 1;
    *(_QWORD *)v17 = &std::_Ref_count_obj2<EffectPackConfiguration>::`vftable';
    *(struct _GUID *)pvar = *a1;
    EffectPackConfiguration::EffectPackConfiguration((EffectPackConfiguration *)(v17 + 8), (struct _GUID *)pvar);
  }
  else
  {
    v18 = 0;
  }
  *(_QWORD *)&v30.Data1 = v18 + 8;
  *(_QWORD *)v30.Data4 = v18;
  if ( v18 == (unsigned __int16 *)-16LL )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x379,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)0x8007000ELL,
      v24);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)0xFFFFFFFFFFFFFFF0LL);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return 2147942414LL;
  }
  v19 = StringCchCopyW(v18 + 280, 0x100u, pDeviceID);
  v21 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37B,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)v19,
      v24);
    if ( v18 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v18);
LABEL_25:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return v21;
  }
  *((GUID *)v18 + 122) = pclsid;
  std::_Hash<std::_Umap_traits<_GUID,enum ValidEffectPackConfigurationSettings,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,enum ValidEffectPackConfigurationSettings>>,0>>::_Find_last<_GUID>(
    v20,
    pvar,
    &pclsid,
    *(unsigned int *)&pclsid.Data4[4]
  ^ *(unsigned int *)pclsid.Data4
  ^ *(unsigned int *)&pclsid.Data2
  ^ (unsigned __int64)pclsid.Data1);
  v22 = pvar[1];
  if ( !pvar[1] )
    std::_Xout_of_range("invalid unordered_map<K, T> key");
  Configuration = EffectPackConfiguration::ReadConfiguration((__int64)(v18 + 8), (__int64)v28, v29, 0, v22[8]);
  v21 = Configuration;
  if ( Configuration < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)(unsigned int)Configuration,
      v25);
    if ( v18 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v18);
    goto LABEL_25;
  }
  if ( EffectPackConfiguration::AposRegisteredAsSfxMfxEfx((EffectPackConfiguration *)(v18 + 8)) )
  {
    std::shared_ptr<std::function<void (void)>>::operator=(a2, &v30);
    if ( *(_QWORD *)v30.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v30.Data4);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
      (const char *)0x80004005LL,
      v25);
    if ( v18 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v18);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDevice);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDeviceID);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1800be920  mov     [rsp+arg_10], rbx
0x1800be925  push    rsi
0x1800be926  push    rdi
0x1800be927  push    r14
0x1800be929  sub     rsp, 0A0h
0x1800be930  mov     rax, cs:__security_cookie
0x1800be937  xor     rax, rsp
0x1800be93a  mov     [rsp+0B8h+var_20], rax
0x1800be942  mov     r14, rdx
0x1800be945  mov     rdi, rcx
0x1800be948  mov     [rsp+0B8h+pDeviceID], 0
0x1800be951  xor     edx, edx
0x1800be953  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800be958  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800be95d  movaps  xmm0, xmmword ptr [rdi]
0x1800be960  movdqa  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800be966  lea     rdx, [rsp+0B8h+pDeviceID]; unsigned __int16 **
0x1800be96b  lea     rcx, [rsp+0B8h+var_68]; struct _GUID
0x1800be970  call    ?GetEffectPackDevNodeId@@YAJU_GUID@@PEAPEAG@Z; GetEffectPackDevNodeId(_GUID,ushort * *)
0x1800be975  mov     ebx, eax
0x1800be977  test    eax, eax
0x1800be979  jns     short loc_1800BE9A9
0x1800be97b  mov     rcx, [rsp+0B8h]; this
0x1800be983  mov     r9d, eax; char *
0x1800be986  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800be98d  mov     edx, 324h; void *
0x1800be992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be997  nop
0x1800be998  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800be99d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800be9a2  mov     eax, ebx
0x1800be9a4  jmp     loc_1800BEF7A
0x1800be9a9  mov     [rsp+0B8h+phkDevice], 0
0x1800be9b2  lea     rdx, [rsp+0B8h+phkDevice]; phkDevice
0x1800be9b7  mov     rcx, [rsp+0B8h+pDeviceID]; pDeviceID
0x1800be9bc  call    ?GetEffectPackDevNodeRegistryRoot@@YAJPEBGPEAPEAUHKEY__@@@Z; GetEffectPackDevNodeRegistryRoot(ushort const *,HKEY__ * *)
0x1800be9c1  mov     ebx, eax
0x1800be9c3  test    eax, eax
0x1800be9c5  jns     short loc_1800BEA00
0x1800be9c7  mov     rcx, [rsp+0B8h]; this
0x1800be9cf  mov     r9d, eax; char *
0x1800be9d2  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800be9d9  mov     edx, 35Ah; void *
0x1800be9de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be9e3  nop
0x1800be9e4  lea     rcx, [rsp+0B8h+phkDevice]
0x1800be9e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800be9ee  nop
0x1800be9ef  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800be9f4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800be9f9  mov     eax, ebx
0x1800be9fb  jmp     loc_1800BEF7A
0x1800bea00  mov     [rsp+0B8h+var_78], 0
0x1800bea09  movaps  xmm0, xmmword ptr [rdi]
0x1800bea0c  movdqa  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800bea12  lea     r8, [rsp+0B8h+var_78]; struct IPropertyStore **
0x1800bea17  lea     rdx, [rsp+0B8h+var_68]; struct _GUID
0x1800bea1c  mov     rcx, [rsp+0B8h+phkDevice]; hKey
0x1800bea21  call    ?GetEffectPackPropertyStore@@YAJPEAUHKEY__@@U_GUID@@PEAPEAUIPropertyStore@@@Z; GetEffectPackPropertyStore(HKEY__ *,_GUID,IPropertyStore * *)
0x1800bea26  mov     ebx, eax
0x1800bea28  test    eax, eax
0x1800bea2a  jns     short loc_1800BEA70
0x1800bea2c  mov     rcx, [rsp+0B8h]; this
0x1800bea34  mov     r9d, eax; char *
0x1800bea37  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bea3e  mov     edx, 35Dh; void *
0x1800bea43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bea48  nop
0x1800bea49  lea     rcx, [rsp+0B8h+var_78]
0x1800bea4e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bea53  nop
0x1800bea54  lea     rcx, [rsp+0B8h+phkDevice]
0x1800bea59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bea5e  nop
0x1800bea5f  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800bea64  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bea69  mov     eax, ebx
0x1800bea6b  jmp     loc_1800BEF7A
0x1800bea70  mov     [rsp+0B8h+var_70], 0
0x1800bea79  movaps  xmm0, xmmword ptr [rdi]
0x1800bea7c  movdqa  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800bea82  lea     r8, [rsp+0B8h+var_70]; struct IPropertyStore **
0x1800bea87  lea     rdx, [rsp+0B8h+var_68]; struct _GUID
0x1800bea8c  mov     rcx, [rsp+0B8h+phkDevice]; hKey
0x1800bea91  call    ?GetEffectPackFxPropertyStore@@YAJPEAUHKEY__@@U_GUID@@PEAPEAUIPropertyStore@@@Z; GetEffectPackFxPropertyStore(HKEY__ *,_GUID,IPropertyStore * *)
0x1800bea96  mov     ebx, eax
0x1800bea98  test    eax, eax
0x1800bea9a  jns     short loc_1800BEAEB
0x1800bea9c  mov     rcx, [rsp+0B8h]; this
0x1800beaa4  mov     r9d, eax; char *
0x1800beaa7  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800beaae  mov     edx, 360h; void *
0x1800beab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beab8  nop
0x1800beab9  lea     rcx, [rsp+0B8h+var_70]
0x1800beabe  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800beac3  nop
0x1800beac4  lea     rcx, [rsp+0B8h+var_78]
0x1800beac9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800beace  nop
0x1800beacf  lea     rcx, [rsp+0B8h+phkDevice]
0x1800bead4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bead9  nop
0x1800beada  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800beadf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800beae4  mov     eax, ebx
0x1800beae6  jmp     loc_1800BEF7A
0x1800beaeb  xorps   xmm0, xmm0
0x1800beaee  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x1800beaf6  xorps   xmm1, xmm1
0x1800beaf9  xor     eax, eax
0x1800beafb  movups  xmmword ptr [rsp+0B8h+pvar], xmm1
0x1800beb00  mov     [rsp+0B8h+var_48], rax
0x1800beb05  mov     rcx, [rsp+0B8h+var_78]
0x1800beb0a  mov     rax, [rcx]
0x1800beb0d  lea     r8, [rsp+0B8h+pvar]
0x1800beb12  lea     rdx, PKEY_FX_EffectPackSchema_Version
0x1800beb19  mov     rax, [rax+28h]
0x1800beb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb22  mov     ebx, eax
0x1800beb24  test    eax, eax
0x1800beb26  jns     short loc_1800BEB83
0x1800beb28  mov     rcx, [rsp+0B8h]; this
0x1800beb30  mov     r9d, eax; char *
0x1800beb33  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800beb3a  mov     edx, 367h; void *
0x1800beb3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beb44  nop
0x1800beb45  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800beb4a  call    cs:__imp_PropVariantClear
0x1800beb50  nop
0x1800beb51  lea     rcx, [rsp+0B8h+var_70]
0x1800beb56  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800beb5b  nop
0x1800beb5c  lea     rcx, [rsp+0B8h+var_78]
0x1800beb61  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800beb66  nop
0x1800beb67  lea     rcx, [rsp+0B8h+phkDevice]
0x1800beb6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800beb71  nop
0x1800beb72  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800beb77  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800beb7c  mov     eax, ebx
0x1800beb7e  jmp     loc_1800BEF7A
0x1800beb83  cmp     word ptr [rsp+0B8h+pvar], 1Fh
0x1800beb89  jnz     short loc_1800BEBFF
0x1800beb8b  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x1800beb93  mov     rcx, [rsp+0B8h+pvar+8]; lpsz
0x1800beb98  call    cs:__imp_CLSIDFromString
0x1800beb9e  mov     ebx, eax
0x1800beba0  test    eax, eax
0x1800beba2  jns     short loc_1800BEBFF
0x1800beba4  mov     rcx, [rsp+0B8h]; this
0x1800bebac  mov     r9d, eax; char *
0x1800bebaf  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bebb6  mov     edx, 36Bh; void *
0x1800bebbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bebc0  nop
0x1800bebc1  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800bebc6  call    cs:__imp_PropVariantClear
0x1800bebcc  nop
0x1800bebcd  lea     rcx, [rsp+0B8h+var_70]
0x1800bebd2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bebd7  nop
0x1800bebd8  lea     rcx, [rsp+0B8h+var_78]
0x1800bebdd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bebe2  nop
0x1800bebe3  lea     rcx, [rsp+0B8h+phkDevice]
0x1800bebe8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bebed  nop
0x1800bebee  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800bebf3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bebf8  mov     eax, ebx
0x1800bebfa  jmp     loc_1800BEF7A
0x1800bebff  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800bec04  call    cs:__imp_PropVariantClear
0x1800bec0a  mov     ebx, 10h
0x1800bec0f  mov     r8d, ebx; Size
0x1800bec12  lea     rdx, [rsp+0B8h+pclsid]; Buf2
0x1800bec1a  lea     rcx, PKEY_FX_EffectPack_Schema_V1; Buf1
0x1800bec21  call    memcmp_0
0x1800bec26  test    eax, eax
0x1800bec28  jz      short loc_1800BEC99
0x1800bec2a  mov     r8d, ebx; Size
0x1800bec2d  lea     rdx, [rsp+0B8h+pclsid]; Buf2
0x1800bec35  lea     rcx, PKEY_FX_EffectPack_Schema_Internal_V1; Buf1
0x1800bec3c  call    memcmp_0
0x1800bec41  test    eax, eax
0x1800bec43  jz      short loc_1800BEC99
0x1800bec45  mov     rcx, [rsp+0B8h]; this
0x1800bec4d  mov     ebx, 80070057h
0x1800bec52  mov     r9d, ebx; char *
0x1800bec55  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bec5c  mov     edx, 373h; void *
0x1800bec61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bec66  nop
0x1800bec67  lea     rcx, [rsp+0B8h+var_70]
0x1800bec6c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bec71  nop
0x1800bec72  lea     rcx, [rsp+0B8h+var_78]
0x1800bec77  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bec7c  nop
0x1800bec7d  lea     rcx, [rsp+0B8h+phkDevice]
0x1800bec82  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bec87  nop
0x1800bec88  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800bec8d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bec92  mov     eax, ebx
0x1800bec94  jmp     loc_1800BEF7A
0x1800bec99  xorps   xmm0, xmm0
0x1800bec9c  movdqu  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800beca2  mov     ecx, 818h; unsigned __int64
0x1800beca7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800becac  mov     rbx, rax
0x1800becaf  mov     [rsp+0B8h+var_38], rax
0x1800becb7  test    rax, rax
0x1800becba  jz      short loc_1800BECF0
0x1800becbc  xorps   xmm0, xmm0
0x1800becbf  movups  xmmword ptr [rax], xmm0
0x1800becc2  mov     eax, 1
0x1800becc7  mov     [rbx+8], eax
0x1800becca  mov     [rbx+0Ch], eax
0x1800beccd  lea     rax, ??_7?$_Ref_count_obj2@UEffectPackConfiguration@@@std@@6B@; const std::_Ref_count_obj2<EffectPackConfiguration>::`vftable'
0x1800becd4  mov     [rbx], rax
0x1800becd7  movaps  xmm0, xmmword ptr [rdi]
0x1800becda  movdqa  xmmword ptr [rsp+0B8h+pvar], xmm0
0x1800bece0  lea     rcx, [rbx+10h]; this
0x1800bece4  lea     rdx, [rsp+0B8h+pvar]; struct _GUID
0x1800bece9  call    ??0EffectPackConfiguration@@QEAA@U_GUID@@@Z; EffectPackConfiguration::EffectPackConfiguration(_GUID)
0x1800becee  jmp     short loc_1800BECF2
0x1800becf0  xor     ebx, ebx
0x1800becf2  lea     rdi, [rbx+10h]
0x1800becf6  mov     qword ptr [rsp+0B8h+var_68.Data1], rdi
0x1800becfb  mov     qword ptr [rsp+0B8h+var_68.Data4], rbx
0x1800bed00  test    rdi, rdi
0x1800bed03  jnz     short loc_1800BED67
0x1800bed05  mov     rcx, [rsp+0B8h]; this
0x1800bed0d  mov     edi, 8007000Eh
0x1800bed12  mov     r9d, edi; char *
0x1800bed15  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bed1c  mov     edx, 379h; void *
0x1800bed21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bed26  nop
0x1800bed27  test    rbx, rbx
0x1800bed2a  jz      short loc_1800BED35
0x1800bed2c  mov     rcx, rbx; this
0x1800bed2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bed34  nop
0x1800bed35  lea     rcx, [rsp+0B8h+var_70]
0x1800bed3a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bed3f  nop
0x1800bed40  lea     rcx, [rsp+0B8h+var_78]
0x1800bed45  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bed4a  nop
0x1800bed4b  lea     rcx, [rsp+0B8h+phkDevice]
0x1800bed50  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bed55  nop
0x1800bed56  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800bed5b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bed60  mov     eax, edi
0x1800bed62  jmp     loc_1800BEF7A
0x1800bed67  lea     rcx, [rdi+220h]; unsigned __int16 *
0x1800bed6e  mov     r8, [rsp+0B8h+pDeviceID]; unsigned __int16 *
0x1800bed73  mov     edx, 100h; unsigned __int64
0x1800bed78  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bed7d  mov     esi, eax
0x1800bed7f  test    eax, eax
0x1800bed81  jns     short loc_1800BEDE0
0x1800bed83  mov     rcx, [rsp+0B8h]; this
0x1800bed8b  mov     r9d, eax; char *
0x1800bed8e  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bed95  mov     edx, 37Bh; void *
0x1800bed9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bed9f  nop
0x1800beda0  test    rbx, rbx
0x1800beda3  jz      short loc_1800BEDAE
0x1800beda5  mov     rcx, rbx; this
0x1800beda8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bedad  nop
0x1800bedae  lea     rcx, [rsp+0B8h+var_70]
0x1800bedb3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bedb8  nop
0x1800bedb9  lea     rcx, [rsp+0B8h+var_78]
0x1800bedbe  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bedc3  nop
0x1800bedc4  lea     rcx, [rsp+0B8h+phkDevice]
0x1800bedc9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bedce  nop
0x1800bedcf  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800bedd4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bedd9  mov     eax, esi
0x1800beddb  jmp     loc_1800BEF7A
0x1800bede0  movups  xmm0, xmmword ptr [rsp+0B8h+pclsid.Data1]
0x1800bede8  movdqu  xmmword ptr [rdi+790h], xmm0
0x1800bedf0  mov     r9d, [rsp+0B8h+pclsid.Data1]
0x1800bedf8  mov     eax, dword ptr [rsp+0B8h+pclsid.Data2]
0x1800bedff  xor     r9, rax
0x1800bee02  mov     eax, dword ptr [rsp+0B8h+pclsid.Data4]
0x1800bee09  xor     r9, rax
0x1800bee0c  mov     eax, dword ptr [rsp+0B8h+pclsid.Data4+4]
  ... truncated ...
```
