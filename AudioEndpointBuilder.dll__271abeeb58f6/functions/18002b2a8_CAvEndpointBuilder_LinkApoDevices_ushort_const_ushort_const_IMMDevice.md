# CAvEndpointBuilder::LinkApoDevices(ushort const *,ushort const *,IMMDevice *)

- ea: `0x18002b2a8`
- end: `0x18002c78f`
- name: `?LinkApoDevices@CAvEndpointBuilder@@AEAAJPEBG0PEAUIMMDevice@@@Z`
- size: `5351`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *this, unsigned __int16 *, unsigned __int16 *, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x1800017f4`
- `0x180001e40`
- `0x180001edc`
- `0x18000207c`
- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001b5f8`
- `0x18001deb0`
- `0x18001ef04`
- `0x18001f374`
- `0x180021030`
- `0x180023d28`
- `0x180024ca0`
- `0x18002707c`
- `0x18002b2a8`
- `0x180033464`
- `0x1800338e0`
- `0x180033a98`
- `0x18003e920`
- `0x18003f780`
- `0x1800486a0`
- `0x1800486dc`
- `0x180048f74`
- `0x180054d9c`
- `0x18005de98`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c40b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c518`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c658`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c40b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c518`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c658`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_Size` at `0x18002bf8d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_Size` at `0x18002bf8d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x18002beb8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x18002beb8`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18002c317`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18002c317`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18002c1bf`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18002c1bf`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18002bc85`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18002bc85`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bc96`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bd82`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bec3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bf98`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002c1ca`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bc96`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bd82`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bec3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002bf98`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002c1ca`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Sibling` at `0x18002c68c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Sibling` at `0x18002c68c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Child` at `0x18002bd77`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Child` at `0x18002bd77`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b6a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b895`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c107`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c1fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c41a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c527`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c667`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b6a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b895`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c107`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c1fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c41a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c527`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c667`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bdd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c0c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c11b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c6a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bdd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c0c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c11b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c53b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c6a7`

## string_xrefs

