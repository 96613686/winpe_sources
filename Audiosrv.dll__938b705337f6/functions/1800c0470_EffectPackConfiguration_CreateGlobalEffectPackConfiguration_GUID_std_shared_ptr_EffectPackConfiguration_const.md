# EffectPackConfiguration::CreateGlobalEffectPackConfiguration(_GUID,std::shared_ptr<EffectPackConfiguration const> &)

- ea: `0x1800c0470`
- end: `0x1800c0aef`
- name: `?CreateGlobalEffectPackConfiguration@EffectPackConfiguration@@SAJU_GUID@@AEAV?$shared_ptr@$$CBUEffectPackConfiguration@@@std@@@Z`
- size: `1663`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18011100c`

## callees

- `0x18000accc`
- `0x18000ca50`
- `0x18000e134`
- `0x1800126bc`
- `0x180023690`
- `0x180025ce4`
- `0x18002a08c`
- `0x18002ac7c`
- `0x1800324a0`
- `0x180042aa0`
- `0x18006abc4`
- `0x1800c0470`
- `0x1800c0af8`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x18013a438`
- `0x18013a5c0`
- `0x18013a660`
- `0x18013a7fc`
- `0x18014c41c`
- `0x18016b010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800c0989`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800c0989`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c069a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c0716`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c0754`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c069a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c0716`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c0754`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c06e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c06e8`

## string_xrefs

