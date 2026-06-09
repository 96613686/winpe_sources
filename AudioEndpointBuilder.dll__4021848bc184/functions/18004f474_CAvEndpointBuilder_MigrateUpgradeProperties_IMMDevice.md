# CAvEndpointBuilder::MigrateUpgradeProperties(IMMDevice *)

- ea: `0x18004f474`
- end: `0x180050042`
- name: `?MigrateUpgradeProperties@CAvEndpointBuilder@@AEAAJPEAUIMMDevice@@@Z`
- size: `3022`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *this, struct IMMDevice *)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a344`
- `0x180052ffc`

## callees

- `0x180006b0c`
- `0x18000f820`
- `0x18000fb60`
- `0x180010da8`
- `0x180012acc`
- `0x180012fd0`
- `0x180013144`
- `0x18001707c`
- `0x18001f374`
- `0x180021030`
- `0x1800231d8`
- `0x180023d28`
- `0x180023fbc`
- `0x180024ca0`
- `0x1800252a4`
- `0x180034c5c`
- `0x180034c84`
- `0x180035738`
- `0x1800366d8`
- `0x1800369a4`
- `0x18004958c`
- `0x18004f474`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004fc82`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004fc82`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f808`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f808`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f590`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f59b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fc95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fca0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fe75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fe80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fe8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fee7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fef2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ffb3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ffbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ffff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f590`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f59b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fc95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fca0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fe75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fe80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fe8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fee7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004fef2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ffb3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ffbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ffff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fbaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ff03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fbaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ff03`

## string_xrefs

