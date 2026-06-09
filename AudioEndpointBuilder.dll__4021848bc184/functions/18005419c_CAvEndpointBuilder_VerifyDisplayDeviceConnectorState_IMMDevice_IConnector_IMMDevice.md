# CAvEndpointBuilder::VerifyDisplayDeviceConnectorState(IMMDevice *,IConnector *,IMMDevice *)

- ea: `0x18005419c`
- end: `0x180054c14`
- name: `?VerifyDisplayDeviceConnectorState@CAvEndpointBuilder@@AEAAJPEAUIMMDevice@@PEAUIConnector@@0@Z`
- size: `2680`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IMMDevice *, struct IConnector *, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052ffc`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001d960`
- `0x180021030`
- `0x18003e920`
- `0x18003f7a4`
- `0x18005419c`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800546c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800547c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800549cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180054a93`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800546c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800547c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800549cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180054a93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005490d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005490d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005463f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005463f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054ba3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054bae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054bb9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054ba3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054bae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054bb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005433d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005434e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005435f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005485c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005486d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005497e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005498f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054af3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005433d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005434e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005435f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005485c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005486d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005497e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005498f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054af3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b8e`

## string_xrefs

- `0x1800542fb`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005446a`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180054835`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180054923`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800549fb`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180054b43`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CAvEndpointBuilder::VerifyDisplayDeviceConnectorState(
        CAvEndpointBuilder *this,
        struct IMMDevice *a2,
        struct IConnector *a3,
        struct IMMDevice *a4)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  HRESULT (__stdcall *GetConnectedTo)(IConnector *, IConnector **); // rbx
  int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // esi
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rbx
  __int64 v17; // rbx
  int (__fastcall *v18)(__int64, _QWORD, _QWORD); // rdi
  __int64 v19; // r8
  int JackProperties; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // r15d
  __int64 v25; // rbx
  int (__fastcall *v26)(__int64, __int64, GUID *, __int64 *); // rdi
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  HRESULT v31; // eax
  int v32; // eax
  void *v33; // rbx
  struct IConnector *v34; // rsi
  HRESULT (__stdcall *v35)(IConnector *, IConnector **); // rdi
  HRESULT (__stdcall *v36)(IConnector *, IConnector **); // rdi
  struct IConnector *v37; // rdi
  HRESULT (__stdcall *GetDeviceIdConnectedTo)(IConnector *, LPWSTR *); // rsi
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rdi
  struct IUnknownVtbl *v40; // rax
  int v41; // eax
  int v42; // edi
  HRESULT v43; // eax
  __int64 v44; // rdx
  HRESULT (__stdcall *v45)(IMMDevice *, LPWSTR *); // rdi
  struct IConnector *v46; // rsi
  HRESULT (__stdcall *v47)(IConnector *, LPWSTR *); // rdi
  int *ppv; // [rsp+20h] [rbp-E0h]
  int v50[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v52; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v53; // [rsp+48h] [rbp-B8h] BYREF
  struct IConnector *v54; // [rsp+50h] [rbp-B0h] BYREF
  int v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, GUID *, struct IConnector **); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v58; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v59; // [rsp+78h] [rbp-88h] BYREF
  struct IConnector *v60; // [rsp+80h] [rbp-80h] BYREF
  struct IConnector *v61; // [rsp+88h] [rbp-78h] BYREF
  __int64 v62; // [rsp+90h] [rbp-70h] BYREF
  int v63; // [rsp+98h] [rbp-68h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v67; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v69; // [rsp+C8h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h]
  PROPVARIANT v72[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v73; // [rsp+F8h] [rbp-8h]
  PROPVARIANT v74[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v75; // [rsp+110h] [rbp+10h]
  IID rclsid; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v77[4]; // [rsp+130h] [rbp+30h] BYREF
  int v78; // [rsp+134h] [rbp+34h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v66 = 0;
  v65 = 0;
  v62 = 0;
  v54 = 0;
  *(_OWORD *)v74 = 0;
  v75 = 0;
  *(_OWORD *)v72 = 0;
  v73 = 0;
  *(_OWORD *)pvar = 0;
  v71 = 0;
  v64 = 0;
  memset_0(v77, 0, 0x60u);
  v53 = 0;
  v52 = 0;
  pv = 0;
  v69 = 0;
  rclsid = 0;
  v63 = 0;
  v55 = 0;
  *(_QWORD *)v50 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v9 = -2147024809;
    v10 = 2147942487LL;
    v11 = 11012;
    goto LABEL_113;
  }
  lpVtbl = a2->lpVtbl;
  v62 = 0;
  v8 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, __int64 *))lpVtbl->OpenPropertyStore)(a2, 2, &v62);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 11015;
LABEL_113:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)v10,
      (int)ppv);
    goto LABEL_114;
  }
  GetConnectedTo = a3->lpVtbl->GetConnectedTo;
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v54);
  if ( ((unsigned int (__fastcall *)(struct IConnector *, struct IConnector **))GetConnectedTo)(a3, &v54) == -2147023728 )
  {
    v56 = 0;
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v54);
    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v62 + 40LL))(
            v62,
            PKEY_Endpoint_LocalIdSaveConnectedTo,
            v72);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 11027;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v13,
        (int)ppv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v56);
LABEL_114:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v50);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v52 )
        CoTaskMemFree(v52);
      if ( v53 )
        CoTaskMemFree(v53);
      goto LABEL_120;
    }
    if ( LOWORD(v72[0]) != 19 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v56);
LABEL_12:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v50);
LABEL_13:
      if ( pv )
        CoTaskMemFree(pv);
      if ( v52 )
        CoTaskMemFree(v52);
      if ( v53 )
        CoTaskMemFree(v53);
      v9 = 0;
      goto LABEL_120;
    }
    v15 = (unsigned int)v72[1];
    Activate = a4->lpVtbl->Activate;
    *(_QWORD *)v50 = 0;
    ppv = v50;
    v13 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))Activate)(
            a4,
            &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
            23);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 11038;
      goto LABEL_9;
    }
    v17 = *(_QWORD *)v50;
    v18 = *(int (__fastcall **)(__int64, _QWORD, _QWORD))(**(_QWORD **)v50 + 56LL);
    v19 = (__int64)v56;
    v56 = 0;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v18(v17, v15, &v56) >= 0 )
    {
      if ( v56 )
      {
        wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v54);
        v13 = (**v56)(v56, &GUID_9c2c4058_23f5_41de_877a_df3af236a09e, &v54);
        v9 = v13;
        if ( v13 < 0 )
        {
          v14 = 11043;
          goto LABEL_9;
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v56);
  }
  if ( !v54 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B27,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x80004005LL,
      (int)ppv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v50);
LABEL_103:
    if ( pv )
      CoTaskMemFree(pv);
    if ( v52 )
      CoTaskMemFree(v52);
    if ( v53 )
      CoTaskMemFree(v53);
    v9 = -2147467259;
    goto LABEL_120;
  }
  JackProperties = GetJackProperties(v54, &v55, 0, 0, 0, 0);
  v9 = JackProperties;
  if ( JackProperties < 0 )
  {
    v10 = (unsigned int)JackProperties;
    v11 = 11050;
    goto LABEL_113;
  }
  if ( v55 )
    goto LABEL_12;
  v21 = v66;
  v66 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = ((__int64 (__fastcall *)(struct IConnector *, GUID *, __int64 *))v54->lpVtbl->QueryInterface)(
          v54,
          &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
          &v66);
  v9 = v22;
  if ( v22 < 0 )
  {
    v10 = (unsigned int)v22;
    v11 = 11056;
    goto LABEL_113;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v62 + 40LL))(
          v62,
          PKEY_Endpoint_Sink_Id,
          v74);
  v9 = v23;
  if ( v23 < 0 )
  {
    v10 = (unsigned int)v23;
    v11 = 11058;
    goto LABEL_113;
  }
  v24 = -72483923;
  if ( LOWORD(v74[0]) == 19 )
    v24 = (int)v74[1];
  v25 = v66;
  v26 = *(int (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v66 + 104LL);
  v27 = v64;
  v64 = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v26(v25, 1, &GUID_d9bd72ed_290f_4581_9ff3_61027a8fe532, &v64) < 0
    || (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v64 + 24LL))(v64, v77) < 0 )
  {
    memset_0(v77, 0, 0x60u);
    v78 = -72483923;
  }
  v28 = v65;
  v65 = 0;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v29 = ((__int64 (__fastcall *)(struct IConnector *, GUID *, __int64 *))v54->lpVtbl->QueryInterface)(
          v54,
          &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
          &v65);
  v9 = v29;
  if ( v29 < 0 )
  {
    v10 = (unsigned int)v29;
    v11 = 11088;
    goto LABEL_113;
  }
  v30 = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v65 + 56LL))(v65, &rclsid);
  v9 = v30;
  if ( v30 < 0 )
  {
    v10 = (unsigned int)v30;
    v11 = 11089;
    goto LABEL_113;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v31 = StringFromCLSID(&rclsid, (LPOLESTR *)&pv);
  v9 = v31;
  if ( v31 < 0 )
  {
    v10 = (unsigned int)v31;
    v11 = 11091;
    goto LABEL_113;
  }
  v32 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v62 + 40LL))(
          v62,
          &PKEY_AudioEndpoint_JackSubType,
          pvar);
  v9 = v32;
  if ( v32 < 0 )
  {
    v10 = (unsigned int)v32;
    v11 = 11094;
    goto LABEL_113;
  }
  if ( LOWORD(pvar[0]) != 31 )
    goto LABEL_12;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v69,
    pvar[1]);
  pvar[1] = 0;
  v33 = v69;
  if ( v24 == (HIWORD(v78) | ((unsigned __int16)v78 << 16)) && !(unsigned int)_o__wcsicmp(v69, pv) )
  {
    v68 = 0;
    v61 = 0;
    v60 = 0;
    v34 = v54;
    v35 = v54->lpVtbl->GetConnectedTo;
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v61);
    ((void (__fastcall *)(struct IConnector *, struct IConnector **))v35)(v34, &v61);
    v36 = a3->lpVtbl->GetConnectedTo;
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v60);
    ((void (__fastcall *)(struct IConnector *, struct IConnector **))v36)(a3, &v60);
    v37 = v54;
    if ( v61 != a3 || v60 != v54 )
    {
      v58 = 0;
      v59 = 0;
      GetDeviceIdConnectedTo = v54->lpVtbl->GetDeviceIdConnectedTo;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v58,
        0);
      ((void (__fastcall *)(struct IConnector *, LPVOID *))GetDeviceIdConnectedTo)(v37, &v58);
      GetId = a2->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v59,
        0);
      ((void (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &v59);
      ((void (__fastcall *)(struct IConnector *))v54->lpVtbl->Disconnect)(v54);
      ((void (__fastcall *)(struct IConnector *))a3->lpVtbl->Disconnect)(a3);
      ((void (__fastcall *)(struct IConnector *, struct IConnector *))v54->lpVtbl->ConnectTo)(v54, a3);
      if ( (unsigned int)_o__wcsicmp(v58, v59) )
      {
        v57 = 0;
        v40 = g_DeviceEnumerator->lpVtbl;
        v57 = 0;
        if ( ((int (__fastcall *)(struct IUnknown *, LPVOID, __int64 *))v40[1].Release)(g_DeviceEnumerator, v58, &v57) >= 0 )
        {
          v55 = 0;
          v41 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v57 + 48LL))(v57, &v55);
          v42 = v41;
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2B8E,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)(unsigned int)v41,
              (int)ppv);
LABEL_66:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
            if ( v59 )
              CoTaskMemFree(v59);
            if ( v58 )
              CoTaskMemFree(v58);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v60);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v61);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
            goto LABEL_71;
          }
          if ( v55 == 1 )
          {
            v67 = 0;
            v43 = CoCreateInstance(
                    &GUID_06cca63e_9941_441b_b004_39f999ada412,
                    0,
                    0x17u,
                    &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
                    &v67);
            v42 = v43;
            if ( v43 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2B95,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)(unsigned int)v43,
                (int)ppv);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v67);
              goto LABEL_66;
            }
            (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v67 + 40LL))(v67, v57, 4);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v67);
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
      }
      if ( v59 )
        CoTaskMemFree(v59);
      if ( v58 )
        CoTaskMemFree(v58);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v60);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v61);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
  }
  if ( v24 == (HIWORD(v78) | ((unsigned __int16)v78 << 16)) && !(unsigned int)_o__wcsicmp(v33, pv) )
    goto LABEL_110;
  v42 = ((__int64 (__fastcall *)(struct IConnector *, int *))v54->lpVtbl->IsConnected)(v54, &v63);
  if ( v42 >= 0 )
  {
    if ( v63 )
    {
      v45 = a2->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v52,
        0);
      v42 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))v45)(a2, &v52);
      if ( v42 < 0 )
      {
        v44 = 11175;
        goto LABEL_94;
      }
      v46 = v54;
      v47 = v54->lpVtbl->GetDeviceIdConnectedTo;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v53,
        0);
      v42 = ((__int64 (__fastcall *)(struct IConnector *, LPVOID *))v47)(v46, &v53);
      if ( v42 < 0 )
      {
        v44 = 11177;
        goto LABEL_94;
      }
      if ( !(unsigned int)_o__wcsicmp(v53, v52) )
      {
        ((void (__fastcall *)(struct IConnector *))v54->lpVtbl->Disconnect)(v54);
        ((void (__fastcall *)(struct IConnector *))a3->lpVtbl->Disconnect)(a3);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v50);
        if ( v33 )
          CoTaskMemFree(v33);
        goto LABEL_103;
      }
    }
LABEL_110:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v50);
    if ( v33 )
      CoTaskMemFree(v33);
    goto LABEL_13;
  }
  v44 = 11171;
LABEL_94:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v44,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v42,
    (int)ppv);
LABEL_71:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v50);
  if ( v33 )
    CoTaskMemFree(v33);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v52 )
    CoTaskMemFree(v52);
  if ( v53 )
    CoTaskMemFree(v53);
  v9 = v42;
LABEL_120:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v64);
  PropVariantClear(pvar);
  PropVariantClear(v72);
  PropVariantClear(v74);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v54);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v62);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
  return v9;
}

```