- `0x18002b568`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b5d4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b68e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b8e3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b9c9`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002ba94`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002bb7f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002bcaf`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002bdb6`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002bfb1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002c0ed`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002c1e3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002c3ec`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002c4f9`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CAvEndpointBuilder::LinkApoDevices(
        CAvEndpointBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IMMDevice *a4)
{
  const struct _tlgProvider_t *v4; // rax
  int v5; // r8d
  int v6; // r9d
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  PROPERTYKEY *i; // rbx
  int v15; // eax
  unsigned int v16; // edi
  const struct _tlgProvider_t *v17; // rax
  int v18; // r8d
  int v19; // r9d
  int j; // eax
  const struct _tlgProvider_t *v21; // rax
  int v22; // r8d
  int v23; // r9d
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  int v31; // eax
  int v32; // eax
  struct IMMDevice *v33; // rdi
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  int v35; // eax
  const struct _tlgProvider_t *v36; // rax
  int v37; // r8d
  int v38; // r9d
  CONFIGRET v39; // eax
  DWORD v40; // eax
  CONFIGRET Child; // eax
  signed int v42; // eax
  CONFIGRET DevNode_PropertyW; // eax
  signed int v44; // eax
  int v45; // ebx
  const struct _tlgProvider_t *v46; // rax
  int v47; // r8d
  int v48; // r9d
  CONFIGRET Device_ID_Size; // eax
  DWORD v50; // eax
  PROPVARIANT *unique_cotaskmem; // rax
  PROPVARIANT v52; // rdx
  void *v53; // rcx
  CONFIGRET Device_IDW; // eax
  DWORD v55; // eax
  const struct _tlgProvider_t *v56; // rax
  int v57; // r8d
  int v58; // r9d
  const unsigned __int16 **v59; // rbx
  const struct _tlgProvider_t *v60; // rax
  int v61; // r8d
  int v62; // r9d
  const struct _tlgProvider_t *v63; // rax
  int v64; // r8d
  int v65; // r9d
  int ApoDeviceIdPKey; // eax
  int v67; // eax
  const struct _tlgProvider_t *v68; // rax
  int v69; // r8d
  int v70; // r9d
  const struct _tlgProvider_t *v71; // rax
  unsigned int PropertyBufferSize; // [rsp+20h] [rbp-2B8h]
  unsigned int PropertyBufferSizea; // [rsp+20h] [rbp-2B8h]
  int PropertyBufferSizeb; // [rsp+20h] [rbp-2B8h]
  __int128 v75; // [rsp+40h] [rbp-298h] BYREF
  __int64 v76; // [rsp+50h] [rbp-288h]
  DEVNODE dnDevInst; // [rsp+58h] [rbp-280h] BYREF
  __int64 v78; // [rsp+60h] [rbp-278h] BYREF
  __int64 *v79; // [rsp+68h] [rbp-270h] BYREF
  __int64 v80; // [rsp+70h] [rbp-268h] BYREF
  struct IMMDevice *v81; // [rsp+78h] [rbp-260h] BYREF
  __int64 v82; // [rsp+80h] [rbp-258h] BYREF
  ULONG pulLen; // [rsp+88h] [rbp-250h] BYREF
  DEVNODE pdnDevInst; // [rsp+8Ch] [rbp-24Ch] BYREF
  LPVOID pv; // [rsp+90h] [rbp-248h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+98h] [rbp-240h] BYREF
  _QWORD v87[2]; // [rsp+A0h] [rbp-238h] BYREF
  char v88; // [rsp+B0h] [rbp-228h]
  LPVOID v89; // [rsp+B8h] [rbp-220h] BYREF
  int v90[2]; // [rsp+C0h] [rbp-218h] BYREF
  HKEY phkDevice; // [rsp+C8h] [rbp-210h] BYREF
  unsigned int v92; // [rsp+D0h] [rbp-208h] BYREF
  ULONG v93; // [rsp+D4h] [rbp-204h] BYREF
  unsigned __int16 *v94; // [rsp+D8h] [rbp-200h] BYREF
  PROPVARIANT v95[2]; // [rsp+E0h] [rbp-1F8h] BYREF
  __int64 v96; // [rsp+F0h] [rbp-1E8h]
  _BYTE v97[8]; // [rsp+F8h] [rbp-1E0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+100h] [rbp-1D8h] BYREF
  __int64 v99; // [rsp+110h] [rbp-1C8h]
  BYTE PropertyBuffer[24]; // [rsp+118h] [rbp-1C0h] BYREF
  PROPERTYKEY v101[18]; // [rsp+130h] [rbp-1A8h] BYREF
  char v102; // [rsp+298h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]
  HKEY v104; // [rsp+2E8h] [rbp+10h] BYREF

  v104 = (HKEY)a2;
  v94 = a3;
  v81 = a4;
  v101[0] = PKEY_FX_PreMixEffectClsid;
  v101[1] = PKEY_FX_PostMixEffectClsid;
  v101[2] = PKEY_FX_StreamEffectClsid;
  v101[3] = PKEY_FX_ModeEffectClsid;
  v101[4] = PKEY_FX_EndpointEffectClsid;
  v101[5] = PKEY_FX_KeywordDetector_StreamEffectClsid;
  v101[6] = PKEY_FX_KeywordDetector_ModeEffectClsid;
  v101[7] = PKEY_FX_KeywordDetector_EndpointEffectClsid;
  v101[8] = PKEY_FX_Offload_StreamEffectClsid;
  v101[9] = PKEY_FX_Offload_ModeEffectClsid;
  v101[10] = PKEY_CompositeFX_StreamEffectClsid;
  v101[11] = PKEY_CompositeFX_ModeEffectClsid;
  v101[12] = PKEY_CompositeFX_EndpointEffectClsid;
  v101[13] = PKEY_CompositeFX_KeywordDetector_StreamEffectClsid;
  v101[14] = PKEY_CompositeFX_KeywordDetector_ModeEffectClsid;
  v101[15] = PKEY_CompositeFX_KeywordDetector_EndpointEffectClsid;
  v101[16] = PKEY_CompositeFX_Offload_StreamEffectClsid;
  v101[17] = PKEY_CompositeFX_Offload_ModeEffectClsid;
  v4 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v4 > 4u )
  {
    v89 = v94;
    phkDevice = v104;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)&word_180075DFE,
      v5,
      v6,
      (__int64)&phkDevice,
      (__int64)&v89);
  }
  v87[0] = &v104;
  v87[1] = &v94;
  v88 = 1;
  v79 = 0;
  v7 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v81, &v79);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E9C,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v7,
      PropertyBufferSize);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
    v88 = 0;
    lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
    return v8;
  }
  v78 = 0;
  v10 = *v79;
  v78 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v10 + 40))(v79, 0, &v78);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA0,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v11,
      PropertyBufferSize);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
    v88 = 0;
    lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
    return v12;
  }
  v13 = v78;
  if ( !v78 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
    v88 = 0;
    lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
    return 0;
  }
  v75 = 0;
  v76 = 0;
  for ( i = v101; i != (PROPERTYKEY *)&v102; ++i )
  {
    *(_OWORD *)pvar = 0;
    v99 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v13 + 40LL))(v13, i, pvar);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EAD,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v15,
        PropertyBufferSize);
      PropVariantClear(pvar);
      if ( (_QWORD)v75 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v75,
          *((_QWORD *)&v75 + 1));
        std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
        v75 = 0;
        v76 = 0;
      }
LABEL_116:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
      v88 = 0;
      lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
      return v16;
    }
    if ( LOWORD(pvar[0]) )
    {
      if ( LOWORD(pvar[0]) == 31 )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::emplace_back<unsigned short * &>(
          &v75,
          &pvar[1]);
        v24 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v24 > 4u )
        {
          v89 = pvar[1];
          pdnDevInst = i->pid;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v24,
            (unsigned int)&unk_180075DC8,
            v25,
            v26,
            (__int64)&pdnDevInst,
            (__int64)&v89);
        }
        pvar[1] = 0;
      }
      else if ( LOWORD(pvar[0]) == 4127 )
      {
        for ( j = (int)pvar[1]; j; j = --LODWORD(pvar[1]) )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::emplace_back<unsigned short * &>(
            &v75,
            v99 + 8LL * (unsigned int)(j - 1));
          v21 = AudioEndpointBuilderTelemetryProvider::Provider();
          if ( *(_DWORD *)v21 > 4u )
          {
            v89 = *(LPVOID *)(v99 + 8LL * (unsigned int)(LODWORD(pvar[1]) - 1));
            PropertyType = i->pid;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v21,
              (unsigned int)byte_180075D89,
              v22,
              v23,
              (__int64)&PropertyType,
              (__int64)&v89);
          }
        }
      }
      else
      {
        v17 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v17 > 4u )
        {
          LOWORD(dnDevInst) = pvar[0];
          pdnDevInst = i->pid;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
            (_DWORD)v17,
            (unsigned int)word_180075D4A,
            v18,
            v19,
            (__int64)&pdnDevInst,
            (__int64)&dnDevInst);
        }
      }
    }
    PropVariantClear(pvar);
    v13 = v78;
  }
  v80 = 0;
  v27 = *v79;
  v80 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v27 + 40))(v79, 2, &v80);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE0,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v28,
      PropertyBufferSize);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    goto LABEL_90;
  }
  if ( !((__int64)(*((_QWORD *)&v75 + 1) - v75) >> 3) )
  {
LABEL_131:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
    v88 = 0;
    lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
    return 0;
  }
  v82 = 0;
  lpVtbl = g_DeviceEnumerator->lpVtbl;
  v82 = 0;
  v31 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, __int64 *))lpVtbl[1].Release)(
          g_DeviceEnumerator,
          v94,
          &v82);
  v29 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v31,
      PropertyBufferSize);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    goto LABEL_90;
  }
  v81 = 0;
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v81);
  v32 = wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v82, &v81);
  v29 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v32,
      PropertyBufferSize);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    goto LABEL_90;
  }
  pv = 0;
  v33 = v81;
  OpenPropertyStore = v81->lpVtbl->OpenPropertyStore;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v35 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))OpenPropertyStore)(v33, &pv);
  v29 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EEC,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v35,
      PropertyBufferSize);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    goto LABEL_90;
  }
  v36 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v36 > 4u )
  {
    v89 = pv;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v36,
      (unsigned int)byte_180075D0B,
      v37,
      v38,
      (__int64)&v89);
  }
  pdnDevInst = 0;
  v39 = CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)pv, 0);
  v40 = CM_MapCrToWin32Err(v39, 0x507u);
  if ( v40 )
  {
    v29 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1EF6,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)v40,
            PropertyBufferSize);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    goto LABEL_90;
  }
  dnDevInst = 0;
  Child = CM_Get_Child(&dnDevInst, pdnDevInst, 0);
  v42 = CM_MapCrToWin32Err(Child, 0x507u);
  v29 = v42;
  if ( v42 > 0 )
    v29 = (unsigned __int16)v42 | 0x80070000;
  if ( (v29 & 0x80000000) != 0 )
  {
    if ( v29 != -2147023728 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EFB,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)v29,
        PropertyBufferSize);
      if ( pv )
        CoTaskMemFree(pv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
      if ( (_QWORD)v75 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v75,
          *((_QWORD *)&v75 + 1));
        std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
        v75 = 0;
        v76 = 0;
      }
      goto LABEL_90;
    }
LABEL_128:
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    goto LABEL_131;
  }
  while ( 1 )
  {
    *(_OWORD *)PropertyBuffer = 0;
    v93 = 16;
    PropertyType = 0;
    DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                          dnDevInst,
                          &DEVPKEY_Device_ClassGuid,
                          &PropertyType,
                          PropertyBuffer,
                          &v93,
                          0);
    v44 = CM_MapCrToWin32Err(DevNode_PropertyW, 0x507u);
    v45 = v44;
    if ( v44 > 0 )
      v45 = (unsigned __int16)v44 | 0x80070000;
    v46 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v46 > 4u )
    {
      *(_QWORD *)v90 = PropertyBuffer;
      pulLen = PropertyType;
      v92 = v45;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (_DWORD)v46,
        (unsigned int)byte_180075CB5,
        v47,
        v48,
        (__int64)&v92,
        (__int64)&pulLen,
        (__int64)v90);
    }
    if ( v45 >= 0 && PropertyType == 13 && !memcmp_0(PropertyBuffer, &GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4, 0x10u) )
      break;
LABEL_126:
    if ( !((__int64)(*((_QWORD *)&v75 + 1) - v75) >> 3) || CM_Get_Sibling(&dnDevInst, dnDevInst, 0) )
      goto LABEL_128;
  }
  pulLen = 0;
  Device_ID_Size = CM_Get_Device_ID_Size(&pulLen, dnDevInst, 0);
  v50 = CM_MapCrToWin32Err(Device_ID_Size, 0x507u);
  if ( v50 )
  {
    v29 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1F1F,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)v50,
            PropertyBufferSizea);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    goto LABEL_90;
  }
  ++pulLen;
  *(_OWORD *)v95 = 0;
  v96 = 0;
  LOWORD(v95[0]) = 31;
  unique_cotaskmem = (PROPVARIANT *)wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(&v89, pulLen);
  v52 = *unique_cotaskmem;
  *unique_cotaskmem = 0;
  v95[1] = v52;
  v53 = v89;
  v89 = 0;
  if ( v53 )
  {
    CoTaskMemFree(v53);
    v52 = v95[1];
  }
  if ( !v52 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F27,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x8007000ELL,
      PropertyBufferSizea);
    PropVariantClear(v95);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    if ( (_QWORD)v75 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        v75,
        *((_QWORD *)&v75 + 1));
      std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
      v75 = 0;
      v76 = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
    v88 = 0;
    lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
    return 2147942414LL;
  }
  Device_IDW = CM_Get_Device_IDW(dnDevInst, (PWSTR)v52, pulLen, 0);
  v55 = CM_MapCrToWin32Err(Device_IDW, 0x507u);
  if ( !v55 )
  {
    v56 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v56 > 4u )
    {
      *(PROPVARIANT *)v90 = v95[1];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v56,
        (unsigned int)word_180075C72,
        v57,
        v58,
        (__int64)v90);
    }
    phkDevice = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkDevice,
      0);
    if ( CM_Open_DevNode_Key(dnDevInst, 0x20019u, 0, 1u, &phkDevice, 1u) )
    {
      v71 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v71 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v71,
          &dword_180075B84);
    }
    else
    {
      v59 = (const unsigned __int16 **)v75;
      while ( v59 != *((const unsigned __int16 ***)&v75 + 1) )
      {
        v60 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v60 > 4u )
        {
          *(_QWORD *)v90 = *v59;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v60,
            (unsigned int)byte_180075C33,
            v61,
            v62,
            (__int64)v90);
        }
        if ( IsAPOClsidRegistered(phkDevice, *v59) )
        {
          v63 = AudioEndpointBuilderTelemetryProvider::Provider();
          if ( *(_DWORD *)v63 > 4u )
          {
            *(_QWORD *)v90 = *v59;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v63,
              (unsigned int)byte_180075BF9,
              v64,
              v65,
              (__int64)v90);
          }
          *(_OWORD *)pvar = 0;
          LODWORD(v99) = 0;
          ApoDeviceIdPKey = GetApoDeviceIdPKey(*v59, (struct _tagpropertykey *)pvar);
          v16 = ApoDeviceIdPKey;
          if ( ApoDeviceIdPKey < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F44,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)(unsigned int)ApoDeviceIdPKey,
              PropertyBufferSizeb);
            if ( phkDevice )
              RegCloseKey(phkDevice);
            PropVariantClear(v95);
            if ( pv )
              CoTaskMemFree(pv);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
            if ( (_QWORD)v75 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                v75,
                *((_QWORD *)&v75 + 1));
              std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
              v75 = 0;
              v76 = 0;
            }
            goto LABEL_116;
          }
          v67 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *, PROPVARIANT *))(*(_QWORD *)v80 + 48LL))(
                  v80,
                  pvar,
                  v95);
          v16 = v67;
          if ( v67 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F45,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)(unsigned int)v67,
              PropertyBufferSizeb);
            if ( phkDevice )
              RegCloseKey(phkDevice);
            PropVariantClear(v95);
            if ( pv )
              CoTaskMemFree(pv);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
            if ( (_QWORD)v75 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                v75,
                *((_QWORD *)&v75 + 1));
              std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
              v75 = 0;
              v76 = 0;
            }
            goto LABEL_116;
          }
          v59 = *(const unsigned __int16 ***)std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::erase(
                                               &v75,
                                               v97,
                                               v59);
        }
        else
        {
          v68 = AudioEndpointBuilderTelemetryProvider::Provider();
          if ( *(_DWORD *)v68 > 4u )
          {
            *(_QWORD *)v90 = *v59;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v68,
              (unsigned int)word_180075BBA,
              v69,
              v70,
              (__int64)v90);
          }
          ++v59;
        }
      }
    }
    if ( phkDevice )
      RegCloseKey(phkDevice);
    PropVariantClear(v95);
    goto LABEL_126;
  }
  v29 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1F2A,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)v55,
          PropertyBufferSizea);
  PropVariantClear(v95);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
  if ( (_QWORD)v75 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
      v75,
      *((_QWORD *)&v75 + 1));
    std::_Deallocate<16>(v75, (v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
    v75 = 0;
    v76 = 0;
  }
LABEL_90:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
  v88 = 0;
  lambda_af49a17175fa11b40f0ef7314e83f99e_::operator()(v87);
  return v29;
}

```