- `0x18004f56d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004f9e3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004ff9b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004ffe7`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CAvEndpointBuilder::MigrateUpgradeProperties(CAvEndpointBuilder *this, struct IMMDevice *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rbx
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, LPVOID *); // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  LPVOID v15; // rcx
  unsigned int v16; // r14d
  unsigned int v17; // r15d
  __int64 v18; // rax
  int v19; // eax
  struct IMMEndpointInternal *v20; // rcx
  struct IMMDevice *v21; // rbx
  HRESULT (__stdcall *v22)(IMMDevice *, DWORD, IPropertyStore **); // rdi
  struct IPropertyStore *v23; // rcx
  struct IMMDeviceVtbl *lpVtbl; // rax
  int ConnectorIdFromSavedConnectedTo; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  __int64 v30; // rdi
  int (__fastcall *v31)(__int64, unsigned __int16 **); // rbx
  CAvEndpointBuilder *v32; // rcx
  CAvEndpointBuilder *v33; // rcx
  const struct _tlgProvider_t *v34; // rax
  const struct _tlgProvider_t *v35; // rax
  const struct _tlgProvider_t *v36; // rax
  int v37; // eax
  const struct _tlgProvider_t *v38; // rax
  struct IMMEndpointInternal *v39; // rbx
  void (__fastcall *v40)(struct IMMEndpointInternal *, _QWORD, __int64 **); // rdi
  __int64 *v41; // rcx
  __int64 v42; // rcx
  struct IMMEndpointInternal *v43; // rbx
  int (__fastcall *v44)(struct IMMEndpointInternal *, __int64, __int64 *); // rdi
  __int64 v45; // rcx
  CAvEndpointBuilder *v46; // rcx
  const struct _tlgProvider_t *v47; // rax
  __int64 v49; // rdx
  __int64 v50; // rdx
  int *ppv; // [rsp+20h] [rbp-E0h]
  struct IPropertyStore *v52; // [rsp+30h] [rbp-D0h] BYREF
  struct IPropertyStore *v53; // [rsp+38h] [rbp-C8h] BYREF
  struct IMMDevice *v54; // [rsp+40h] [rbp-C0h] BYREF
  struct IMMEndpointInternal *v55; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v56; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  int v61[2]; // [rsp+78h] [rbp-88h] BYREF
  PROPVARIANT v62[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h]
  PROPVARIANT v64[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h]
  PROPVARIANT pvar[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h]
  struct IMMEndpointInternal *v68; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v69; // [rsp+D0h] [rbp-30h] BYREF
  int v70; // [rsp+D8h] [rbp-28h] BYREF
  int v71; // [rsp+DCh] [rbp-24h] BYREF
  __int64 v72; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v74; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v75; // [rsp+F8h] [rbp-8h] BYREF
  PROPVARIANT v76[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v77; // [rsp+110h] [rbp+10h]
  PROPVARIANT v78[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v79; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  CAvEndpointBuilder *v81; // [rsp+170h] [rbp+70h] BYREF
  struct IMMDevice *v82; // [rsp+178h] [rbp+78h] BYREF
  __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v83; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v84; // [rsp+188h] [rbp+88h] BYREF

  v82 = a2;
  v81 = this;
  v84 = 0;
  v69 = 0;
  v74 = 0;
  v73 = 0;
  v68 = 0;
  v83 = eRender;
  v72 = 0;
  v75 = 0;
  pv = 0;
  v70 = 0;
  *(_OWORD *)v62 = 0;
  v63 = 0;
  *(_OWORD *)pvar = 0;
  v67 = 0;
  v53 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  v68 = 0;
  v3 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v82, &v68);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9282;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v3,
      (int)ppv);
    goto LABEL_10;
  }
  v3 = (*(__int64 (__fastcall **)(struct IMMEndpointInternal *, int *))(*(_QWORD *)v68 + 32LL))(v68, &v70);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9283;
    goto LABEL_9;
  }
  if ( (v70 & 0x20000000) != 0 )
    goto LABEL_116;
  v6 = v73;
  v73 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v3 = wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(&v82, &v73);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9290;
    goto LABEL_9;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *))(*(_QWORD *)v73 + 24LL))(
         v73,
         &v83);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9292;
    goto LABEL_9;
  }
  OpenPropertyStore = a2->lpVtbl->OpenPropertyStore;
  v53 = 0;
  v3 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, struct IPropertyStore **))OpenPropertyStore)(a2, 2, &v53);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9296;
    goto LABEL_9;
  }
  v3 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v53->lpVtbl->GetValue)(
         v53,
         &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
         v62);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9297;
    goto LABEL_9;
  }
  if ( LOWORD(v62[0]) != 72 )
  {
    Activate = a2->lpVtbl->Activate;
    v9 = v72;
    v72 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    ppv = (int *)&v72;
    v3 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))Activate)(
           a2,
           &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
           23);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 9300;
      goto LABEL_9;
    }
    v10 = v72;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v72 + 32LL);
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v75);
    v3 = v11(v10, 0, &v75);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 9303;
      goto LABEL_9;
    }
    v12 = v75;
    v13 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v75 + 72LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    v3 = v13(v12, &pv);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 9306;
      goto LABEL_9;
    }
  }
  QueryInterface = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v74);
  v3 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, __int64 **))QueryInterface)(
         g_DeviceEnumerator,
         (unsigned int)v83,
         15,
         &v74);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9310;
    goto LABEL_9;
  }
  v3 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v74 + 24))(v74, &v84);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9312;
    goto LABEL_9;
  }
  v15 = v69;
  v69 = 0;
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  v3 = CoCreateInstance(
         &GUID_06cca63e_9941_441b_b004_39f999ada412,
         0,
         0x17u,
         &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
         &v69);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 9315;
    goto LABEL_9;
  }
  v16 = 1;
  v17 = 0;
  if ( !v84 )
  {
LABEL_116:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
    PropVariantClear(pvar);
    PropVariantClear(v62);
    if ( pv )
      CoTaskMemFree(pv);
    v4 = 0;
    goto LABEL_119;
  }
  while ( 1 )
  {
    v54 = 0;
    v55 = 0;
    v52 = 0;
    v56 = 0;
    v57 = 0;
    *(_OWORD *)v64 = 0;
    v65 = 0;
    v71 = 0;
    v18 = *v74;
    v54 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMMDevice **))(v18 + 32))(v74, v17, &v54);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9329;
      goto LABEL_135;
    }
    v20 = v55;
    v55 = 0;
    if ( v20 )
      (*(void (__fastcall **)(struct IMMEndpointInternal *))(*(_QWORD *)v20 + 16LL))(v20);
    v19 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, struct IMMEndpointInternal **))v54->lpVtbl->QueryInterface)(
            v54,
            &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21,
            &v55);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9332;
      goto LABEL_135;
    }
    v19 = (*(__int64 (__fastcall **)(struct IMMEndpointInternal *, int *))(*(_QWORD *)v55 + 32LL))(v55, &v71);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9333;
      goto LABEL_135;
    }
    if ( (v71 & 0x20000000) != 0 )
      break;