## disassembly

```asm
0x18005419c  mov     [rsp-8+arg_0], rbx
0x1800541a1  push    rbp
0x1800541a2  push    rsi
0x1800541a3  push    rdi
0x1800541a4  push    r12
0x1800541a6  push    r13
0x1800541a8  push    r14
0x1800541aa  push    r15
0x1800541ac  lea     rbp, [rsp-0A0h]
0x1800541b4  sub     rsp, 1A0h
0x1800541bb  mov     rax, cs:__security_cookie
0x1800541c2  xor     rax, rsp
0x1800541c5  mov     [rbp+0D0h+var_40], rax
0x1800541cc  mov     rdi, r9
0x1800541cf  mov     r14, r8
0x1800541d2  mov     r12, rdx
0x1800541d5  xor     r13d, r13d
0x1800541d8  mov     [rbp+0D0h+var_120], r13
0x1800541dc  mov     [rbp+0D0h+var_128], r13
0x1800541e0  mov     [rbp+0D0h+var_140], r13
0x1800541e4  mov     [rsp+1D0h+var_180], r13
0x1800541e9  xorps   xmm0, xmm0
0x1800541ec  xor     eax, eax
0x1800541ee  movups  xmmword ptr [rbp+0D0h+var_D0], xmm0
0x1800541f2  mov     [rbp+0D0h+var_C0], rax
0x1800541f6  movups  xmmword ptr [rbp+0D0h+var_E8], xmm0
0x1800541fa  mov     [rbp+0D0h+var_D8], rax
0x1800541fe  movups  xmmword ptr [rbp+0D0h+pvar], xmm0
0x180054202  mov     [rbp+0D0h+var_F0], rax
0x180054206  mov     [rbp+0D0h+var_130], r13
0x18005420a  xor     edx, edx; Val
0x18005420c  lea     r8d, [r13+60h]; Size
0x180054210  lea     rcx, [rbp+0D0h+var_A0]; void *
0x180054214  call    memset_0
0x180054219  mov     [rsp+1D0h+var_188], r13
0x18005421e  mov     [rsp+1D0h+var_190], r13
0x180054223  mov     [rsp+1D0h+pv], r13
0x180054228  mov     [rbp+0D0h+var_108], r13
0x18005422c  xorps   xmm0, xmm0
0x18005422f  movups  xmmword ptr [rbp+0D0h+rclsid.Data1], xmm0
0x180054233  mov     [rbp+0D0h+var_138], r13d
0x180054237  mov     [rsp+1D0h+var_178], r13d
0x18005423c  mov     qword ptr [rsp+1D0h+var_1A0], r13
0x180054241  test    r12, r12
0x180054244  jz      loc_180054B36
0x18005424a  test    r14, r14
0x18005424d  jz      loc_180054B36
0x180054253  test    rdi, rdi
0x180054256  jz      loc_180054B36
0x18005425c  mov     rax, [r12]
0x180054260  mov     [rbp+0D0h+var_140], r13
0x180054264  lea     r8, [rbp+0D0h+var_140]
0x180054268  lea     edx, [r13+2]
0x18005426c  mov     rcx, r12
0x18005426f  mov     rax, [rax+20h]
0x180054273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054278  mov     ebx, eax
0x18005427a  test    eax, eax
0x18005427c  jns     short loc_18005428B
0x18005427e  mov     r9d, eax
0x180054281  mov     edx, 2B07h
0x180054286  jmp     loc_180054B43
0x18005428b  mov     rax, [r14]
0x18005428e  mov     rbx, [rax+40h]
0x180054292  lea     rcx, [rsp+1D0h+var_180]
0x180054297  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18005429c  lea     rdx, [rsp+1D0h+var_180]
0x1800542a1  mov     rcx, r14
0x1800542a4  mov     rax, rbx
0x1800542a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542ac  mov     esi, 13h
0x1800542b1  cmp     eax, 80070490h
0x1800542b6  jnz     loc_180054453
0x1800542bc  mov     [rsp+1D0h+var_170], r13
0x1800542c1  lea     rcx, [rsp+1D0h+var_180]
0x1800542c6  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x1800542cb  mov     rcx, [rbp+0D0h+var_140]
0x1800542cf  mov     rax, [rcx]
0x1800542d2  lea     r8, [rbp+0D0h+var_E8]
0x1800542d6  lea     rdx, PKEY_Endpoint_LocalIdSaveConnectedTo
0x1800542dd  mov     rax, [rax+28h]
0x1800542e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542e6  mov     ebx, eax
0x1800542e8  test    eax, eax
0x1800542ea  jns     short loc_180054317
0x1800542ec  mov     edx, 2B13h; void *
0x1800542f1  mov     rcx, [rbp+0D8h]; this
0x1800542f8  mov     r9d, eax; char *
0x1800542fb  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180054302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054307  nop
0x180054308  lea     rcx, [rsp+1D0h+var_170]
0x18005430d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180054312  jmp     loc_180054B57
0x180054317  cmp     si, word ptr [rbp+0D0h+var_E8]
0x18005431b  jz      short loc_18005436D
0x18005431d  lea     rcx, [rsp+1D0h+var_170]
0x180054322  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180054327  nop
0x180054328  lea     rcx, [rsp+1D0h+var_1A0]
0x18005432d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180054332  nop
0x180054333  mov     rcx, [rsp+1D0h+pv]; pv
0x180054338  test    rcx, rcx
0x18005433b  jz      short loc_180054344
0x18005433d  call    cs:__imp_CoTaskMemFree
0x180054343  nop
0x180054344  mov     rcx, [rsp+1D0h+var_190]; pv
0x180054349  test    rcx, rcx
0x18005434c  jz      short loc_180054355
0x18005434e  call    cs:__imp_CoTaskMemFree
0x180054354  nop
0x180054355  mov     rcx, [rsp+1D0h+var_188]; pv
0x18005435a  test    rcx, rcx
0x18005435d  jz      short loc_180054365
0x18005435f  call    cs:__imp_CoTaskMemFree
0x180054365  mov     ebx, r13d
0x180054368  jmp     loc_180054B95
0x18005436d  mov     esi, dword ptr [rbp+0D0h+var_E8+8]
0x180054370  mov     rax, [rdi]
0x180054373  mov     rbx, [rax+18h]
0x180054377  mov     rcx, qword ptr [rsp+1D0h+var_1A0]
0x18005437c  mov     qword ptr [rsp+1D0h+var_1A0], r13
0x180054381  test    rcx, rcx
0x180054384  jz      short loc_180054393
0x180054386  mov     rax, [rcx]
0x180054389  mov     rax, [rax+10h]
0x18005438d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054392  nop
0x180054393  lea     rax, [rsp+1D0h+var_1A0]
0x180054398  mov     [rsp+1D0h+ppv], rax; int
0x18005439d  xor     r9d, r9d
0x1800543a0  lea     r8d, [r9+17h]
0x1800543a4  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x1800543ab  mov     rcx, rdi
0x1800543ae  mov     rax, rbx
0x1800543b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800543b6  mov     ebx, eax
0x1800543b8  test    eax, eax
0x1800543ba  jns     short loc_1800543C6
0x1800543bc  mov     edx, 2B1Eh
0x1800543c1  jmp     loc_1800542F1
0x1800543c6  mov     rbx, qword ptr [rsp+1D0h+var_1A0]
0x1800543cb  mov     rax, [rbx]
0x1800543ce  mov     rdi, [rax+38h]
0x1800543d2  mov     r8, [rsp+1D0h+var_170]
0x1800543d7  mov     [rsp+1D0h+var_170], r13
0x1800543dc  test    r8, r8
0x1800543df  jz      short loc_1800543F1
0x1800543e1  mov     rcx, [r8]
0x1800543e4  mov     rax, [rcx+10h]
0x1800543e8  mov     rcx, r8
0x1800543eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800543f0  nop
0x1800543f1  lea     r8, [rsp+1D0h+var_170]
0x1800543f6  mov     edx, esi
0x1800543f8  mov     rcx, rbx
0x1800543fb  mov     rax, rdi
0x1800543fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054403  test    eax, eax
0x180054405  js      short loc_180054444
0x180054407  cmp     [rsp+1D0h+var_170], r13
0x18005440c  jz      short loc_180054444
0x18005440e  lea     rcx, [rsp+1D0h+var_180]
0x180054413  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180054418  mov     rcx, [rsp+1D0h+var_170]
0x18005441d  mov     rax, [rcx]
0x180054420  lea     r8, [rsp+1D0h+var_180]
0x180054425  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x18005442c  mov     rax, [rax]
0x18005442f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054434  mov     ebx, eax
0x180054436  test    eax, eax
0x180054438  jns     short loc_180054444
0x18005443a  mov     edx, 2B23h
0x18005443f  jmp     loc_1800542F1
0x180054444  lea     rcx, [rsp+1D0h+var_170]
0x180054449  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005444e  mov     esi, 13h
0x180054453  mov     rcx, [rsp+1D0h+var_180]; struct IConnector *
0x180054458  test    rcx, rcx
0x18005445b  jnz     short loc_18005448C
0x18005445d  mov     rcx, [rbp+0D8h]; this
0x180054464  mov     r9d, 80004005h; char *
0x18005446a  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180054471  mov     edx, 2B27h; void *
0x180054476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005447b  nop
0x18005447c  lea     rcx, [rsp+1D0h+var_1A0]
0x180054481  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180054486  nop
0x180054487  jmp     loc_180054AD8
0x18005448c  mov     [rsp+1D0h+var_1A8], r13; unsigned int *
0x180054491  mov     [rsp+1D0h+ppv], r13; int
0x180054496  xor     r9d, r9d; int *
0x180054499  xor     r8d, r8d; int *
0x18005449c  lea     rdx, [rsp+1D0h+var_178]; int *
0x1800544a1  call    ?GetJackProperties@@YAJPEAUIConnector@@PEAH111PEAK@Z; GetJackProperties(IConnector *,int *,int *,int *,int *,ulong *)
0x1800544a6  mov     ebx, eax
0x1800544a8  test    eax, eax
0x1800544aa  jns     short loc_1800544B9
0x1800544ac  mov     r9d, eax
0x1800544af  mov     edx, 2B2Ah
0x1800544b4  jmp     loc_180054B43
0x1800544b9  cmp     [rsp+1D0h+var_178], r13d
0x1800544be  jnz     loc_180054328
0x1800544c4  mov     rcx, [rbp+0D0h+var_120]
0x1800544c8  mov     [rbp+0D0h+var_120], r13
0x1800544cc  test    rcx, rcx
0x1800544cf  jz      short loc_1800544DE
0x1800544d1  mov     rax, [rcx]
0x1800544d4  mov     rax, [rax+10h]
0x1800544d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544dd  nop
0x1800544de  mov     rcx, [rsp+1D0h+var_180]
0x1800544e3  mov     rax, [rcx]
0x1800544e6  lea     r8, [rbp+0D0h+var_120]
0x1800544ea  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x1800544f1  mov     rax, [rax]
0x1800544f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544f9  mov     ebx, eax
0x1800544fb  test    eax, eax
0x1800544fd  jns     short loc_18005450C
0x1800544ff  mov     r9d, eax
0x180054502  mov     edx, 2B30h
0x180054507  jmp     loc_180054B43
0x18005450c  mov     rcx, [rbp+0D0h+var_140]
0x180054510  mov     rax, [rcx]
0x180054513  lea     r8, [rbp+0D0h+var_D0]
0x180054517  lea     rdx, PKEY_Endpoint_Sink_Id
0x18005451e  mov     rax, [rax+28h]
0x180054522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054527  mov     ebx, eax
0x180054529  test    eax, eax
0x18005452b  jns     short loc_18005453A
0x18005452d  mov     r9d, eax
0x180054530  mov     edx, 2B32h
0x180054535  jmp     loc_180054B43
0x18005453a  mov     r15d, 0FBADFBADh
0x180054540  cmp     word ptr [rbp+0D0h+var_D0], si
0x180054544  cmovz   r15d, dword ptr [rbp+0D0h+var_D0+8]
0x180054549  mov     rbx, [rbp+0D0h+var_120]
0x18005454d  mov     rax, [rbx]
0x180054550  mov     rdi, [rax+68h]
0x180054554  mov     rcx, [rbp+0D0h+var_130]
0x180054558  mov     [rbp+0D0h+var_130], r13
0x18005455c  test    rcx, rcx
0x18005455f  jz      short loc_18005456E
0x180054561  mov     rax, [rcx]
0x180054564  mov     rax, [rax+10h]
0x180054568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005456d  nop
0x18005456e  lea     r9, [rbp+0D0h+var_130]
0x180054572  lea     r8, _GUID_d9bd72ed_290f_4581_9ff3_61027a8fe532
0x180054579  mov     edx, 1
0x18005457e  mov     rcx, rbx
0x180054581  mov     rax, rdi
0x180054584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054589  test    eax, eax
0x18005458b  js      short loc_1800545A5
0x18005458d  mov     rcx, [rbp+0D0h+var_130]
0x180054591  mov     rax, [rcx]
0x180054594  lea     rdx, [rbp+0D0h+var_A0]
0x180054598  mov     rax, [rax+18h]
0x18005459c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545a1  test    eax, eax
0x1800545a3  jns     short loc_1800545BB
0x1800545a5  xor     edx, edx; Val
0x1800545a7  lea     r8d, [rdx+60h]; Size
0x1800545ab  lea     rcx, [rbp+0D0h+var_A0]; void *
0x1800545af  call    memset_0
0x1800545b4  mov     [rbp+0D0h+var_9C], 0FBADFBADh
0x1800545bb  mov     rcx, [rbp+0D0h+var_128]
0x1800545bf  mov     [rbp+0D0h+var_128], r13
0x1800545c3  test    rcx, rcx
0x1800545c6  jz      short loc_1800545D5
0x1800545c8  mov     rax, [rcx]
0x1800545cb  mov     rax, [rax+10h]
0x1800545cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545d4  nop
0x1800545d5  mov     rcx, [rsp+1D0h+var_180]
0x1800545da  mov     rax, [rcx]
0x1800545dd  lea     r8, [rbp+0D0h+var_128]
0x1800545e1  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x1800545e8  mov     rax, [rax]
0x1800545eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545f0  mov     ebx, eax
0x1800545f2  test    eax, eax
0x1800545f4  jns     short loc_180054603
0x1800545f6  mov     r9d, eax
0x1800545f9  mov     edx, 2B50h
0x1800545fe  jmp     loc_180054B43
0x180054603  mov     rcx, [rbp+0D0h+var_128]
0x180054607  mov     rax, [rcx]
0x18005460a  lea     rdx, [rbp+0D0h+rclsid]
0x18005460e  mov     rax, [rax+38h]
0x180054612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054617  mov     ebx, eax
0x180054619  test    eax, eax
0x18005461b  jns     short loc_18005462A
  ... truncated ...
```