## disassembly

```asm
0x18002b2a8  mov     r11, rsp
0x18002b2ab  mov     [r11+10h], rdx
0x18002b2af  push    rbx
0x18002b2b0  push    rsi
0x18002b2b1  push    rdi
0x18002b2b2  push    r12
0x18002b2b4  push    r14
0x18002b2b6  sub     rsp, 2B0h
0x18002b2bd  mov     rax, cs:__security_cookie
0x18002b2c4  xor     rax, rsp
0x18002b2c7  mov     [rsp+2D8h+var_38], rax
0x18002b2cf  mov     [r11-200h], r8
0x18002b2d6  mov     [rsp+2D8h+var_260], r9
0x18002b2db  movups  xmm0, xmmword ptr cs:PKEY_FX_PreMixEffectClsid.fmtid.Data1
0x18002b2e2  movaps  [rsp+2D8h+var_1A8], xmm0
0x18002b2ea  mov     eax, cs:PKEY_FX_PreMixEffectClsid.pid
0x18002b2f0  mov     [rsp+2D8h+var_198], eax
0x18002b2f7  movups  xmm0, xmmword ptr cs:PKEY_FX_PostMixEffectClsid.fmtid.Data1
0x18002b2fe  movups  [rsp+2D8h+var_194], xmm0
0x18002b306  mov     eax, cs:PKEY_FX_PostMixEffectClsid.pid
0x18002b30c  mov     [rsp+2D8h+var_184], eax
0x18002b313  movups  xmm0, xmmword ptr cs:PKEY_FX_StreamEffectClsid.fmtid.Data1
0x18002b31a  movups  [rsp+2D8h+var_180], xmm0
0x18002b322  mov     eax, cs:PKEY_FX_StreamEffectClsid.pid
0x18002b328  mov     [rsp+2D8h+var_170], eax
0x18002b32f  movups  xmm0, xmmword ptr cs:PKEY_FX_ModeEffectClsid.fmtid.Data1
0x18002b336  movups  [rsp+2D8h+var_16C], xmm0
0x18002b33e  mov     eax, cs:PKEY_FX_ModeEffectClsid.pid
0x18002b344  mov     [rsp+2D8h+var_15C], eax
0x18002b34b  movups  xmm0, xmmword ptr cs:PKEY_FX_EndpointEffectClsid.fmtid.Data1
0x18002b352  movaps  [rsp+2D8h+var_158], xmm0
0x18002b35a  mov     eax, cs:PKEY_FX_EndpointEffectClsid.pid
0x18002b360  mov     [rsp+2D8h+var_148], eax
0x18002b367  movups  xmm0, xmmword ptr cs:PKEY_FX_KeywordDetector_StreamEffectClsid.fmtid.Data1
0x18002b36e  movups  [rsp+2D8h+var_144], xmm0
0x18002b376  mov     eax, cs:PKEY_FX_KeywordDetector_StreamEffectClsid.pid
0x18002b37c  mov     [rsp+2D8h+var_134], eax
0x18002b383  movups  xmm0, xmmword ptr cs:PKEY_FX_KeywordDetector_ModeEffectClsid.fmtid.Data1
0x18002b38a  movups  [rsp+2D8h+var_130], xmm0
0x18002b392  mov     eax, cs:PKEY_FX_KeywordDetector_ModeEffectClsid.pid
0x18002b398  mov     [rsp+2D8h+var_120], eax
0x18002b39f  movups  xmm0, xmmword ptr cs:PKEY_FX_KeywordDetector_EndpointEffectClsid.fmtid.Data1
0x18002b3a6  movups  [rsp+2D8h+var_11C], xmm0
0x18002b3ae  mov     eax, cs:PKEY_FX_KeywordDetector_EndpointEffectClsid.pid
0x18002b3b4  mov     [rsp+2D8h+var_10C], eax
0x18002b3bb  movups  xmm0, xmmword ptr cs:PKEY_FX_Offload_StreamEffectClsid.fmtid.Data1
0x18002b3c2  movaps  [rsp+2D8h+var_108], xmm0
0x18002b3ca  mov     eax, cs:PKEY_FX_Offload_StreamEffectClsid.pid
0x18002b3d0  mov     [rsp+2D8h+var_F8], eax
0x18002b3d7  movups  xmm0, xmmword ptr cs:PKEY_FX_Offload_ModeEffectClsid.fmtid.Data1
0x18002b3de  movups  [rsp+2D8h+var_F4], xmm0
0x18002b3e6  mov     eax, cs:PKEY_FX_Offload_ModeEffectClsid.pid
0x18002b3ec  mov     [rsp+2D8h+var_E4], eax
0x18002b3f3  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_StreamEffectClsid.fmtid.Data1
0x18002b3fa  movups  [rsp+2D8h+var_E0], xmm0
0x18002b402  mov     eax, cs:PKEY_CompositeFX_StreamEffectClsid.pid
0x18002b408  mov     [rsp+2D8h+var_D0], eax
0x18002b40f  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_ModeEffectClsid.fmtid.Data1
0x18002b416  movups  [rsp+2D8h+var_CC], xmm0
0x18002b41e  mov     eax, cs:PKEY_CompositeFX_ModeEffectClsid.pid
0x18002b424  mov     [rsp+2D8h+var_BC], eax
0x18002b42b  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_EndpointEffectClsid.fmtid.Data1
0x18002b432  movaps  [rsp+2D8h+var_B8], xmm0
0x18002b43a  mov     eax, cs:PKEY_CompositeFX_EndpointEffectClsid.pid
0x18002b440  mov     [rsp+2D8h+var_A8], eax
0x18002b447  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_KeywordDetector_StreamEffectClsid.fmtid.Data1
0x18002b44e  movups  [rsp+2D8h+var_A4], xmm0
0x18002b456  mov     eax, cs:PKEY_CompositeFX_KeywordDetector_StreamEffectClsid.pid
0x18002b45c  mov     [rsp+2D8h+var_94], eax
0x18002b463  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_KeywordDetector_ModeEffectClsid.fmtid.Data1
0x18002b46a  movups  [rsp+2D8h+var_90], xmm0
0x18002b472  mov     eax, cs:PKEY_CompositeFX_KeywordDetector_ModeEffectClsid.pid
0x18002b478  mov     [r11-80h], eax
0x18002b47c  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_KeywordDetector_EndpointEffectClsid.fmtid.Data1
0x18002b483  movups  xmmword ptr [r11-7Ch], xmm0
0x18002b488  mov     eax, cs:PKEY_CompositeFX_KeywordDetector_EndpointEffectClsid.pid
0x18002b48e  mov     [r11-6Ch], eax
0x18002b492  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_Offload_StreamEffectClsid.fmtid.Data1
0x18002b499  movaps  xmmword ptr [r11-68h], xmm0
0x18002b49e  mov     eax, cs:PKEY_CompositeFX_Offload_StreamEffectClsid.pid
0x18002b4a4  mov     [r11-58h], eax
0x18002b4a8  movups  xmm0, xmmword ptr cs:PKEY_CompositeFX_Offload_ModeEffectClsid.fmtid.Data1
0x18002b4af  movups  xmmword ptr [r11-54h], xmm0
0x18002b4b4  mov     eax, cs:PKEY_CompositeFX_Offload_ModeEffectClsid.pid
0x18002b4ba  mov     [r11-44h], eax
0x18002b4be  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002b4c3  mov     ecx, [rax]
0x18002b4c5  cmp     ecx, 4
0x18002b4c8  jbe     short loc_18002B513
0x18002b4ca  mov     rcx, [rsp+2D8h+var_200]
0x18002b4d2  mov     [rsp+2D8h+var_220], rcx
0x18002b4da  mov     rcx, [rsp+2D8h+arg_8]
0x18002b4e2  mov     [rsp+2D8h+phkDevice], rcx
0x18002b4ea  lea     rcx, [rsp+2D8h+var_220]
0x18002b4f2  mov     qword ptr [rsp+2D8h+ulFlags], rcx
0x18002b4f7  lea     rcx, [rsp+2D8h+phkDevice]
0x18002b4ff  mov     [rsp+2D8h+PropertyBufferSize], rcx; int
0x18002b504  lea     rdx, word_180075DFE
0x18002b50b  mov     rcx, rax
0x18002b50e  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002b513  lea     rax, [rsp+2D8h+arg_8]
0x18002b51b  mov     [rsp+2D8h+var_238], rax
0x18002b523  lea     rax, [rsp+2D8h+var_200]
0x18002b52b  mov     [rsp+2D8h+var_230], rax
0x18002b533  mov     r14d, 1
0x18002b539  mov     [rsp+2D8h+var_228], r14b
0x18002b541  xor     esi, esi
0x18002b543  mov     [rsp+2D8h+var_270], rsi
0x18002b548  lea     rdx, [rsp+2D8h+var_270]
0x18002b54d  lea     rcx, [rsp+2D8h+var_260]
0x18002b552  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x18002b557  mov     ebx, eax
0x18002b559  test    eax, eax
0x18002b55b  jns     short loc_18002B5A1
0x18002b55d  mov     rcx, [rsp+2D8h]; this
0x18002b565  mov     r9d, eax; char *
0x18002b568  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b56f  mov     edx, 1E9Ch; void *
0x18002b574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b579  nop
0x18002b57a  lea     rcx, [rsp+2D8h+var_270]
0x18002b57f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b584  nop
0x18002b585  mov     [rsp+2D8h+var_228], sil
0x18002b58d  lea     rcx, [rsp+2D8h+var_238]
0x18002b595  call    _lambda_af49a17175fa11b40f0ef7314e83f99e___operator__
0x18002b59a  mov     eax, ebx
0x18002b59c  jmp     loc_18002C76F
0x18002b5a1  mov     [rsp+2D8h+var_278], rsi
0x18002b5a6  mov     rcx, [rsp+2D8h+var_270]
0x18002b5ab  mov     rax, [rcx]
0x18002b5ae  mov     [rsp+2D8h+var_278], rsi
0x18002b5b3  lea     r8, [rsp+2D8h+var_278]
0x18002b5b8  xor     edx, edx
0x18002b5ba  mov     rax, [rax+28h]
0x18002b5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5c3  mov     ebx, eax
0x18002b5c5  test    eax, eax
0x18002b5c7  jns     short loc_18002B618
0x18002b5c9  mov     rcx, [rsp+2D8h]; this
0x18002b5d1  mov     r9d, eax; char *
0x18002b5d4  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b5db  mov     edx, 1EA0h; void *
0x18002b5e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b5e5  nop
0x18002b5e6  lea     rcx, [rsp+2D8h+var_278]
0x18002b5eb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b5f0  nop
0x18002b5f1  lea     rcx, [rsp+2D8h+var_270]
0x18002b5f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b5fb  nop
0x18002b5fc  mov     [rsp+2D8h+var_228], sil
0x18002b604  lea     rcx, [rsp+2D8h+var_238]
0x18002b60c  call    _lambda_af49a17175fa11b40f0ef7314e83f99e___operator__
0x18002b611  mov     eax, ebx
0x18002b613  jmp     loc_18002C76F
0x18002b618  mov     rcx, [rsp+2D8h+var_278]
0x18002b61d  test    rcx, rcx
0x18002b620  jz      loc_18002C739
0x18002b626  xorps   xmm0, xmm0
0x18002b629  movdqu  [rsp+2D8h+var_298], xmm0
0x18002b62f  mov     [rsp+2D8h+var_288], rsi
0x18002b634  lea     rbx, [rsp+2D8h+var_1A8]
0x18002b63c  lea     r12, [rsp+2D8h+var_40]
0x18002b644  cmp     rbx, r12
0x18002b647  jz      loc_18002B8A9
0x18002b64d  xorps   xmm0, xmm0
0x18002b650  xor     eax, eax
0x18002b652  movups  xmmword ptr [rsp+2D8h+pvar], xmm0
0x18002b65a  mov     [rsp+2D8h+var_1C8], rax
0x18002b662  mov     rax, [rcx]
0x18002b665  lea     r8, [rsp+2D8h+pvar]
0x18002b66d  mov     rdx, rbx
0x18002b670  mov     rax, [rax+28h]
0x18002b674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b679  mov     edi, eax
0x18002b67b  test    eax, eax
0x18002b67d  jns     loc_18002B719
0x18002b683  mov     rcx, [rsp+2D8h]; this
0x18002b68b  mov     r9d, eax; char *
0x18002b68e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b695  mov     edx, 1EADh; void *
0x18002b69a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b69f  nop
0x18002b6a0  lea     rcx, [rsp+2D8h+pvar]; pvar
0x18002b6a8  call    cs:__imp_PropVariantClear
0x18002b6ae  nop
0x18002b6af  mov     rcx, qword ptr [rsp+2D8h+var_298]
0x18002b6b4  test    rcx, rcx
0x18002b6b7  jz      short loc_18002B6E7
0x18002b6b9  mov     rdx, qword ptr [rsp+2D8h+var_298+8]
0x18002b6be  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18002b6c3  mov     rcx, qword ptr [rsp+2D8h+var_298]
0x18002b6c8  mov     rdx, [rsp+2D8h+var_288]
0x18002b6cd  sub     rdx, rcx
0x18002b6d0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002b6d4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b6d9  xorps   xmm0, xmm0
0x18002b6dc  movdqu  [rsp+2D8h+var_298], xmm0
0x18002b6e2  mov     [rsp+2D8h+var_288], rsi
0x18002b6e7  lea     rcx, [rsp+2D8h+var_278]
0x18002b6ec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b6f1  nop
0x18002b6f2  lea     rcx, [rsp+2D8h+var_270]
0x18002b6f7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b6fc  nop
0x18002b6fd  mov     [rsp+2D8h+var_228], sil
0x18002b705  lea     rcx, [rsp+2D8h+var_238]
0x18002b70d  call    _lambda_af49a17175fa11b40f0ef7314e83f99e___operator__
0x18002b712  mov     eax, edi
0x18002b714  jmp     loc_18002C76F
0x18002b719  movzx   eax, word ptr [rsp+2D8h+pvar]
0x18002b721  test    eax, eax
0x18002b723  jz      loc_18002B88D
0x18002b729  cmp     eax, 1Fh
0x18002b72c  jz      loc_18002B824
0x18002b732  cmp     eax, 101Fh
0x18002b737  jz      short loc_18002B78B
0x18002b739  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002b73e  mov     ecx, [rax]
0x18002b740  cmp     ecx, 4
0x18002b743  jbe     loc_18002B88D
0x18002b749  movzx   ecx, word ptr [rsp+2D8h+pvar]
0x18002b751  mov     word ptr [rsp+2D8h+dnDevInst], cx
0x18002b756  mov     ecx, [rbx+10h]
0x18002b759  mov     [rsp+2D8h+pdnDevInst], ecx
0x18002b760  lea     rcx, [rsp+2D8h+dnDevInst]
0x18002b765  mov     qword ptr [rsp+2D8h+ulFlags], rcx
0x18002b76a  lea     rcx, [rsp+2D8h+pdnDevInst]
0x18002b772  mov     [rsp+2D8h+PropertyBufferSize], rcx
0x18002b777  lea     rdx, word_180075D4A
0x18002b77e  mov     rcx, rax
0x18002b781  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x18002b786  jmp     loc_18002B88D
0x18002b78b  mov     eax, dword ptr [rsp+2D8h+pvar+8]
0x18002b792  test    eax, eax
0x18002b794  jz      loc_18002B88D
0x18002b79a  lea     ecx, [rax-1]
0x18002b79d  mov     rax, [rsp+2D8h+var_1C8]
0x18002b7a5  lea     rdx, [rax+rcx*8]
0x18002b7a9  lea     rcx, [rsp+2D8h+var_298]
0x18002b7ae  call    ??$emplace_back@AEAPEAG@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAPEAG@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::emplace_back<ushort * &>(ushort * &)
0x18002b7b3  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002b7b8  mov     ecx, [rax]
0x18002b7ba  cmp     ecx, 4
0x18002b7bd  jbe     short loc_18002B80F
0x18002b7bf  mov     edx, dword ptr [rsp+2D8h+pvar+8]
0x18002b7c6  dec     edx
0x18002b7c8  mov     rcx, [rsp+2D8h+var_1C8]
0x18002b7d0  mov     rdx, [rcx+rdx*8]
0x18002b7d4  mov     [rsp+2D8h+var_220], rdx
0x18002b7dc  mov     ecx, [rbx+10h]
0x18002b7df  mov     [rsp+2D8h+PropertyType], ecx
0x18002b7e6  lea     rcx, [rsp+2D8h+var_220]
0x18002b7ee  mov     qword ptr [rsp+2D8h+ulFlags], rcx
0x18002b7f3  lea     rcx, [rsp+2D8h+PropertyType]
0x18002b7fb  mov     [rsp+2D8h+PropertyBufferSize], rcx
0x18002b800  lea     rdx, byte_180075D89
0x18002b807  mov     rcx, rax
0x18002b80a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002b80f  mov     eax, dword ptr [rsp+2D8h+pvar+8]
0x18002b816  dec     eax
0x18002b818  mov     dword ptr [rsp+2D8h+pvar+8], eax
0x18002b81f  jmp     loc_18002B792
0x18002b824  lea     rdx, [rsp+2D8h+pvar+8]
0x18002b82c  lea     rcx, [rsp+2D8h+var_298]
0x18002b831  call    ??$emplace_back@AEAPEAG@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAPEAG@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::emplace_back<ushort * &>(ushort * &)
0x18002b836  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002b83b  mov     ecx, [rax]
0x18002b83d  cmp     ecx, 4
0x18002b840  jbe     short loc_18002B885
0x18002b842  mov     rcx, [rsp+2D8h+pvar+8]
0x18002b84a  mov     [rsp+2D8h+var_220], rcx
0x18002b852  mov     ecx, [rbx+10h]
0x18002b855  mov     [rsp+2D8h+pdnDevInst], ecx
0x18002b85c  lea     rcx, [rsp+2D8h+var_220]
0x18002b864  mov     qword ptr [rsp+2D8h+ulFlags], rcx
0x18002b869  lea     rcx, [rsp+2D8h+pdnDevInst]
0x18002b871  mov     [rsp+2D8h+PropertyBufferSize], rcx
0x18002b876  lea     rdx, unk_180075DC8
0x18002b87d  mov     rcx, rax
0x18002b880  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002b885  mov     [rsp+2D8h+pvar+8], rsi
0x18002b88d  lea     rcx, [rsp+2D8h+pvar]; pvar
0x18002b895  call    cs:__imp_PropVariantClear
0x18002b89b  add     rbx, 14h
0x18002b89f  mov     rcx, [rsp+2D8h+var_278]
0x18002b8a4  jmp     loc_18002B644
0x18002b8a9  mov     [rsp+2D8h+var_268], rsi
0x18002b8ae  mov     rcx, [rsp+2D8h+var_270]
0x18002b8b3  mov     rax, [rcx]
0x18002b8b6  mov     [rsp+2D8h+var_268], rsi
0x18002b8bb  lea     r8, [rsp+2D8h+var_268]
0x18002b8c0  mov     edx, 2
0x18002b8c5  mov     rax, [rax+28h]
0x18002b8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8ce  mov     ebx, eax
0x18002b8d0  test    eax, eax
0x18002b8d2  jns     loc_18002B96A
0x18002b8d8  mov     rcx, [rsp+2D8h]; this
  ... truncated ...
```
