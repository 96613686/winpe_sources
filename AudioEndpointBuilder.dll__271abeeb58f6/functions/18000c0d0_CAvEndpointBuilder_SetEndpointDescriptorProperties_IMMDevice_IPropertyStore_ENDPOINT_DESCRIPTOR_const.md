# CAvEndpointBuilder::SetEndpointDescriptorProperties(IMMDevice *,IPropertyStore *,ENDPOINT_DESCRIPTOR const *)

- ea: `0x18000c0d0`
- end: `0x18000cea2`
- name: `?SetEndpointDescriptorProperties@CAvEndpointBuilder@@AEAAJPEAUIMMDevice@@PEAUIPropertyStore@@PEBUENDPOINT_DESCRIPTOR@@@Z`
- size: `3538`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IMMDevice *, struct IPropertyStore *, const struct ENDPOINT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x180006b0c`
- `0x18000c0d0`
- `0x18000fb60`
- `0x180010da8`
- `0x18001ba30`
- `0x18001d960`
- `0x180024fd4`
- `0x180028258`
- `0x180034c5c`
- `0x18003e920`
- `0x180052cb8`
- `0x180054f08`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb75`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c881`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000ca2f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000caca`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c881`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000ca2f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000caca`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c858`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c858`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ce7a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ce7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c20c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c56b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c20c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c56b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce6e`

## string_xrefs

- `0x18000c1ce`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000c720`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000cadb`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000cd6f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CAvEndpointBuilder::SetEndpointDescriptorProperties(
        CAvEndpointBuilder *this,
        struct IMMDevice *a2,
        struct IPropertyStore *a3,
        const struct ENDPOINT_DESCRIPTOR *a4)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  bool v12; // zf
  __int64 v13; // rax
  __int128 v14; // xmm0
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, unsigned __int16 **); // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  HRESULT v25; // eax
  __int64 v26; // rdx
  void *v27; // rcx
  _DWORD *v28; // rax
  CAvEndpointBuilder *v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v34; // r8d
  int v36; // [rsp+20h] [rbp-89h]
  unsigned __int16 *v37; // [rsp+30h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-71h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-69h] BYREF
  __int128 v40; // [rsp+48h] [rbp-61h] BYREF
  __int64 v41; // [rsp+58h] [rbp-51h]
  LPOLESTR v42; // [rsp+60h] [rbp-49h] BYREF
  int v43[2]; // [rsp+68h] [rbp-41h] BYREF
  LPVOID v44; // [rsp+70h] [rbp-39h] BYREF
  int v45; // [rsp+78h] [rbp-31h] BYREF
  int v46; // [rsp+7Ch] [rbp-2Dh] BYREF
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-29h] BYREF
  _DWORD *v48; // [rsp+90h] [rbp-19h]
  __int128 v49; // [rsp+98h] [rbp-11h] BYREF
  GUID pguid; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *(_OWORD *)pvar = 0;
  v48 = 0;
  lpsz = 0;
  v43[0] = 0;
  LODWORD(v42) = 0;
  v45 = 0;
  v37 = 0;
  v49 = 0;
  pguid = 0;
  pv = 0;
  v46 = 0;
  LODWORD(v44) = 0;
  if ( *((_DWORD *)a4 + 61) )
  {
    v40 = 0;
    v41 = 0;
    LOWORD(v40) = 11;
    WORD4(v40) = -1;
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
           a3,
           PKEY_Endpoint_IsUSB,
           &v40);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7055;
LABEL_7:
      v11 = (unsigned int)v8;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)v11,
        v36);
LABEL_9:
      if ( pv )
        CoTaskMemFree(pv);
      if ( v37 )
        CoTaskMemFree(v37);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      goto LABEL_166;
    }
  }
  if ( *((_DWORD *)a4 + 62) )
  {
    v40 = 0;
    v41 = 0;
    LOWORD(v40) = 11;
    WORD4(v40) = -1;
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
           a3,
           PKEY_Endpoint_IsSideband,
           &v40);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7064;
      goto LABEL_7;
    }
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 31;
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 7);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &PKEY_Device_DeviceDesc,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7073;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 31;
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 9);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         PKEY_Endpoint_Device_NAME,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7081;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 31;
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 5);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         PKEY_Endpoint_Devnode,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7087;
    goto LABEL_7;
  }
  if ( *((_QWORD *)a4 + 6) )
  {
    *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 6);
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
           a3,
           PKEY_Endpoint_SidebandDevnode,
           &v40);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7093;
      goto LABEL_7;
    }
  }
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 10);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &DEVPKEY_Device_DriverNodeStrongName,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7098;
    goto LABEL_7;
  }
  if ( *((_QWORD *)a4 + 11) )
  {
    *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 11);
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, __int128 *))a3->lpVtbl->SetValue)(
           a3,
           &DEVPKEY_Device_MatchingDeviceId,
           &v40);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7104;
      goto LABEL_7;
    }
  }
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 12);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &DEVPKEY_Device_DriverInfPath,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7108;
    goto LABEL_7;
  }
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 13);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &DEVPKEY_Device_DriverInfSection,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7110;
    goto LABEL_7;
  }
  if ( *((_DWORD *)a4 + 61) )
  {
    if ( *((_QWORD *)a4 + 17) )
    {
      *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 17);
      v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
             a3,
             PKEY_AudioEndpoint_HardwareId,
             &v40);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 7116;
        goto LABEL_7;
      }
    }
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 11;
  v12 = *((_BYTE *)a4 + 288) == 0;
  WORD4(v40) = -1;
  if ( v12 )
    WORD4(v40) = 0;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         PKEY_AudioEndpoint_HasNonInboxInf,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7124;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 64;
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 18);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &DEVPKEY_Device_InstallDate,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7132;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 11;
  v12 = *((_BYTE *)a4 + 289) == 0;
  WORD4(v40) = -1;
  if ( v12 )
    WORD4(v40) = 0;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &DEVPKEY_Device_IsRebootRequired,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7137;
    goto LABEL_7;
  }
  GetJackProperties(*((struct IConnector **)a4 + 1), 0, v43, (int *)&v42, &v46, (unsigned int *)&v44);
  v8 = IsPnPDevNodeRemovable(*((const unsigned __int16 **)a4 + 5), &v45);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -536870389 )
    {
      v9 = -536870389;
      goto LABEL_166;
    }
    v10 = 7144;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 72;
  v13 = *((_QWORD *)a4 + 23) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v13 )
    v13 = *((_QWORD *)a4 + 24) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    v14 = *(_OWORD *)((char *)a4 + 184);
  }
  else
  {
    v15 = *((_QWORD *)a4 + 21) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( !v15 )
      v15 = *((_QWORD *)a4 + 22) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
      }
      v14 = *(_OWORD *)((char *)a4 + 168);
    }
    else
    {
      if ( !v45 && !(_DWORD)v42 && v43[0] )
      {
        v16 = 0;
        *(_QWORD *)v43 = 0;
        v42 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
          v16 = *(_QWORD *)v43;
        }
        *(_QWORD *)v43 = 0;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v17 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, int *))a2->lpVtbl->QueryInterface)(
                a2,
                &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21,
                v43);
        v9 = v17;
        if ( v17 >= 0 )
        {
          v19 = *(_QWORD *)v43;
          v20 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(**(_QWORD **)v43 + 56LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v37,
            0);
          v17 = v20(v19, &v37);
          v9 = v17;
          if ( v17 >= 0 )
          {
            v17 = StringCbLengthW(v37, 0x104u, (unsigned __int64 *)&v42);
            v9 = v17;
            if ( v17 >= 0 )
            {
              v17 = GenerateClass5Guid(&GUID_AUDIOENDPOINTBUILDER_CONTAINER_ID_NAMESPACE, v37, (unsigned int)v42, &v49);
              v9 = v17;
              if ( v17 >= 0 )
              {
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v43);
                goto LABEL_92;
              }
              v18 = 7176;
            }
            else
            {
              v18 = 7175;
            }
          }
          else
          {
            v18 = 7174;
          }
        }
        else
        {
          v18 = 7173;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v17,
          v36);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v43);
        goto LABEL_9;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
      }
      v14 = *(_OWORD *)((char *)a4 + 152);
    }
  }
  v49 = v14;
LABEL_92:
  *((_QWORD *)&v40 + 1) = &v49;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &PKEY_Device_ContainerId,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7185;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 31;
  v8 = CoCreateGuid(&pguid);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7194;
    goto LABEL_7;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v8 = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7196;
    goto LABEL_7;
  }
  *((_QWORD *)&v40 + 1) = pv;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         PKEY_AudioEndpoint_PersistentId,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7203;
    goto LABEL_7;
  }
  v40 = 0;
  v41 = 0;
  v21 = *((_QWORD *)a4 + 23) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v21 )
    v21 = *((_QWORD *)a4 + 24) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v21 )
  {
    v22 = *((_QWORD *)a4 + 8);
    if ( v22 )
    {
      LOWORD(v40) = 31;
      *((_QWORD *)&v40 + 1) = v22;
      v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
             a3,
             PKEY_Endpoint_DeviceInterface_FriendlyName,
             &v40);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 7211;
        goto LABEL_7;
      }
    }
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 31;
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 15);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &PKEY_Device_EnumeratorName,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7219;
    goto LABEL_7;
  }
  v23 = *((_QWORD *)a4 + 27);
  if ( v23 )
  {
    v40 = 0;
    v41 = v23;
    DWORD2(v40) = 72;
    LOWORD(v40) = 65;
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
           a3,
           PKEY_Endpoint_KsComponentId,
           &v40);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7230;
      goto LABEL_7;
    }
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 19;
  DWORD2(v40) = *((_DWORD *)a4 + 57);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &PKEY_AudioEndpoint_FormFactor,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7238;
    goto LABEL_7;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v8 = StringFromCLSID((const IID *const)((char *)a4 + 20), &lpsz);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7241;
    goto LABEL_7;
  }
  *(_QWORD *)&v40 = 31;
  v41 = 0;
  *((_QWORD *)&v40 + 1) = lpsz;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &PKEY_AudioEndpoint_JackSubType,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7246;
    goto LABEL_7;
  }
  v24 = *((_QWORD *)a4 + 34) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v24 )
    v24 = *((_QWORD *)a4 + 35) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v24 )
  {
    v42 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v42,
      0);
    v25 = StringFromCLSID((const IID *const)a4 + 17, &v42);
    v9 = v25;
    if ( v25 < 0 )
    {
      v26 = 7252;
LABEL_122:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v25,
        v36);
      v27 = v42;
      goto LABEL_123;
    }
    *(_QWORD *)&v40 = 31;
    v41 = 0;
    *((_QWORD *)&v40 + 1) = v42;
    v25 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
            a3,
            PKEY_SWD_InterfaceClass,
            &v40);
    v9 = v25;
    if ( v25 < 0 )
    {
      v26 = 7257;
      goto LABEL_122;
    }
    if ( v42 )
      CoTaskMemFree(v42);
  }
  if ( (unsigned int)(*((_DWORD *)a4 + 57) - 7) <= 1 )
  {
    v28 = CoTaskMemAlloc(0x2Cu);
    if ( !v28 )
    {
      v9 = -2147024882;
      v11 = 2147942414LL;
      v10 = 7272;
      goto LABEL_8;
    }
    *v28 = 16;
    v28[1] = 2;
    v28[2] = 2;
    v28[3] = 146;
    *((_QWORD *)v28 + 2) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
    v28[6] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
    v28[7] = 8;
    *((_QWORD *)v28 + 4) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
    v28[10] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
    LOWORD(pvar[0]) = 65;
    LODWORD(pvar[1]) = 44;
    v48 = v28;
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a3->lpVtbl->SetValue)(
           a3,
           PKEY_Endpoint_SPDIFFormatSupport,
           pvar);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7288;
      goto LABEL_7;
    }
  }
  v40 = 0;
  v41 = 0;
  LOWORD(v40) = 31;
  *((_QWORD *)&v40 + 1) = *((_QWORD *)a4 + 14);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         &PKEY_DeviceClass_IconPath,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7296;
    goto LABEL_7;
  }
  v40 = 0;
  LOWORD(v40) = 65;
  DWORD2(v40) = *((_DWORD *)this + 24);
  v41 = *((_QWORD *)this + 11);
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
         a3,
         PKEY_AudioEndpoint_Version,
         &v40);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 7302;
    goto LABEL_7;
  }
  if ( v46 )
  {
    v40 = 0;
    v41 = 0;
    LOWORD(v40) = 19;
    DWORD2(v40) = (_DWORD)v44;
    v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
           a3,
           PKEY_AudioEndpoint_ConfigId,
           &v40);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7310;
      goto LABEL_7;
    }
  }
  if ( *((_DWORD *)a4 + 59) )
  {
    v8 = CAvEndpointBuilder::SetBluetoothProperties(v29, a2, a4);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 7316;
      goto LABEL_7;
    }
  }
  if ( *((_DWORD *)a4 + 63) )
  {
    v30 = *((_DWORD *)a4 + 58);
    if ( v30 )
    {
      v44 = 0;
      v40 = 0;
      v41 = 0;
      LOWORD(v40) = 19;
      DWORD2(v40) = v30;
      v31 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, __int128 *))a3->lpVtbl->SetValue)(
              a3,
              &DEVPKEY_Device_SessionId,
              &v40);
      v9 = v31;
      if ( v31 < 0 )
      {
        v32 = 7327;
LABEL_148:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v31,
          v36);
        v27 = v44;
LABEL_123:
        if ( v27 )
          CoTaskMemFree(v27);
        goto LABEL_9;
      }
      v40 = 0;
      v41 = 0;
      LOWORD(v40) = 11;
      WORD4(v40) = -1;
      v31 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
              a3,
              PKEY_ApxEndpoint_IsSessionIdLocked,
              &v40);
      v9 = v31;
      if ( v31 < 0 )
      {
        v32 = 7332;
        goto LABEL_148;
      }
      GetId = a2->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v44,
        0);
      v31 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &v44);
      v9 = v31;
      if ( v31 < 0 )
      {
        v32 = 7334;
        goto LABEL_148;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v34, *((_DWORD *)a4 + 58), (__int64)v44);
      }
      if ( v44 )
        CoTaskMemFree(v44);
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v37 )
    CoTaskMemFree(v37);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  v9 = 0;
LABEL_166:
  PropVariantClear(pvar);
  return v9;
}

```