- `0x1800c04d6`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c0522`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c0587`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c05f7`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c0683`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c06ff`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c07a5`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c0865`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c08de`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c09bc`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x1800c0a2a`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`

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
  v13 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, PROPVARIANT *))v28->lpVtbl->GetValue)(
          v28,
          &PKEY_FX_EffectPackSchema_Version,
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
0x1800c0470  mov     [rsp+arg_10], rbx
0x1800c0475  push    rsi
0x1800c0476  push    rdi
0x1800c0477  push    r14
0x1800c0479  sub     rsp, 0A0h
0x1800c0480  mov     rax, cs:__security_cookie
0x1800c0487  xor     rax, rsp
0x1800c048a  mov     [rsp+0B8h+var_20], rax
0x1800c0492  mov     r14, rdx
0x1800c0495  mov     rdi, rcx
0x1800c0498  mov     [rsp+0B8h+pDeviceID], 0
0x1800c04a1  xor     edx, edx
0x1800c04a3  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c04a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c04ad  movaps  xmm0, xmmword ptr [rdi]
0x1800c04b0  movdqa  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800c04b6  lea     rdx, [rsp+0B8h+pDeviceID]; unsigned __int16 **
0x1800c04bb  lea     rcx, [rsp+0B8h+var_68]; struct _GUID
0x1800c04c0  call    ?GetEffectPackDevNodeId@@YAJU_GUID@@PEAPEAG@Z; GetEffectPackDevNodeId(_GUID,ushort * *)
0x1800c04c5  mov     ebx, eax
0x1800c04c7  test    eax, eax
0x1800c04c9  jns     short loc_1800C04F9
0x1800c04cb  mov     rcx, [rsp+0B8h]; this
0x1800c04d3  mov     r9d, eax; char *
0x1800c04d6  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c04dd  mov     edx, 324h; void *
0x1800c04e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c04e7  nop
0x1800c04e8  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c04ed  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c04f2  mov     eax, ebx
0x1800c04f4  jmp     loc_1800C0ACA
0x1800c04f9  mov     [rsp+0B8h+phkDevice], 0
0x1800c0502  lea     rdx, [rsp+0B8h+phkDevice]; phkDevice
0x1800c0507  mov     rcx, [rsp+0B8h+pDeviceID]; pDeviceID
0x1800c050c  call    ?GetEffectPackDevNodeRegistryRoot@@YAJPEBGPEAPEAUHKEY__@@@Z; GetEffectPackDevNodeRegistryRoot(ushort const *,HKEY__ * *)
0x1800c0511  mov     ebx, eax
0x1800c0513  test    eax, eax
0x1800c0515  jns     short loc_1800C0550
0x1800c0517  mov     rcx, [rsp+0B8h]; this
0x1800c051f  mov     r9d, eax; char *
0x1800c0522  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c0529  mov     edx, 35Ah; void *
0x1800c052e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0533  nop
0x1800c0534  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c0539  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c053e  nop
0x1800c053f  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c0544  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c0549  mov     eax, ebx
0x1800c054b  jmp     loc_1800C0ACA
0x1800c0550  mov     [rsp+0B8h+var_78], 0
0x1800c0559  movaps  xmm0, xmmword ptr [rdi]
0x1800c055c  movdqa  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800c0562  lea     r8, [rsp+0B8h+var_78]; struct IPropertyStore **
0x1800c0567  lea     rdx, [rsp+0B8h+var_68]; struct _GUID
0x1800c056c  mov     rcx, [rsp+0B8h+phkDevice]; hKey
0x1800c0571  call    ?GetEffectPackPropertyStore@@YAJPEAUHKEY__@@U_GUID@@PEAPEAUIPropertyStore@@@Z; GetEffectPackPropertyStore(HKEY__ *,_GUID,IPropertyStore * *)
0x1800c0576  mov     ebx, eax
0x1800c0578  test    eax, eax
0x1800c057a  jns     short loc_1800C05C0
0x1800c057c  mov     rcx, [rsp+0B8h]; this
0x1800c0584  mov     r9d, eax; char *
0x1800c0587  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c058e  mov     edx, 35Dh; void *
0x1800c0593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0598  nop
0x1800c0599  lea     rcx, [rsp+0B8h+var_78]
0x1800c059e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c05a3  nop
0x1800c05a4  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c05a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c05ae  nop
0x1800c05af  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c05b4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c05b9  mov     eax, ebx
0x1800c05bb  jmp     loc_1800C0ACA
0x1800c05c0  mov     [rsp+0B8h+var_70], 0
0x1800c05c9  movaps  xmm0, xmmword ptr [rdi]
0x1800c05cc  movdqa  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800c05d2  lea     r8, [rsp+0B8h+var_70]; struct IPropertyStore **
0x1800c05d7  lea     rdx, [rsp+0B8h+var_68]; struct _GUID
0x1800c05dc  mov     rcx, [rsp+0B8h+phkDevice]; hKey
0x1800c05e1  call    ?GetEffectPackFxPropertyStore@@YAJPEAUHKEY__@@U_GUID@@PEAPEAUIPropertyStore@@@Z; GetEffectPackFxPropertyStore(HKEY__ *,_GUID,IPropertyStore * *)
0x1800c05e6  mov     ebx, eax
0x1800c05e8  test    eax, eax
0x1800c05ea  jns     short loc_1800C063B
0x1800c05ec  mov     rcx, [rsp+0B8h]; this
0x1800c05f4  mov     r9d, eax; char *
0x1800c05f7  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c05fe  mov     edx, 360h; void *
0x1800c0603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0608  nop
0x1800c0609  lea     rcx, [rsp+0B8h+var_70]
0x1800c060e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c0613  nop
0x1800c0614  lea     rcx, [rsp+0B8h+var_78]
0x1800c0619  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c061e  nop
0x1800c061f  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c0624  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c0629  nop
0x1800c062a  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c062f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c0634  mov     eax, ebx
0x1800c0636  jmp     loc_1800C0ACA
0x1800c063b  xorps   xmm0, xmm0
0x1800c063e  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x1800c0646  xorps   xmm1, xmm1
0x1800c0649  xor     eax, eax
0x1800c064b  movups  xmmword ptr [rsp+0B8h+pvar], xmm1
0x1800c0650  mov     [rsp+0B8h+var_48], rax
0x1800c0655  mov     rcx, [rsp+0B8h+var_78]
0x1800c065a  mov     rax, [rcx]
0x1800c065d  lea     r8, [rsp+0B8h+pvar]
0x1800c0662  lea     rdx, PKEY_FX_EffectPackSchema_Version
0x1800c0669  mov     rax, [rax+28h]
0x1800c066d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0672  mov     ebx, eax
0x1800c0674  test    eax, eax
0x1800c0676  jns     short loc_1800C06D3
0x1800c0678  mov     rcx, [rsp+0B8h]; this
0x1800c0680  mov     r9d, eax; char *
0x1800c0683  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c068a  mov     edx, 367h; void *
0x1800c068f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0694  nop
0x1800c0695  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800c069a  call    cs:__imp_PropVariantClear
0x1800c06a0  nop
0x1800c06a1  lea     rcx, [rsp+0B8h+var_70]
0x1800c06a6  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c06ab  nop
0x1800c06ac  lea     rcx, [rsp+0B8h+var_78]
0x1800c06b1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c06b6  nop
0x1800c06b7  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c06bc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c06c1  nop
0x1800c06c2  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c06c7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c06cc  mov     eax, ebx
0x1800c06ce  jmp     loc_1800C0ACA
0x1800c06d3  cmp     word ptr [rsp+0B8h+pvar], 1Fh
0x1800c06d9  jnz     short loc_1800C074F
0x1800c06db  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x1800c06e3  mov     rcx, [rsp+0B8h+pvar+8]; lpsz
0x1800c06e8  call    cs:__imp_CLSIDFromString
0x1800c06ee  mov     ebx, eax
0x1800c06f0  test    eax, eax
0x1800c06f2  jns     short loc_1800C074F
0x1800c06f4  mov     rcx, [rsp+0B8h]; this
0x1800c06fc  mov     r9d, eax; char *
0x1800c06ff  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c0706  mov     edx, 36Bh; void *
0x1800c070b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0710  nop
0x1800c0711  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800c0716  call    cs:__imp_PropVariantClear
0x1800c071c  nop
0x1800c071d  lea     rcx, [rsp+0B8h+var_70]
0x1800c0722  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c0727  nop
0x1800c0728  lea     rcx, [rsp+0B8h+var_78]
0x1800c072d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c0732  nop
0x1800c0733  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c0738  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c073d  nop
0x1800c073e  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c0743  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c0748  mov     eax, ebx
0x1800c074a  jmp     loc_1800C0ACA
0x1800c074f  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800c0754  call    cs:__imp_PropVariantClear
0x1800c075a  mov     ebx, 10h
0x1800c075f  mov     r8d, ebx; Size
0x1800c0762  lea     rdx, [rsp+0B8h+pclsid]; Buf2
0x1800c076a  lea     rcx, PKEY_FX_EffectPack_Schema_V1; Buf1
0x1800c0771  call    memcmp_0
0x1800c0776  test    eax, eax
0x1800c0778  jz      short loc_1800C07E9
0x1800c077a  mov     r8d, ebx; Size
0x1800c077d  lea     rdx, [rsp+0B8h+pclsid]; Buf2
0x1800c0785  lea     rcx, PKEY_FX_EffectPack_Schema_Internal_V1; Buf1
0x1800c078c  call    memcmp_0
0x1800c0791  test    eax, eax
0x1800c0793  jz      short loc_1800C07E9
0x1800c0795  mov     rcx, [rsp+0B8h]; this
0x1800c079d  mov     ebx, 80070057h
0x1800c07a2  mov     r9d, ebx; char *
0x1800c07a5  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c07ac  mov     edx, 373h; void *
0x1800c07b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c07b6  nop
0x1800c07b7  lea     rcx, [rsp+0B8h+var_70]
0x1800c07bc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c07c1  nop
0x1800c07c2  lea     rcx, [rsp+0B8h+var_78]
0x1800c07c7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c07cc  nop
0x1800c07cd  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c07d2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c07d7  nop
0x1800c07d8  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c07dd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c07e2  mov     eax, ebx
0x1800c07e4  jmp     loc_1800C0ACA
0x1800c07e9  xorps   xmm0, xmm0
0x1800c07ec  movdqu  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x1800c07f2  mov     ecx, 818h; unsigned __int64
0x1800c07f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c07fc  mov     rbx, rax
0x1800c07ff  mov     [rsp+0B8h+var_38], rax
0x1800c0807  test    rax, rax
0x1800c080a  jz      short loc_1800C0840
0x1800c080c  xorps   xmm0, xmm0
0x1800c080f  movups  xmmword ptr [rax], xmm0
0x1800c0812  mov     eax, 1
0x1800c0817  mov     [rbx+8], eax
0x1800c081a  mov     [rbx+0Ch], eax
0x1800c081d  lea     rax, ??_7?$_Ref_count_obj2@UEffectPackConfiguration@@@std@@6B@; const std::_Ref_count_obj2<EffectPackConfiguration>::`vftable'
0x1800c0824  mov     [rbx], rax
0x1800c0827  movaps  xmm0, xmmword ptr [rdi]
0x1800c082a  movdqa  xmmword ptr [rsp+0B8h+pvar], xmm0
0x1800c0830  lea     rcx, [rbx+10h]; this
0x1800c0834  lea     rdx, [rsp+0B8h+pvar]; struct _GUID
0x1800c0839  call    ??0EffectPackConfiguration@@QEAA@U_GUID@@@Z; EffectPackConfiguration::EffectPackConfiguration(_GUID)
0x1800c083e  jmp     short loc_1800C0842
0x1800c0840  xor     ebx, ebx
0x1800c0842  lea     rdi, [rbx+10h]
0x1800c0846  mov     qword ptr [rsp+0B8h+var_68.Data1], rdi
0x1800c084b  mov     qword ptr [rsp+0B8h+var_68.Data4], rbx
0x1800c0850  test    rdi, rdi
0x1800c0853  jnz     short loc_1800C08B7
0x1800c0855  mov     rcx, [rsp+0B8h]; this
0x1800c085d  mov     edi, 8007000Eh
0x1800c0862  mov     r9d, edi; char *
0x1800c0865  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c086c  mov     edx, 379h; void *
0x1800c0871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0876  nop
0x1800c0877  test    rbx, rbx
0x1800c087a  jz      short loc_1800C0885
0x1800c087c  mov     rcx, rbx; this
0x1800c087f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c0884  nop
0x1800c0885  lea     rcx, [rsp+0B8h+var_70]
0x1800c088a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c088f  nop
0x1800c0890  lea     rcx, [rsp+0B8h+var_78]
0x1800c0895  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c089a  nop
0x1800c089b  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c08a0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c08a5  nop
0x1800c08a6  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c08ab  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c08b0  mov     eax, edi
0x1800c08b2  jmp     loc_1800C0ACA
0x1800c08b7  lea     rcx, [rdi+220h]; unsigned __int16 *
0x1800c08be  mov     r8, [rsp+0B8h+pDeviceID]; unsigned __int16 *
0x1800c08c3  mov     edx, 100h; unsigned __int64
0x1800c08c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c08cd  mov     esi, eax
0x1800c08cf  test    eax, eax
0x1800c08d1  jns     short loc_1800C0930
0x1800c08d3  mov     rcx, [rsp+0B8h]; this
0x1800c08db  mov     r9d, eax; char *
0x1800c08de  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800c08e5  mov     edx, 37Bh; void *
0x1800c08ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c08ef  nop
0x1800c08f0  test    rbx, rbx
0x1800c08f3  jz      short loc_1800C08FE
0x1800c08f5  mov     rcx, rbx; this
0x1800c08f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c08fd  nop
0x1800c08fe  lea     rcx, [rsp+0B8h+var_70]
0x1800c0903  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c0908  nop
0x1800c0909  lea     rcx, [rsp+0B8h+var_78]
0x1800c090e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c0913  nop
0x1800c0914  lea     rcx, [rsp+0B8h+phkDevice]
0x1800c0919  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c091e  nop
0x1800c091f  lea     rcx, [rsp+0B8h+pDeviceID]
0x1800c0924  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c0929  mov     eax, esi
0x1800c092b  jmp     loc_1800C0ACA
0x1800c0930  movups  xmm0, xmmword ptr [rsp+0B8h+pclsid.Data1]
0x1800c0938  movdqu  xmmword ptr [rdi+790h], xmm0
0x1800c0940  mov     r9d, [rsp+0B8h+pclsid.Data1]
0x1800c0948  mov     eax, dword ptr [rsp+0B8h+pclsid.Data2]
0x1800c094f  xor     r9, rax
0x1800c0952  mov     eax, dword ptr [rsp+0B8h+pclsid.Data4]
0x1800c0959  xor     r9, rax
0x1800c095c  mov     eax, dword ptr [rsp+0B8h+pclsid.Data4+4]
  ... truncated ...
```