LABEL_115:
    PropVariantClear(v64);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v56);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
    if ( ++v17 >= v84 )
      goto LABEL_116;
  }
  if ( (v71 & 0x3000000) == 0x3000000 )
  {
LABEL_48:
    (*(void (__fastcall **)(LPVOID, struct IMMDevice *))(*(_QWORD *)v69 + 32LL))(v69, v54);
    goto LABEL_115;
  }
  v21 = v54;
  v22 = v54->lpVtbl->OpenPropertyStore;
  v23 = v52;
  v52 = 0;
  if ( v23 )
    ((void (__fastcall *)(struct IPropertyStore *))v23->lpVtbl->Release)(v23);
  v19 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, struct IPropertyStore **))v22)(v21, 0, &v52);
  v4 = v19;
  if ( v19 < 0 )
  {
    v49 = 9355;
    goto LABEL_135;
  }
  v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v52->lpVtbl->GetValue)(
          v52,
          &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
          v64);
  v4 = v19;
  if ( v19 < 0 )
  {
    v49 = 9356;
    goto LABEL_135;
  }
  if ( LOWORD(v62[0]) == 72 || LOWORD(v64[0]) == 72 )
  {
    *(_OWORD *)v78 = 0;
    v79 = 0;
    *(_OWORD *)v76 = 0;
    v77 = 0;
    if ( LOWORD(v62[0]) != 72
      || LOWORD(v64[0]) != 72
      || *(_QWORD *)v64[1] != *(_QWORD *)v62[1]
      || *((_QWORD *)v64[1] + 1) != *((_QWORD *)v62[1] + 1) )
    {
LABEL_114:
      PropVariantClear(v76);
      PropVariantClear(v78);
      goto LABEL_115;
    }
    v37 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v52->lpVtbl->GetValue)(
            v52,
            &DEVPKEY_AudioEndpointPlugin_PnPInterface,
            v78);
    v4 = v37;
    if ( v37 < 0 )
    {
      v50 = 9379;
      goto LABEL_129;
    }
    v37 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v53->lpVtbl->GetValue)(
            v53,
            &DEVPKEY_AudioEndpointPlugin_PnPInterface,
            v76);
    v4 = v37;
    if ( v37 < 0 )
    {
      v50 = 9380;
LABEL_129:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v37,
        (int)ppv);
      PropVariantClear(v76);
      PropVariantClear(v78);
      goto LABEL_136;
    }
    if ( LOWORD(v76[0]) != 31 || LOWORD(v78[0]) != 31 || (unsigned int)_o__wcsicmp(v76[1], v78[1]) )
      goto LABEL_114;
    PropVariantClear(v76);
    PropVariantClear(v78);
  }
  else
  {
    *(_QWORD *)v61 = 0;
    v60 = 0;
    v59 = 0;
    lpVtbl = v54->lpVtbl;
    *(_QWORD *)v61 = 0;
    ppv = v61;
    ConnectorIdFromSavedConnectedTo = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))lpVtbl->Activate)(
                                        v54,
                                        &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
                                        23);
    v26 = retaddr;
    if ( ConnectorIdFromSavedConnectedTo < 0 )
    {
      v27 = 9404;
LABEL_57:
      wil::details::in1diag3::_Log_Hr(
        v26,
        (void *)v27,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)ConnectorIdFromSavedConnectedTo,
        (int)v61);