## disassembly

```asm
0x18000c0d0  push    rbp
0x18000c0d2  push    rbx
0x18000c0d3  push    rsi
0x18000c0d4  push    rdi
0x18000c0d5  push    r12
0x18000c0d7  push    r13
0x18000c0d9  push    r14
0x18000c0db  push    r15
0x18000c0dd  lea     rbp, [rsp-1Fh]
0x18000c0e2  sub     rsp, 0C8h
0x18000c0e9  mov     rax, cs:__security_cookie
0x18000c0f0  xor     rax, rsp
0x18000c0f3  mov     [rbp+57h+var_48], rax
0x18000c0f7  mov     r14, r9
0x18000c0fa  mov     rsi, r8
0x18000c0fd  mov     r12, rdx
0x18000c100  mov     r13, rcx
0x18000c103  xorps   xmm0, xmm0
0x18000c106  xor     eax, eax
0x18000c108  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000c10c  mov     [rbp+57h+var_70], rax
0x18000c110  xor     edi, edi
0x18000c112  mov     [rbp+57h+lpsz], rdi
0x18000c116  mov     [rbp+57h+var_98], edi
0x18000c119  mov     dword ptr [rbp+57h+var_A0], edi
0x18000c11c  mov     [rbp+57h+var_88], edi
0x18000c11f  mov     [rbp+57h+var_D0], rdi
0x18000c123  movups  [rbp+57h+var_68], xmm0
0x18000c127  xorps   xmm1, xmm1
0x18000c12a  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm1
0x18000c12e  mov     [rbp+57h+pv], rdi
0x18000c132  mov     [rbp+57h+var_84], edi
0x18000c135  mov     dword ptr [rbp+57h+var_90], edi
0x18000c138  lea     edx, [rax+0Bh]
0x18000c13b  or      ecx, 0FFFFFFFFh
0x18000c13e  cmp     [r9+0F4h], edi
0x18000c145  jz      short loc_18000C184
0x18000c147  movups  [rbp+57h+var_B8], xmm0
0x18000c14b  mov     [rbp+57h+var_A8], rax
0x18000c14f  mov     word ptr [rbp+57h+var_B8], dx
0x18000c153  mov     word ptr [rbp+57h+var_B8+8], cx
0x18000c157  mov     rax, [r8]
0x18000c15a  lea     r8, [rbp+57h+var_B8]
0x18000c15e  lea     rdx, PKEY_Endpoint_IsUSB
0x18000c165  mov     rcx, rsi
0x18000c168  mov     rax, [rax+30h]
0x18000c16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c171  mov     ebx, eax
0x18000c173  test    eax, eax
0x18000c175  jns     short loc_18000C17E
0x18000c177  mov     edx, 1B8Fh
0x18000c17c  jmp     short loc_18000C1CB
0x18000c17e  or      ecx, 0FFFFFFFFh
0x18000c181  lea     edx, [rcx+0Ch]
0x18000c184  cmp     [r14+0F8h], edi
0x18000c18b  jz      loc_18000C217
0x18000c191  xorps   xmm0, xmm0
0x18000c194  xor     eax, eax
0x18000c196  movups  [rbp+57h+var_B8], xmm0
0x18000c19a  mov     [rbp+57h+var_A8], rax
0x18000c19e  mov     word ptr [rbp+57h+var_B8], dx
0x18000c1a2  mov     word ptr [rbp+57h+var_B8+8], cx
0x18000c1a6  mov     rax, [rsi]
0x18000c1a9  lea     r8, [rbp+57h+var_B8]
0x18000c1ad  lea     rdx, PKEY_Endpoint_IsSideband
0x18000c1b4  mov     rcx, rsi
0x18000c1b7  mov     rax, [rax+30h]
0x18000c1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c0  mov     ebx, eax
0x18000c1c2  test    eax, eax
0x18000c1c4  jns     short loc_18000C217
0x18000c1c6  mov     edx, 1B98h; void *
0x18000c1cb  mov     r9d, eax; char *
0x18000c1ce  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000c1d5  mov     rcx, [rbp+5Fh]; this
0x18000c1d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1de  nop
0x18000c1df  mov     rcx, [rbp+57h+pv]; pv
0x18000c1e3  test    rcx, rcx
0x18000c1e6  jz      short loc_18000C1EF
0x18000c1e8  call    cs:__imp_CoTaskMemFree
0x18000c1ee  nop
0x18000c1ef  mov     rcx, [rbp+57h+var_D0]; pv
0x18000c1f3  test    rcx, rcx
0x18000c1f6  jz      short loc_18000C1FF
0x18000c1f8  call    cs:__imp_CoTaskMemFree
0x18000c1fe  nop
0x18000c1ff  mov     rcx, [rbp+57h+lpsz]; pv
0x18000c203  test    rcx, rcx
0x18000c206  jz      loc_18000CE76
0x18000c20c  call    cs:__imp_CoTaskMemFree
0x18000c212  jmp     loc_18000CE76
0x18000c217  xorps   xmm0, xmm0
0x18000c21a  xor     eax, eax
0x18000c21c  movups  [rbp+57h+var_B8], xmm0
0x18000c220  mov     [rbp+57h+var_A8], rax
0x18000c224  lea     r15d, [rax+1Fh]
0x18000c228  mov     word ptr [rbp+57h+var_B8], r15w
0x18000c22d  mov     rax, [r14+38h]
0x18000c231  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c235  mov     rax, [rsi]
0x18000c238  lea     r8, [rbp+57h+var_B8]
0x18000c23c  lea     rdx, PKEY_Device_DeviceDesc
0x18000c243  mov     rcx, rsi
0x18000c246  mov     rax, [rax+30h]
0x18000c24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24f  mov     ebx, eax
0x18000c251  test    eax, eax
0x18000c253  jns     short loc_18000C25F
0x18000c255  mov     edx, 1BA1h
0x18000c25a  jmp     loc_18000C1CB
0x18000c25f  xorps   xmm0, xmm0
0x18000c262  xor     eax, eax
0x18000c264  movups  [rbp+57h+var_B8], xmm0
0x18000c268  mov     [rbp+57h+var_A8], rax
0x18000c26c  mov     word ptr [rbp+57h+var_B8], r15w
0x18000c271  mov     rax, [r14+48h]
0x18000c275  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c279  mov     rax, [rsi]
0x18000c27c  lea     r8, [rbp+57h+var_B8]
0x18000c280  lea     rdx, PKEY_Endpoint_Device_NAME
0x18000c287  mov     rcx, rsi
0x18000c28a  mov     rax, [rax+30h]
0x18000c28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c293  mov     ebx, eax
0x18000c295  test    eax, eax
0x18000c297  jns     short loc_18000C2A3
0x18000c299  mov     edx, 1BA9h
0x18000c29e  jmp     loc_18000C1CB
0x18000c2a3  xorps   xmm0, xmm0
0x18000c2a6  xor     eax, eax
0x18000c2a8  movups  [rbp+57h+var_B8], xmm0
0x18000c2ac  mov     [rbp+57h+var_A8], rax
0x18000c2b0  mov     word ptr [rbp+57h+var_B8], r15w
0x18000c2b5  mov     rax, [r14+28h]
0x18000c2b9  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c2bd  mov     rax, [rsi]
0x18000c2c0  lea     r8, [rbp+57h+var_B8]
0x18000c2c4  lea     rdx, PKEY_Endpoint_Devnode
0x18000c2cb  mov     rcx, rsi
0x18000c2ce  mov     rax, [rax+30h]
0x18000c2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d7  mov     ebx, eax
0x18000c2d9  test    eax, eax
0x18000c2db  jns     short loc_18000C2E7
0x18000c2dd  mov     edx, 1BAFh
0x18000c2e2  jmp     loc_18000C1CB
0x18000c2e7  mov     rax, [r14+30h]
0x18000c2eb  test    rax, rax
0x18000c2ee  jz      short loc_18000C31E
0x18000c2f0  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c2f4  mov     rax, [rsi]
0x18000c2f7  lea     r8, [rbp+57h+var_B8]
0x18000c2fb  lea     rdx, PKEY_Endpoint_SidebandDevnode
0x18000c302  mov     rcx, rsi
0x18000c305  mov     rax, [rax+30h]
0x18000c309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c30e  mov     ebx, eax
0x18000c310  test    eax, eax
0x18000c312  jns     short loc_18000C31E
0x18000c314  mov     edx, 1BB5h
0x18000c319  jmp     loc_18000C1CB
0x18000c31e  mov     rax, [r14+50h]
0x18000c322  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c326  mov     rax, [rsi]
0x18000c329  lea     r8, [rbp+57h+var_B8]
0x18000c32d  lea     rdx, DEVPKEY_Device_DriverNodeStrongName
0x18000c334  mov     rcx, rsi
0x18000c337  mov     rax, [rax+30h]
0x18000c33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c340  mov     ebx, eax
0x18000c342  test    eax, eax
0x18000c344  jns     short loc_18000C350
0x18000c346  mov     edx, 1BBAh
0x18000c34b  jmp     loc_18000C1CB
0x18000c350  mov     rax, [r14+58h]
0x18000c354  test    rax, rax
0x18000c357  jz      short loc_18000C387
0x18000c359  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c35d  mov     rax, [rsi]
0x18000c360  lea     r8, [rbp+57h+var_B8]
0x18000c364  lea     rdx, DEVPKEY_Device_MatchingDeviceId
0x18000c36b  mov     rcx, rsi
0x18000c36e  mov     rax, [rax+30h]
0x18000c372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c377  mov     ebx, eax
0x18000c379  test    eax, eax
0x18000c37b  jns     short loc_18000C387
0x18000c37d  mov     edx, 1BC0h
0x18000c382  jmp     loc_18000C1CB
0x18000c387  mov     rax, [r14+60h]
0x18000c38b  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c38f  mov     rax, [rsi]
0x18000c392  lea     r8, [rbp+57h+var_B8]
0x18000c396  lea     rdx, DEVPKEY_Device_DriverInfPath
0x18000c39d  mov     rcx, rsi
0x18000c3a0  mov     rax, [rax+30h]
0x18000c3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3a9  mov     ebx, eax
0x18000c3ab  test    eax, eax
0x18000c3ad  jns     short loc_18000C3B9
0x18000c3af  mov     edx, 1BC4h
0x18000c3b4  jmp     loc_18000C1CB
0x18000c3b9  mov     rax, [r14+68h]
0x18000c3bd  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c3c1  mov     rax, [rsi]
0x18000c3c4  lea     r8, [rbp+57h+var_B8]
0x18000c3c8  lea     rdx, DEVPKEY_Device_DriverInfSection
0x18000c3cf  mov     rcx, rsi
0x18000c3d2  mov     rax, [rax+30h]
0x18000c3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3db  mov     ebx, eax
0x18000c3dd  test    eax, eax
0x18000c3df  jns     short loc_18000C3EB
0x18000c3e1  mov     edx, 1BC6h
0x18000c3e6  jmp     loc_18000C1CB
0x18000c3eb  cmp     [r14+0F4h], edi
0x18000c3f2  jz      short loc_18000C42E
0x18000c3f4  mov     rax, [r14+88h]
0x18000c3fb  test    rax, rax
0x18000c3fe  jz      short loc_18000C42E
0x18000c400  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c404  mov     rax, [rsi]
0x18000c407  lea     r8, [rbp+57h+var_B8]
0x18000c40b  lea     rdx, PKEY_AudioEndpoint_HardwareId
0x18000c412  mov     rcx, rsi
0x18000c415  mov     rax, [rax+30h]
0x18000c419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c41e  mov     ebx, eax
0x18000c420  test    eax, eax
0x18000c422  jns     short loc_18000C42E
0x18000c424  mov     edx, 1BCCh
0x18000c429  jmp     loc_18000C1CB
0x18000c42e  xorps   xmm0, xmm0
0x18000c431  xor     eax, eax
0x18000c433  movups  [rbp+57h+var_B8], xmm0
0x18000c437  mov     [rbp+57h+var_A8], rax
0x18000c43b  mov     eax, 0Bh
0x18000c440  mov     word ptr [rbp+57h+var_B8], ax
0x18000c444  or      r15d, 0FFFFFFFFh
0x18000c448  cmp     [r14+120h], dil
0x18000c44f  mov     word ptr [rbp+57h+var_B8+8], r15w
0x18000c454  jnz     short loc_18000C45A
0x18000c456  mov     word ptr [rbp+57h+var_B8+8], di
0x18000c45a  mov     rax, [rsi]
0x18000c45d  lea     r8, [rbp+57h+var_B8]
0x18000c461  lea     rdx, PKEY_AudioEndpoint_HasNonInboxInf
0x18000c468  mov     rcx, rsi
0x18000c46b  mov     rax, [rax+30h]
0x18000c46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c474  mov     ebx, eax
0x18000c476  test    eax, eax
0x18000c478  jns     short loc_18000C484
0x18000c47a  mov     edx, 1BD4h
0x18000c47f  jmp     loc_18000C1CB
0x18000c484  xorps   xmm0, xmm0
0x18000c487  xor     eax, eax
0x18000c489  movups  [rbp+57h+var_B8], xmm0
0x18000c48d  mov     [rbp+57h+var_A8], rax
0x18000c491  mov     eax, 40h ; '@'
0x18000c496  mov     word ptr [rbp+57h+var_B8], ax
0x18000c49a  mov     rax, [r14+90h]
0x18000c4a1  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18000c4a5  mov     rax, [rsi]
0x18000c4a8  lea     r8, [rbp+57h+var_B8]
0x18000c4ac  lea     rdx, DEVPKEY_Device_InstallDate
0x18000c4b3  mov     rcx, rsi
0x18000c4b6  mov     rax, [rax+30h]
0x18000c4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4bf  mov     ebx, eax
0x18000c4c1  test    eax, eax
0x18000c4c3  jns     short loc_18000C4CF
0x18000c4c5  mov     edx, 1BDCh
0x18000c4ca  jmp     loc_18000C1CB
0x18000c4cf  xorps   xmm0, xmm0
0x18000c4d2  xor     eax, eax
0x18000c4d4  movups  [rbp+57h+var_B8], xmm0
0x18000c4d8  mov     [rbp+57h+var_A8], rax
0x18000c4dc  mov     eax, 0Bh
0x18000c4e1  mov     word ptr [rbp+57h+var_B8], ax
0x18000c4e5  cmp     [r14+121h], dil
0x18000c4ec  mov     word ptr [rbp+57h+var_B8+8], r15w
0x18000c4f1  jnz     short loc_18000C4F7
0x18000c4f3  mov     word ptr [rbp+57h+var_B8+8], di
0x18000c4f7  mov     rax, [rsi]
0x18000c4fa  lea     r8, [rbp+57h+var_B8]
0x18000c4fe  lea     rdx, DEVPKEY_Device_IsRebootRequired
0x18000c505  mov     rcx, rsi
0x18000c508  mov     rax, [rax+30h]
0x18000c50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c511  mov     ebx, eax
0x18000c513  test    eax, eax
0x18000c515  jns     short loc_18000C521
0x18000c517  mov     edx, 1BE1h
0x18000c51c  jmp     loc_18000C1CB
0x18000c521  lea     rax, [rbp+57h+var_90]
0x18000c525  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18000c52a  lea     rax, [rbp+57h+var_84]
0x18000c52e  mov     [rsp+100h+var_E0], rax; int
0x18000c533  lea     r9, [rbp+57h+var_A0]; int *
  ... truncated ...
```