LABEL_58:
      if ( v59 )
        CoTaskMemFree(v59);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v61);
      goto LABEL_115;
    }
    v28 = *(_QWORD *)v61;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v61 + 32LL);
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v60);
    ConnectorIdFromSavedConnectedTo = v29(v28, 0, &v60);
    v26 = retaddr;
    if ( ConnectorIdFromSavedConnectedTo < 0 )
    {
      v27 = 9412;
      goto LABEL_57;
    }
    v30 = v60;
    v31 = *(int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v60 + 72LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v59,
      0);
    if ( v31(v30, &v59) < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v59,
        0);
      ConnectorIdFromSavedConnectedTo = GetConnectorIdFromSavedConnectedTo(v52, &v59);
      v26 = retaddr;
      if ( ConnectorIdFromSavedConnectedTo < 0 )
      {
        v27 = 9427;
        goto LABEL_57;
      }
    }
    if ( !(unsigned int)AudMigLibCompareDeviceIds((const unsigned __int16 *)pv, v59) )
      goto LABEL_58;
    LODWORD(v81) = 0;
    if ( (int)CAvEndpointBuilder::CompareDigitalAudioPropertiesForMigration(v32, v53, v52, (int *)&v81) >= 0
      && (_DWORD)v81 )
    {
      v34 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v34 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v34,
          &word_18007580E);
      goto LABEL_58;
    }
    if ( (int)CAvEndpointBuilder::CompareRootEnumeratedDevicesForMigration(v33, v53, v52, (int *)&v81) >= 0
      && (_DWORD)v81 )
    {
      v35 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v35 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v35,
          &dword_18007579C);
      goto LABEL_58;
    }
    if ( (int)CAvEndpointBuilder::CompareBTHLEDevicesForMigration(
                (CAvEndpointBuilder *)&v81,
                (const unsigned __int16 *)pv,
                v53,
                v59,
                v52,
                (int *)&v81) >= 0
      && (_DWORD)v81 )
    {
      v36 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v36 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v36,
          byte_180075733);
      goto LABEL_58;
    }
    if ( v59 )
      CoTaskMemFree(v59);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v61);
  }
  v38 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v38 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v38,
      byte_1800756F9);
  if ( ((int (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v52->lpVtbl->GetValue)(
         v52,
         PKEY_AudioEndpoint_MigrationReason,
         pvar) >= 0
    && LOWORD(pvar[0]) == 19
    && LODWORD(pvar[1]) )
  {
    v16 = (unsigned int)pvar[1];
  }
  v39 = v55;
  v40 = *(void (__fastcall **)(struct IMMEndpointInternal *, _QWORD, __int64 **))(*(_QWORD *)v55 + 40LL);
  v41 = v56;
  v56 = 0;
  if ( v41 )
    (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
  v40(v39, 0, &v56);
  v19 = AudMigLibCopyEndpointUpgradeProperties((__int64)v53, (__int64 *)v52, (__int64)v56, v16, 0);
  v4 = v19;
  if ( v19 < 0 )
  {
    v49 = 9503;
    goto LABEL_135;
  }
  if ( !v56 )
    goto LABEL_107;
  v43 = v68;
  v44 = *(int (__fastcall **)(struct IMMEndpointInternal *, __int64, __int64 *))(*(_QWORD *)v68 + 40LL);
  v45 = v57;
  v57 = 0;
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v44(v43, 2, &v57) < 0
    || (v42 = v57) == 0
    || (v19 = AudMigLibCopyEndpointUpgradeProperties(v57, v56, (__int64)v52, v16, 0), v4 = v19, v19 >= 0) )
  {
LABEL_107:
    v19 = CAvEndpointBuilder::MigrateUpgradeAudioSystemEffectsProperties(v42, v68, v55, v16);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9516;
      goto LABEL_135;
    }
    v19 = CAvEndpointBuilder::MoveUpgradeLfxGfxFxPropertiesToContextProperties(v46, v68, v55);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9519;
      goto LABEL_135;
    }
    v19 = AudMigLibMigrateRoleAndDeviceState(v53, v52, v83);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9521;
      goto LABEL_135;
    }
    v19 = (*(__int64 (__fastcall **)(LPVOID, struct IMMDevice *, _QWORD))(*(_QWORD *)v69 + 56LL))(v69, a2, 0);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9525;
      goto LABEL_135;
    }
    v19 = MigrateUpgradeHistory(v54, a2);
    v4 = v19;
    if ( v19 < 0 )
    {
      v49 = 9529;
      goto LABEL_135;
    }
    v47 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v47 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v47,
        byte_1800756B1);
    goto LABEL_48;
  }
  v49 = 9511;
LABEL_135:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v49,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v19,
    (int)ppv);
LABEL_136:
  PropVariantClear(v64);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v56);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
LABEL_10:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  PropVariantClear(pvar);
  PropVariantClear(v62);
  if ( pv )
    CoTaskMemFree(pv);
LABEL_119:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
  return v4;
}

```

## disassembly

```asm
0x18004f474  mov     [rsp-8+arg_8], rdx
0x18004f479  mov     [rsp-8+arg_0], rcx
0x18004f47e  push    rbp
0x18004f47f  push    rbx
0x18004f480  push    rsi
0x18004f481  push    rdi
0x18004f482  push    r12
0x18004f484  push    r14
0x18004f486  push    r15
0x18004f488  lea     rbp, [rsp-30h]
0x18004f48d  sub     rsp, 130h
0x18004f494  mov     rsi, rdx
0x18004f497  xor     r12d, r12d
0x18004f49a  mov     [rbp+60h+arg_18], r12d
0x18004f4a1  mov     [rbp+60h+var_90], r12
0x18004f4a5  mov     [rbp+60h+var_70], r12
0x18004f4a9  mov     [rbp+60h+var_78], r12
0x18004f4ad  mov     ecx, r12d
0x18004f4b0  mov     [rbp+60h+var_98], rcx
0x18004f4b4  mov     [rbp+60h+arg_10], r12d
0x18004f4bb  mov     [rbp+60h+var_80], r12
0x18004f4bf  mov     [rbp+60h+var_68], r12
0x18004f4c3  mov     [rsp+160h+pv], r12
0x18004f4c8  mov     [rbp+60h+var_88], r12d
0x18004f4cc  xorps   xmm0, xmm0
0x18004f4cf  xor     eax, eax
0x18004f4d1  movups  xmmword ptr [rbp+60h+var_E0], xmm0
0x18004f4d5  mov     [rbp+60h+var_D0], rax
0x18004f4d9  movups  xmmword ptr [rbp+60h+pvar], xmm0
0x18004f4dd  mov     [rbp+60h+var_A0], rax
0x18004f4e1  mov     [rsp+160h+var_128], r12
0x18004f4e6  lea     rdx, WPP_GLOBAL_Control
0x18004f4ed  mov     rax, cs:WPP_GLOBAL_Control
0x18004f4f4  cmp     rax, rdx
0x18004f4f7  jz      short loc_18004F51E
0x18004f4f9  test    byte ptr [rax+1Ch], 4
0x18004f4fd  jz      short loc_18004F51E
0x18004f4ff  cmp     byte ptr [rax+19h], 4
0x18004f503  jb      short loc_18004F51E
0x18004f505  lea     edx, [r12+40h]
0x18004f50a  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18004f511  mov     rcx, [rax+10h]
0x18004f515  call    WPP_SF_
0x18004f51a  mov     rcx, [rbp+60h+var_98]
0x18004f51e  mov     [rbp+60h+var_98], r12
0x18004f522  test    rcx, rcx
0x18004f525  jz      short loc_18004F534
0x18004f527  mov     rax, [rcx]
0x18004f52a  mov     rax, [rax+10h]
0x18004f52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f533  nop
0x18004f534  lea     rdx, [rbp+60h+var_98]
0x18004f538  lea     rcx, [rbp+60h+arg_8]
0x18004f53c  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x18004f541  mov     ebx, eax
0x18004f543  test    eax, eax
0x18004f545  jns     short loc_18004F54E
0x18004f547  mov     edx, 2442h
0x18004f54c  jmp     short loc_18004F56D
0x18004f54e  mov     rcx, [rbp+60h+var_98]
0x18004f552  mov     rax, [rcx]
0x18004f555  lea     rdx, [rbp+60h+var_88]
0x18004f559  mov     rax, [rax+20h]
0x18004f55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f562  mov     ebx, eax
0x18004f564  test    eax, eax
0x18004f566  jns     short loc_18004F5BB
0x18004f568  mov     edx, 2443h; void *
0x18004f56d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f574  mov     r9d, eax; char *
0x18004f577  mov     rcx, [rbp+68h]; this
0x18004f57b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f580  nop
0x18004f581  lea     rcx, [rsp+160h+var_128]
0x18004f586  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f58b  nop
0x18004f58c  lea     rcx, [rbp+60h+pvar]; pvar
0x18004f590  call    cs:__imp_PropVariantClear
0x18004f596  nop
0x18004f597  lea     rcx, [rbp+60h+var_E0]; pvar
0x18004f59b  call    cs:__imp_PropVariantClear
0x18004f5a1  nop
0x18004f5a2  mov     rcx, [rsp+160h+pv]; pv
0x18004f5a7  test    rcx, rcx
0x18004f5aa  jz      loc_18004FF0C
0x18004f5b0  call    cs:__imp_CoTaskMemFree
0x18004f5b6  jmp     loc_18004FF0C
0x18004f5bb  test    [rbp+60h+var_88], 20000000h
0x18004f5c2  jnz     loc_18004FED8
0x18004f5c8  mov     rcx, [rbp+60h+var_78]
0x18004f5cc  mov     [rbp+60h+var_78], r12
0x18004f5d0  test    rcx, rcx
0x18004f5d3  jz      short loc_18004F5E2
0x18004f5d5  mov     rax, [rcx]
0x18004f5d8  mov     rax, [rax+10h]
0x18004f5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5e1  nop
0x18004f5e2  lea     rdx, [rbp+60h+var_78]
0x18004f5e6  lea     rcx, [rbp+60h+arg_8]
0x18004f5ea  call    ??$com_query_to_nothrow@UIMMEndpoint@@AEAPEAUIMMDevice@@@wil@@YAJAEAPEAUIMMDevice@@PEAPEAUIMMEndpoint@@@Z; wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(IMMDevice * &,IMMEndpoint * *)
0x18004f5ef  mov     ebx, eax
0x18004f5f1  test    eax, eax
0x18004f5f3  jns     short loc_18004F5FF
0x18004f5f5  mov     edx, 244Ah
0x18004f5fa  jmp     loc_18004F56D
0x18004f5ff  mov     rcx, [rbp+60h+var_78]
0x18004f603  mov     rax, [rcx]
0x18004f606  lea     rdx, [rbp+60h+arg_10]
0x18004f60d  mov     rax, [rax+18h]
0x18004f611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f616  mov     ebx, eax
0x18004f618  test    eax, eax
0x18004f61a  jns     short loc_18004F626
0x18004f61c  mov     edx, 244Ch
0x18004f621  jmp     loc_18004F56D
0x18004f626  mov     rax, [rsi]
0x18004f629  mov     rbx, [rax+20h]
0x18004f62d  mov     rcx, [rsp+160h+var_128]
0x18004f632  mov     [rsp+160h+var_128], r12
0x18004f637  test    rcx, rcx
0x18004f63a  jz      short loc_18004F649
0x18004f63c  mov     rdx, [rcx]
0x18004f63f  mov     rax, [rdx+10h]
0x18004f643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f648  nop
0x18004f649  lea     r8, [rsp+160h+var_128]
0x18004f64e  mov     edx, 2
0x18004f653  mov     rcx, rsi
0x18004f656  mov     rax, rbx
0x18004f659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f65e  mov     ebx, eax
0x18004f660  test    eax, eax
0x18004f662  jns     short loc_18004F66E
0x18004f664  mov     edx, 2450h
0x18004f669  jmp     loc_18004F56D
0x18004f66e  mov     rcx, [rsp+160h+var_128]
0x18004f673  mov     rax, [rcx]
0x18004f676  lea     r8, [rbp+60h+var_E0]
0x18004f67a  lea     rdx, DEVPKEY_AudioEndpointPlugin_FactoryCLSID
0x18004f681  mov     rax, [rax+28h]
0x18004f685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f68a  mov     ebx, eax
0x18004f68c  test    eax, eax
0x18004f68e  jns     short loc_18004F69A
0x18004f690  mov     edx, 2451h
0x18004f695  jmp     loc_18004F56D
0x18004f69a  cmp     word ptr [rbp+60h+var_E0], 48h ; 'H'
0x18004f69f  jz      loc_18004F764
0x18004f6a5  mov     rax, [rsi]
0x18004f6a8  mov     rbx, [rax+18h]
0x18004f6ac  mov     rcx, [rbp+60h+var_80]
0x18004f6b0  mov     [rbp+60h+var_80], r12
0x18004f6b4  test    rcx, rcx
0x18004f6b7  jz      short loc_18004F6C6
0x18004f6b9  mov     rax, [rcx]
0x18004f6bc  mov     rax, [rax+10h]
0x18004f6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6c5  nop
0x18004f6c6  lea     rax, [rbp+60h+var_80]
0x18004f6ca  mov     [rsp+160h+ppv], rax
0x18004f6cf  xor     r9d, r9d
0x18004f6d2  lea     r8d, [r9+17h]
0x18004f6d6  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18004f6dd  mov     rcx, rsi
0x18004f6e0  mov     rax, rbx
0x18004f6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6e8  mov     ebx, eax
0x18004f6ea  test    eax, eax
0x18004f6ec  jns     short loc_18004F6F8
0x18004f6ee  mov     edx, 2454h
0x18004f6f3  jmp     loc_18004F56D
0x18004f6f8  mov     rdi, [rbp+60h+var_80]
0x18004f6fc  mov     rax, [rdi]
0x18004f6ff  mov     rbx, [rax+20h]
0x18004f703  lea     rcx, [rbp+60h+var_68]
0x18004f707  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18004f70c  lea     r8, [rbp+60h+var_68]
0x18004f710  xor     edx, edx
0x18004f712  mov     rcx, rdi
0x18004f715  mov     rax, rbx
0x18004f718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f71d  mov     ebx, eax
0x18004f71f  test    eax, eax
0x18004f721  jns     short loc_18004F72D
0x18004f723  mov     edx, 2457h
0x18004f728  jmp     loc_18004F56D
0x18004f72d  mov     rdi, [rbp+60h+var_68]
0x18004f731  mov     rax, [rdi]
0x18004f734  mov     rbx, [rax+48h]
0x18004f738  xor     edx, edx
0x18004f73a  lea     rcx, [rsp+160h+pv]
0x18004f73f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004f744  lea     rdx, [rsp+160h+pv]
0x18004f749  mov     rcx, rdi
0x18004f74c  mov     rax, rbx
0x18004f74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f754  mov     ebx, eax
0x18004f756  test    eax, eax
0x18004f758  jns     short loc_18004F764
0x18004f75a  mov     edx, 245Ah
0x18004f75f  jmp     loc_18004F56D
0x18004f764  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18004f76b  mov     rcx, [rax]
0x18004f76e  mov     rbx, [rcx+18h]
0x18004f772  lea     rcx, [rbp+60h+var_70]
0x18004f776  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x18004f77b  lea     r9, [rbp+60h+var_70]
0x18004f77f  mov     r8d, 0Fh
0x18004f785  mov     edx, [rbp+60h+arg_10]
0x18004f78b  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18004f792  mov     rax, rbx
0x18004f795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f79a  mov     ebx, eax
0x18004f79c  test    eax, eax
0x18004f79e  jns     short loc_18004F7AA
0x18004f7a0  mov     edx, 245Eh
0x18004f7a5  jmp     loc_18004F56D
0x18004f7aa  mov     rcx, [rbp+60h+var_70]
0x18004f7ae  mov     rax, [rcx]
0x18004f7b1  lea     rdx, [rbp+60h+arg_18]
0x18004f7b8  mov     rax, [rax+18h]
0x18004f7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7c1  mov     ebx, eax
0x18004f7c3  test    eax, eax
0x18004f7c5  jns     short loc_18004F7D1
0x18004f7c7  mov     edx, 2460h
0x18004f7cc  jmp     loc_18004F56D
0x18004f7d1  mov     rcx, [rbp+60h+var_90]
0x18004f7d5  mov     [rbp+60h+var_90], r12
0x18004f7d9  test    rcx, rcx
0x18004f7dc  jz      short loc_18004F7EB
0x18004f7de  mov     rax, [rcx]
0x18004f7e1  mov     rax, [rax+10h]
0x18004f7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7ea  nop
0x18004f7eb  lea     rax, [rbp+60h+var_90]
0x18004f7ef  mov     [rsp+160h+ppv], rax; int
0x18004f7f4  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x18004f7fb  xor     edx, edx; pUnkOuter
0x18004f7fd  lea     r8d, [rdx+17h]; dwClsContext
0x18004f801  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x18004f808  call    cs:__imp_CoCreateInstance
0x18004f80e  mov     ebx, eax
0x18004f810  test    eax, eax
0x18004f812  jns     short loc_18004F81E
0x18004f814  mov     edx, 2463h
0x18004f819  jmp     loc_18004F56D
0x18004f81e  mov     r14d, 1
0x18004f824  mov     r15d, r12d
0x18004f827  cmp     [rbp+60h+arg_18], r12d
0x18004f82e  jbe     loc_18004FED8
0x18004f834  mov     [rsp+160h+var_120], r12
0x18004f839  mov     [rsp+160h+var_118], r12
0x18004f83e  mov     [rsp+160h+var_130], r12
0x18004f843  mov     [rsp+160h+var_110], r12
0x18004f848  mov     [rsp+160h+var_108], r12
0x18004f84d  xorps   xmm0, xmm0
0x18004f850  xor     eax, eax
0x18004f852  movups  xmmword ptr [rbp+60h+var_C8], xmm0
0x18004f856  mov     [rbp+60h+var_B8], rax
0x18004f85a  mov     [rbp+60h+var_84], r12d
0x18004f85e  mov     rcx, [rbp+60h+var_70]
0x18004f862  mov     rax, [rcx]
0x18004f865  mov     [rsp+160h+var_120], r12
0x18004f86a  lea     r8, [rsp+160h+var_120]
0x18004f86f  mov     edx, r15d
0x18004f872  mov     rax, [rax+20h]
0x18004f876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f87b  mov     ebx, eax
0x18004f87d  test    eax, eax
0x18004f87f  js      loc_18004FFE2
0x18004f885  mov     rcx, [rsp+160h+var_118]
0x18004f88a  mov     [rsp+160h+var_118], r12
0x18004f88f  test    rcx, rcx
0x18004f892  jz      short loc_18004F8A1
0x18004f894  mov     rax, [rcx]
0x18004f897  mov     rax, [rax+10h]
0x18004f89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8a0  nop
0x18004f8a1  mov     rcx, [rsp+160h+var_120]
0x18004f8a6  mov     rax, [rcx]
0x18004f8a9  lea     r8, [rsp+160h+var_118]
0x18004f8ae  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x18004f8b5  mov     rax, [rax]
0x18004f8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8bd  mov     ebx, eax
0x18004f8bf  test    eax, eax
0x18004f8c1  js      loc_18004FFDB
0x18004f8c7  mov     rcx, [rsp+160h+var_118]
0x18004f8cc  mov     rax, [rcx]
0x18004f8cf  lea     rdx, [rbp+60h+var_84]
0x18004f8d3  mov     rax, [rax+20h]
0x18004f8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8dc  mov     ebx, eax
0x18004f8de  test    eax, eax
0x18004f8e0  js      loc_18004FFD4
0x18004f8e6  mov     eax, [rbp+60h+var_84]
0x18004f8e9  bt      eax, 1Dh
0x18004f8ed  jnb     loc_18004FE87
0x18004f8f3  and     eax, 3000000h
  ... truncated ...
```
