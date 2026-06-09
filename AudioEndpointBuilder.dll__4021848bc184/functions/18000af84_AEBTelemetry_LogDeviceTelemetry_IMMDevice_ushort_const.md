# AEBTelemetry::LogDeviceTelemetry(IMMDevice *,ushort const *)

- ea: `0x18000af84`
- end: `0x18000bc94`
- name: `?LogDeviceTelemetry@AEBTelemetry@@SAXPEAUIMMDevice@@PEBG@Z`
- size: `3344`
- prototype: `void __fastcall(struct IMMDevice *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009740`
- `0x18003b790`

## callees

- `0x180002508`
- `0x180006b0c`
- `0x18000af84`
- `0x18000fb60`
- `0x180013a8c`
- `0x18001f374`
- `0x18001f430`
- `0x1800252a4`
- `0x180029c9c`
- `0x180037090`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18000b4f7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18000b85d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18000b4f7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18000b85d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b25c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b373`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bb94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bba2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbc5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbe1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbfd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc27`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc43`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b25c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b373`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bb94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bba2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbc5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbe1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bbfd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc27`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc43`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc61`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall AEBTelemetry::LogDeviceTelemetry(struct IMMDevice *a1, const unsigned __int16 *a2)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v4; // r15d
  __int16 *v5; // rbx
  BOOL v6; // r12d
  struct IMMDeviceVtbl *lpVtbl; // rax
  char v8; // di
  const WCHAR *v9; // r13
  const WCHAR *v10; // rsi
  struct IMMDevice *v11; // r14
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rax
  __int64 v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  int v16; // r14d
  __int64 v17; // r8
  __int64 v18; // r9
  char v19; // al
  int v20; // eax
  const WCHAR *v21; // rax
  __int16 v22; // ax
  GUID *v23; // rax
  char v24; // al
  char v25; // al
  const WCHAR *v26; // rax
  const WCHAR *v27; // rax
  const WCHAR *v28; // rax
  const WCHAR *v29; // rax
  const struct _tlgProvider_t *v30; // rax
  __int64 v31; // r8
  __int64 v32; // r14
  __int64 v33; // r8
  __int64 v34; // r9
  char v35; // al
  int v36; // eax
  const WCHAR *v37; // rax
  __int16 v38; // ax
  GUID *v39; // rax
  char v40; // al
  char v41; // al
  const WCHAR *v42; // rax
  const WCHAR *v43; // rax
  const WCHAR *v44; // rax
  const WCHAR *v45; // rax
  bool v46; // [rsp+110h] [rbp-80h] BYREF
  char v47; // [rsp+111h] [rbp-7Fh] BYREF
  char v48; // [rsp+112h] [rbp-7Eh] BYREF
  char v49; // [rsp+113h] [rbp-7Dh] BYREF
  char v50; // [rsp+114h] [rbp-7Ch] BYREF
  _BYTE v51[3]; // [rsp+115h] [rbp-7Bh] BYREF
  _WORD v52[2]; // [rsp+118h] [rbp-78h] BYREF
  __int16 v53; // [rsp+11Ch] [rbp-74h] BYREF
  __int16 v54; // [rsp+11Eh] [rbp-72h] BYREF
  __int16 v55; // [rsp+120h] [rbp-70h] BYREF
  __int16 v56; // [rsp+122h] [rbp-6Eh] BYREF
  __int16 v57; // [rsp+124h] [rbp-6Ch] BYREF
  __int16 v58; // [rsp+126h] [rbp-6Ah] BYREF
  __int16 v59; // [rsp+128h] [rbp-68h] BYREF
  _WORD v60[3]; // [rsp+12Ah] [rbp-66h] BYREF
  __int64 v61; // [rsp+130h] [rbp-60h] BYREF
  _WORD v62[2]; // [rsp+138h] [rbp-58h] BYREF
  int v63; // [rsp+13Ch] [rbp-54h] BYREF
  int v64; // [rsp+140h] [rbp-50h] BYREF
  struct IMMDevice *v65; // [rsp+148h] [rbp-48h] BYREF
  __int64 v66; // [rsp+150h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+158h] [rbp-38h] BYREF
  const WCHAR *v68; // [rsp+160h] [rbp-30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+168h] [rbp-28h] BYREF
  __int64 v70; // [rsp+178h] [rbp-18h]
  __int64 v71; // [rsp+180h] [rbp-10h] BYREF
  __int64 v72; // [rsp+188h] [rbp-8h] BYREF
  const WCHAR *v73; // [rsp+190h] [rbp+0h] BYREF
  const WCHAR *v74; // [rsp+198h] [rbp+8h] BYREF
  const WCHAR *v75; // [rsp+1A0h] [rbp+10h] BYREF
  const WCHAR *v76; // [rsp+1A8h] [rbp+18h] BYREF
  const WCHAR *v77; // [rsp+1B0h] [rbp+20h] BYREF
  const WCHAR *v78; // [rsp+1B8h] [rbp+28h] BYREF
  const WCHAR *v79; // [rsp+1C0h] [rbp+30h] BYREF
  const WCHAR *v80; // [rsp+1C8h] [rbp+38h] BYREF
  __int64 v81; // [rsp+1D0h] [rbp+40h] BYREF
  struct IMMDevice *v82; // [rsp+1D8h] [rbp+48h] BYREF
  _WORD *v83; // [rsp+1E0h] [rbp+50h] BYREF
  int v84; // [rsp+1E8h] [rbp+58h]
  PROPVARIANT v85[2]; // [rsp+1F0h] [rbp+60h] BYREF
  __int64 v86; // [rsp+200h] [rbp+70h]
  PROPVARIANT v87[2]; // [rsp+208h] [rbp+78h] BYREF
  __int64 v88; // [rsp+218h] [rbp+88h]
  PROPVARIANT v89[2]; // [rsp+220h] [rbp+90h] BYREF
  __int64 v90; // [rsp+230h] [rbp+A0h]
  PROPVARIANT v91[2]; // [rsp+238h] [rbp+A8h] BYREF
  __int64 v92; // [rsp+248h] [rbp+B8h]
  PROPVARIANT v93[2]; // [rsp+250h] [rbp+C0h] BYREF
  __int16 *v94; // [rsp+260h] [rbp+D0h]
  PROPVARIANT v95[2]; // [rsp+268h] [rbp+D8h] BYREF
  __int64 v96; // [rsp+278h] [rbp+E8h]
  PROPVARIANT v97[2]; // [rsp+280h] [rbp+F0h] BYREF
  __int64 v98; // [rsp+290h] [rbp+100h]
  PROPVARIANT v99[2]; // [rsp+298h] [rbp+108h] BYREF
  __int64 v100; // [rsp+2A8h] [rbp+118h]
  PROPVARIANT v101[2]; // [rsp+2B0h] [rbp+120h] BYREF
  __int64 v102; // [rsp+2C0h] [rbp+130h]
  PROPVARIANT v103[2]; // [rsp+2C8h] [rbp+138h] BYREF
  __int64 v104; // [rsp+2D8h] [rbp+148h]
  PROPVARIANT v105[2]; // [rsp+2E0h] [rbp+150h] BYREF
  __int64 v106; // [rsp+2F0h] [rbp+160h]
  PROPVARIANT v107[2]; // [rsp+2F8h] [rbp+168h] BYREF
  __int64 v108; // [rsp+308h] [rbp+178h]
  PROPVARIANT v109[2]; // [rsp+310h] [rbp+180h] BYREF
  const WCHAR **v110; // [rsp+320h] [rbp+190h]
  PROPVARIANT v111[2]; // [rsp+328h] [rbp+198h] BYREF
  __int64 v112; // [rsp+338h] [rbp+1A8h]
  PROPVARIANT v113[2]; // [rsp+340h] [rbp+1B0h] BYREF
  __int64 v114; // [rsp+350h] [rbp+1C0h]
  GUID v115; // [rsp+358h] [rbp+1C8h] BYREF

  v68 = a2;
  v65 = a1;
  v63 = 2;
  v71 = 0;
  if ( (int)wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(&v65, (__int64)&v71) >= 0 )
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 24LL))(v71, &v63);
  pv = 0;
  GetId = a1->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  ((void (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a1, &pv);
  *(_OWORD *)v107 = 0;
  v108 = 0;
  *(_OWORD *)v105 = 0;
  v106 = 0;
  *(_OWORD *)v103 = 0;
  v104 = 0;
  *(_OWORD *)v101 = 0;
  v102 = 0;
  *(_OWORD *)v99 = 0;
  v100 = 0;
  *(_OWORD *)v97 = 0;
  v98 = 0;
  *(_OWORD *)v95 = 0;
  v96 = 0;
  v4 = 10;
  *(_OWORD *)v93 = 0;
  v94 = 0;
  *(_OWORD *)v91 = 0;
  v92 = 0;
  *(_OWORD *)v89 = 0;
  v90 = 0;
  v5 = 0;
  v52[0] = 0;
  v115 = GUID_00000000_0000_0000_0000_000000000000;
  v6 = 0;
  *(_OWORD *)v87 = 0;
  v88 = 0;
  v61 = 0;
  lpVtbl = a1->lpVtbl;
  v61 = 0;
  v8 = 1;
  if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))lpVtbl->OpenPropertyStore)(a1, 0, &v61) >= 0 )
  {
    (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      &DEVPKEY_Device_EnumeratorName,
      v107);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      PKEY_Endpoint_Devnode,
      v105);
    (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      &DEVPKEY_Device_ContainerId,
      v103);
    (*(void (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      &PKEY_AudioEndpoint_JackSubType,
      v101);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      PKEY_Endpoint_IsBluetooth,
      v99);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(v61, PKEY_Endpoint_IsUSB, v97);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      PKEY_Endpoint_IsSideband,
      v95);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      PKEY_AudioEndpoint_PersistentId,
      v91);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
      v61,
      PKEY_Devices_AudioDevice_Microphone_IsFarField,
      v87);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
    {
      *(_OWORD *)pvar = 0;
      v70 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
        v61,
        PKEY_Multicast_Target_SessionDescriptor,
        pvar);
      if ( LOWORD(pvar[0]) == 65 && LODWORD(pvar[1]) == 36 )
        v115 = *(GUID *)(v70 + 20);
      PropVariantClear(pvar);
    }
    *(_OWORD *)v111 = 0;
    v112 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
           v61,
           &PKEY_AudioEndpoint_FormFactor,
           v111) >= 0
      && LOWORD(v111[0]) == 19 )
    {
      v4 = (int)v111[1];
    }
    if ( v63 == 1
      && (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
           v61,
           &PKEY_Devices_MicrophoneArray_Geometry,
           v93) >= 0
      && LOWORD(v93[0]) == 4113
      && v94
      && LODWORD(v93[1]) >= 0x12 )
    {
      v52[0] = v94[8];
      if ( LODWORD(v93[1]) < 12 * (unsigned __int64)v52[0] + 18 )
      {
        v5 = 0;
        v52[0] = 0;
      }
      else
      {
        v5 = v94;
        if ( v52[0] > 0x10u )
          v52[0] = 16;
      }
    }
    if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v61 + 40LL))(
           v61,
           PKEY_Devices_AudioPosture_Support,
           v89) >= 0
      && LOWORD(v89[0]) == 11 )
    {
      v6 = LOWORD(v89[1]) == 0xFFFF;
    }
    PropVariantClear(v111);
  }
  *(_OWORD *)v109 = 0;
  v110 = 0;
  *(_OWORD *)v113 = 0;
  v114 = 0;
  v9 = &LocaleName;
  v10 = &LocaleName;
  *(_OWORD *)v85 = 0;
  v86 = 0;
  v66 = 0;
  v82 = 0;
  if ( (int)AEBTelemetry::GetPnpDevnodeFromMMDevice(a1, &v82) >= 0 )
  {
    v11 = v82;
    OpenPropertyStore = v82->lpVtbl->OpenPropertyStore;
    v65 = (struct IMMDevice *)OpenPropertyStore;
    v13 = v66;
    v66 = 0;
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      OpenPropertyStore = (HRESULT (__stdcall *)(IMMDevice *, DWORD, IPropertyStore **))v65;
    }
    if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(v11, 0, &v66) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v66 + 40LL))(
             v66,
             &DEVPKEY_Device_HardwareIds,
             v109) >= 0
        && LOWORD(v109[0]) == 4127
        && LODWORD(v109[1]) )
      {
        v9 = *v110;
      }
      if ( (*(int (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v66 + 40LL))(
             v66,
             &DEVPKEY_Device_Parent,
             v113) >= 0
        && LOWORD(v113[0]) == 31 )
      {
        v10 = (const WCHAR *)v113[1];
      }
      (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v66 + 40LL))(
        v66,
        &DEVPKEY_Device_InstanceId,
        v85);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
  {
    v14 = AudioEndpointBuilderTelemetryProvider::Provider();
    v16 = (int)v14;
    if ( *(_DWORD *)v14 > 4u && (unsigned __int8)tlgKeywordOn(v14, 0x800000000000LL, v15) )
    {
      v72 = (__int64)&v115;
      v46 = StrStrIW(v10, L"\\SGPC_FUNC_01") != 0;
      if ( LOWORD(v89[0]) != 11 || (v19 = 1, !v6) )
        v19 = 0;
      v47 = v19;
      v20 = 0;
      if ( LOWORD(v87[0]) == 19 )
        v20 = (int)v87[1];
      v64 = v20;
      v21 = 0;
      LOWORD(v17) = 31;
      if ( LOWORD(v91[0]) == 31 )
        v21 = (const WCHAR *)v91[1];
      v73 = v21;
      v83 = v5 + 9;
      v84 = 12 * v52[0];
      pvar[0] = v52;
      LODWORD(pvar[1]) = 2;
      if ( v5 )
      {
        v53 = v5[3];
        v54 = v5[2];
        v55 = v5[5];
        v56 = v5[4];
        v57 = *v5;
        v58 = v5[8];
        v59 = v5[1];
        v60[0] = v5[6];
        v22 = v5[7];
      }
      else
      {
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60[0] = 0;
        v22 = 0;
      }
      v62[0] = v22;
      v48 = v63;
      if ( LOWORD(v103[0]) != 72 || (v23 = (GUID *)v103[1]) == 0 )
        v23 = &GUID_00000000_0000_0000_0000_000000000000;
      v74 = (const WCHAR *)v23;
      if ( LOWORD(v95[0]) != 11 || (v24 = 1, !LOWORD(v95[1])) )
        v24 = 0;
      v49 = v24;
      if ( LOWORD(v97[0]) != 11 || (v25 = 1, !LOWORD(v97[1])) )
        v25 = 0;
      v50 = v25;
      if ( LOWORD(v99[0]) != 11 || !LOWORD(v99[1]) )
        v8 = 0;
      v51[0] = v8;
      v75 = (const WCHAR *)pv;
      v26 = 0;
      if ( LOWORD(v101[0]) == 31 )
        v26 = (const WCHAR *)v101[1];
      v76 = v26;
      LODWORD(v65) = v4;
      v27 = 0;
      if ( LOWORD(v105[0]) == 31 )
        v27 = (const WCHAR *)v105[1];
      v77 = v27;
      v28 = 0;
      if ( LOWORD(v107[0]) == 31 )
        v28 = (const WCHAR *)v107[1];
      v78 = v28;
      v29 = 0;
      if ( LOWORD(v85[0]) == 31 )
        v29 = (const WCHAR *)v85[1];
      v79 = v29;
      v80 = v9;
      v81 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>>(
        v16,
        (int)&byte_18007804F,
        v17,
        v18,
        (__int64)&v81,
        &v68,
        &v80,
        &v79,
        &v78,
        &v77,
        (__int64)&v65,
        &v76,
        &v75,
        (__int64)v51,
        (__int64)&v50,
        (__int64)&v49,
        (__int64 *)&v74,
        (__int64)&v48,
        (__int64)v62,
        (__int64)v60,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v53,
        (__int64 *)pvar,
        (__int64 *)&v83,
        &v73,
        (__int64)&v64,
        (__int64)&v47,
        (__int64)&v46,
        &v72);
    }
  }
  else
  {
    v30 = AudioEndpointBuilderTelemetryProvider::Provider();
    v32 = (__int64)v30;
    if ( *(_DWORD *)v30 > 4u && (unsigned __int8)tlgKeywordOn(v30, 0x800000000000LL, v31) )
    {
      v51[0] = StrStrIW(v10, L"\\SGPC_FUNC_01") != 0;
      if ( LOWORD(v89[0]) != 11 || (v35 = 1, !v6) )
        v35 = 0;
      v50 = v35;
      v36 = 0;
      if ( LOWORD(v87[0]) == 19 )
        v36 = (int)v87[1];
      LODWORD(v65) = v36;
      v37 = 0;
      LOWORD(v33) = 31;
      if ( LOWORD(v91[0]) == 31 )
        v37 = (const WCHAR *)v91[1];
      v81 = (__int64)v37;
      pvar[0] = v5 + 9;
      LODWORD(pvar[1]) = 12 * v52[0];
      v83 = v52;
      v84 = 2;
      if ( v5 )
      {
        v60[0] = v5[3];
        v59 = v5[2];
        v58 = v5[5];
        v57 = v5[4];
        v56 = *v5;
        v55 = v5[8];
        v54 = v5[1];
        v53 = v5[6];
        v38 = v5[7];
      }
      else
      {
        v60[0] = 0;
        v59 = 0;
        v58 = 0;
        v57 = 0;
        v56 = 0;
        v55 = 0;
        v54 = 0;
        v53 = 0;
        v38 = 0;
      }
      v62[0] = v38;
      v49 = v63;
      if ( LOWORD(v103[0]) != 72 || (v39 = (GUID *)v103[1]) == 0 )
        v39 = &GUID_00000000_0000_0000_0000_000000000000;
      v80 = (const WCHAR *)v39;
      if ( LOWORD(v95[0]) != 11 || (v40 = 1, !LOWORD(v95[1])) )
        v40 = 0;
      v48 = v40;
      if ( LOWORD(v97[0]) != 11 || (v41 = 1, !LOWORD(v97[1])) )
        v41 = 0;
      v47 = v41;
      if ( LOWORD(v99[0]) != 11 || !LOWORD(v99[1]) )
        v8 = 0;
      v46 = v8;
      v79 = (const WCHAR *)pv;
      v42 = 0;
      if ( LOWORD(v101[0]) == 31 )
        v42 = (const WCHAR *)v101[1];
      v78 = v42;
      v64 = v4;
      v43 = 0;
      if ( LOWORD(v105[0]) == 31 )
        v43 = (const WCHAR *)v105[1];
      v77 = v43;
      v44 = 0;
      if ( LOWORD(v107[0]) == 31 )
        v44 = (const WCHAR *)v107[1];
      v76 = v44;
      v45 = 0;
      if ( LOWORD(v85[0]) == 31 )
        v45 = (const WCHAR *)v85[1];
      v75 = v45;
      v74 = v9;
      v73 = v68;
      v72 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v32,
        (unsigned __int8 *)word_180077E22,
        v33,
        v34,
        (__int64)&v72,
        &v73,
        &v74,
        &v75,
        &v76,
        &v77,
        (__int64)&v64,
        &v78,
        &v79,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v48,
        (__int64 *)&v80,
        (__int64)&v49,
        (__int64)v62,
        (__int64)&v53,
        (__int64)&v54,
        (__int64)&v55,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)v60,
        (__int64 *)&v83,
        (__int64 *)pvar,
        (const WCHAR **)&v81,
        (__int64)&v65,
        (__int64)&v50,
        (__int64)v51);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v82);
  PropVariantClear(v85);
  PropVariantClear(v113);
  PropVariantClear(v109);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
  PropVariantClear(v87);
  PropVariantClear(v89);
  PropVariantClear(v91);
  PropVariantClear(v93);
  PropVariantClear(v95);
  PropVariantClear(v97);
  PropVariantClear(v99);
  PropVariantClear(v101);
  PropVariantClear(v103);
  PropVariantClear(v105);
  PropVariantClear(v107);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
}

```

## disassembly

```asm
0x18000af84  push    rbp
0x18000af86  push    rbx
0x18000af87  push    rsi
0x18000af88  push    rdi
0x18000af89  push    r12
0x18000af8b  push    r13
0x18000af8d  push    r14
0x18000af8f  push    r15
0x18000af91  lea     rbp, [rsp-1E8h]
0x18000af99  sub     rsp, 378h
0x18000afa0  mov     rax, cs:__security_cookie
0x18000afa7  xor     rax, rsp
0x18000afaa  mov     [rbp+220h+var_48], rax
0x18000afb1  mov     [rbp+220h+var_250], rdx
0x18000afb5  mov     r14, rcx
0x18000afb8  mov     [rbp+220h+var_268], rcx
0x18000afbc  mov     [rbp+220h+var_274], 2
0x18000afc3  xor     esi, esi
0x18000afc5  mov     [rbp+220h+var_230], rsi
0x18000afc9  lea     rdx, [rbp+220h+var_230]
0x18000afcd  lea     rcx, [rbp+220h+var_268]
0x18000afd1  call    ??$com_query_to_nothrow@UIMMEndpoint@@AEAPEAUIMMDevice@@@wil@@YAJAEAPEAUIMMDevice@@PEAPEAUIMMEndpoint@@@Z; wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(IMMDevice * &,IMMEndpoint * *)
0x18000afd6  test    eax, eax
0x18000afd8  js      short loc_18000AFEE
0x18000afda  mov     rcx, [rbp+220h+var_230]
0x18000afde  mov     rax, [rcx]
0x18000afe1  lea     rdx, [rbp+220h+var_274]
0x18000afe5  mov     rax, [rax+18h]
0x18000afe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afee  mov     [rbp+220h+pv], rsi
0x18000aff2  mov     rax, [r14]
0x18000aff5  mov     rbx, [rax+28h]
0x18000aff9  xor     edx, edx
0x18000affb  lea     rcx, [rbp+220h+pv]
0x18000afff  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000b004  lea     rdx, [rbp+220h+pv]
0x18000b008  mov     rcx, r14
0x18000b00b  mov     rax, rbx
0x18000b00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b013  xorps   xmm0, xmm0
0x18000b016  xor     eax, eax
0x18000b018  movups  xmmword ptr [rbp+220h+var_B8], xmm0
0x18000b01f  mov     [rbp+220h+var_A8], rax
0x18000b026  movups  xmmword ptr [rbp+220h+var_D0], xmm0
0x18000b02d  mov     [rbp+220h+var_C0], rax
0x18000b034  movups  xmmword ptr [rbp+220h+var_E8], xmm0
0x18000b03b  mov     [rbp+220h+var_D8], rax
0x18000b042  movups  xmmword ptr [rbp+220h+var_100], xmm0
0x18000b049  mov     [rbp+220h+var_F0], rax
0x18000b050  movups  xmmword ptr [rbp+220h+var_118], xmm0
0x18000b057  mov     [rbp+220h+var_108], rax
0x18000b05e  movups  xmmword ptr [rbp+220h+var_130], xmm0
0x18000b065  mov     [rbp+220h+var_120], rax
0x18000b06c  movups  xmmword ptr [rbp+220h+var_148], xmm0
0x18000b073  mov     [rbp+220h+var_138], rax
0x18000b07a  lea     r15d, [rax+0Ah]
0x18000b07e  movups  xmmword ptr [rbp+220h+var_160], xmm0
0x18000b085  mov     [rbp+220h+var_150], rax
0x18000b08c  movups  xmmword ptr [rbp+220h+var_178], xmm0
0x18000b093  mov     [rbp+220h+var_168], rax
0x18000b09a  movups  xmmword ptr [rbp+220h+var_190], xmm0
0x18000b0a1  mov     [rbp+220h+var_180], rax
0x18000b0a8  mov     rbx, rsi
0x18000b0ab  mov     [rbp+220h+var_298], si
0x18000b0af  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000b0b6  movdqu  [rbp+220h+var_58], xmm0
0x18000b0be  mov     r12d, esi
0x18000b0c1  xorps   xmm1, xmm1
0x18000b0c4  movups  xmmword ptr [rbp+220h+var_1A8], xmm1
0x18000b0c8  mov     [rbp+220h+var_198], rax
0x18000b0cf  mov     [rbp+220h+var_280], rsi
0x18000b0d3  mov     rax, [r14]
0x18000b0d6  mov     [rbp+220h+var_280], rsi
0x18000b0da  lea     r8, [rbp+220h+var_280]
0x18000b0de  xor     edx, edx
0x18000b0e0  mov     rcx, r14
0x18000b0e3  mov     rax, [rax+20h]
0x18000b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ec  lea     edi, [r15-9]
0x18000b0f0  test    eax, eax
0x18000b0f2  js      loc_18000B379
0x18000b0f8  mov     rcx, [rbp+220h+var_280]
0x18000b0fc  mov     rax, [rcx]
0x18000b0ff  lea     r8, [rbp+220h+var_B8]
0x18000b106  lea     rdx, DEVPKEY_Device_EnumeratorName
0x18000b10d  mov     rax, [rax+28h]
0x18000b111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b116  mov     rcx, [rbp+220h+var_280]
0x18000b11a  mov     rax, [rcx]
0x18000b11d  lea     r8, [rbp+220h+var_D0]
0x18000b124  lea     rdx, PKEY_Endpoint_Devnode
0x18000b12b  mov     rax, [rax+28h]
0x18000b12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b134  mov     rcx, [rbp+220h+var_280]
0x18000b138  mov     rax, [rcx]
0x18000b13b  lea     r8, [rbp+220h+var_E8]
0x18000b142  lea     rdx, DEVPKEY_Device_ContainerId
0x18000b149  mov     rax, [rax+28h]
0x18000b14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b152  mov     rcx, [rbp+220h+var_280]
0x18000b156  mov     rax, [rcx]
0x18000b159  lea     r8, [rbp+220h+var_100]
0x18000b160  lea     rdx, PKEY_AudioEndpoint_JackSubType
0x18000b167  mov     rax, [rax+28h]
0x18000b16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b170  mov     rcx, [rbp+220h+var_280]
0x18000b174  mov     rax, [rcx]
0x18000b177  lea     r8, [rbp+220h+var_118]
0x18000b17e  lea     rdx, PKEY_Endpoint_IsBluetooth
0x18000b185  mov     rax, [rax+28h]
0x18000b189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18e  mov     rcx, [rbp+220h+var_280]
0x18000b192  mov     rax, [rcx]
0x18000b195  lea     r8, [rbp+220h+var_130]
0x18000b19c  lea     rdx, PKEY_Endpoint_IsUSB
0x18000b1a3  mov     rax, [rax+28h]
0x18000b1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ac  mov     rcx, [rbp+220h+var_280]
0x18000b1b0  mov     rax, [rcx]
0x18000b1b3  lea     r8, [rbp+220h+var_148]
0x18000b1ba  lea     rdx, PKEY_Endpoint_IsSideband
0x18000b1c1  mov     rax, [rax+28h]
0x18000b1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ca  mov     rcx, [rbp+220h+var_280]
0x18000b1ce  mov     rax, [rcx]
0x18000b1d1  lea     r8, [rbp+220h+var_178]
0x18000b1d8  lea     rdx, PKEY_AudioEndpoint_PersistentId
0x18000b1df  mov     rax, [rax+28h]
0x18000b1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e8  mov     rcx, [rbp+220h+var_280]
0x18000b1ec  mov     rax, [rcx]
0x18000b1ef  lea     r8, [rbp+220h+var_1A8]
0x18000b1f3  lea     rdx, PKEY_Devices_AudioDevice_Microphone_IsFarField
0x18000b1fa  mov     rax, [rax+28h]
0x18000b1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b203  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x18000b20a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x18000b20f  test    al, al
0x18000b211  jz      short loc_18000B262
0x18000b213  xorps   xmm0, xmm0
0x18000b216  xor     eax, eax
0x18000b218  movups  xmmword ptr [rbp+220h+pvar], xmm0
0x18000b21c  mov     [rbp+220h+var_238], rax
0x18000b220  mov     rcx, [rbp+220h+var_280]
0x18000b224  mov     rax, [rcx]
0x18000b227  lea     r8, [rbp+220h+pvar]
0x18000b22b  lea     rdx, PKEY_Multicast_Target_SessionDescriptor
0x18000b232  mov     rax, [rax+28h]
0x18000b236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b23b  cmp     word ptr [rbp+220h+pvar], 41h ; 'A'
0x18000b240  jnz     short loc_18000B258
0x18000b242  cmp     dword ptr [rbp+220h+pvar+8], 24h ; '$'
0x18000b246  jnz     short loc_18000B258
0x18000b248  mov     rax, [rbp+220h+var_238]
0x18000b24c  movups  xmm0, xmmword ptr [rax+14h]
0x18000b250  movdqu  [rbp+220h+var_58], xmm0
0x18000b258  lea     rcx, [rbp+220h+pvar]; pvar
0x18000b25c  call    cs:__imp_PropVariantClear
0x18000b262  xorps   xmm0, xmm0
0x18000b265  xor     eax, eax
0x18000b267  movups  xmmword ptr [rbp+220h+var_88], xmm0
0x18000b26e  mov     [rbp+220h+var_78], rax
0x18000b275  mov     rcx, [rbp+220h+var_280]
0x18000b279  mov     rax, [rcx]
0x18000b27c  lea     r8, [rbp+220h+var_88]
0x18000b283  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x18000b28a  mov     rax, [rax+28h]
0x18000b28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b293  test    eax, eax
0x18000b295  js      short loc_18000B2A7
0x18000b297  cmp     word ptr [rbp+220h+var_88], 13h
0x18000b29f  cmovz   r15d, dword ptr [rbp+220h+var_88+8]
0x18000b2a7  cmp     [rbp+220h+var_274], edi
0x18000b2aa  jnz     loc_18000B331
0x18000b2b0  mov     rcx, [rbp+220h+var_280]
0x18000b2b4  mov     rax, [rcx]
0x18000b2b7  lea     r8, [rbp+220h+var_160]
0x18000b2be  lea     rdx, PKEY_Devices_MicrophoneArray_Geometry
0x18000b2c5  mov     rax, [rax+28h]
0x18000b2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ce  test    eax, eax
0x18000b2d0  js      short loc_18000B331
0x18000b2d2  mov     eax, 1011h
0x18000b2d7  cmp     word ptr [rbp+220h+var_160], ax
0x18000b2de  jnz     short loc_18000B331
0x18000b2e0  mov     rdx, [rbp+220h+var_150]
0x18000b2e7  test    rdx, rdx
0x18000b2ea  jz      short loc_18000B331
0x18000b2ec  cmp     dword ptr [rbp+220h+var_160+8], 12h
0x18000b2f3  jb      short loc_18000B331
0x18000b2f5  movzx   r8d, word ptr [rdx+10h]
0x18000b2fa  mov     [rbp+220h+var_298], r8w
0x18000b2ff  lea     rcx, [r8+r8*2]
0x18000b303  lea     rcx, ds:12h[rcx*4]
0x18000b30b  mov     eax, dword ptr [rbp+220h+var_160+8]
0x18000b311  cmp     rax, rcx
0x18000b314  jb      short loc_18000B32A
0x18000b316  mov     rbx, rdx
0x18000b319  mov     eax, 10h
0x18000b31e  cmp     r8w, ax
0x18000b322  jbe     short loc_18000B331
0x18000b324  mov     [rbp+220h+var_298], ax
0x18000b328  jmp     short loc_18000B331
0x18000b32a  mov     rbx, rsi
0x18000b32d  mov     [rbp+220h+var_298], si
0x18000b331  mov     rcx, [rbp+220h+var_280]
0x18000b335  mov     rax, [rcx]
0x18000b338  lea     r8, [rbp+220h+var_190]
0x18000b33f  lea     rdx, PKEY_Devices_AudioPosture_Support
0x18000b346  mov     rax, [rax+28h]
0x18000b34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b34f  test    eax, eax
0x18000b351  js      short loc_18000B36C
0x18000b353  cmp     word ptr [rbp+220h+var_190], 0Bh
0x18000b35b  jnz     short loc_18000B36C
0x18000b35d  mov     r12d, esi
0x18000b360  cmp     word ptr [rbp+220h+var_190+8], 0FFFFh
0x18000b368  setz    r12b
0x18000b36c  lea     rcx, [rbp+220h+var_88]; pvar
0x18000b373  call    cs:__imp_PropVariantClear
0x18000b379  xorps   xmm0, xmm0
0x18000b37c  xor     eax, eax
0x18000b37e  movups  xmmword ptr [rbp+220h+var_A0], xmm0
0x18000b385  mov     [rbp+220h+var_90], rax
0x18000b38c  movups  xmmword ptr [rbp+220h+var_70], xmm0
0x18000b393  mov     [rbp+220h+var_60], rax
0x18000b39a  lea     r13, LocaleName
0x18000b3a1  mov     rsi, r13
0x18000b3a4  movups  xmmword ptr [rbp+220h+var_1C0], xmm0
0x18000b3a8  mov     [rbp+220h+var_1B0], rax
0x18000b3ac  xor     ecx, ecx
0x18000b3ae  mov     [rbp+220h+var_260], rcx
0x18000b3b2  mov     [rbp+220h+var_1D8], rcx
0x18000b3b6  lea     rdx, [rbp+220h+var_1D8]; struct IMMDevice **
0x18000b3ba  mov     rcx, r14; struct IMMDevice *
0x18000b3bd  call    ?GetPnpDevnodeFromMMDevice@AEBTelemetry@@CAJPEAUIMMDevice@@PEAPEAU2@@Z; AEBTelemetry::GetPnpDevnodeFromMMDevice(IMMDevice *,IMMDevice * *)
0x18000b3c2  xor     edx, edx
0x18000b3c4  test    eax, eax
0x18000b3c6  js      loc_18000B4A1
0x18000b3cc  mov     r14, [rbp+220h+var_1D8]
0x18000b3d0  mov     rax, [r14]
0x18000b3d3  mov     rax, [rax+20h]
0x18000b3d7  mov     [rbp+220h+var_268], rax
0x18000b3db  mov     rcx, [rbp+220h+var_260]
0x18000b3df  mov     [rbp+220h+var_260], rdx
0x18000b3e3  test    rcx, rcx
0x18000b3e6  jz      short loc_18000B3F8
0x18000b3e8  mov     rdx, [rcx]
0x18000b3eb  mov     rax, [rdx+10h]
0x18000b3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f4  mov     rax, [rbp+220h+var_268]
0x18000b3f8  lea     r8, [rbp+220h+var_260]
0x18000b3fc  xor     edx, edx
0x18000b3fe  mov     rcx, r14
0x18000b401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b406  xor     r14d, r14d
0x18000b409  test    eax, eax
0x18000b40b  js      loc_18000B4A1
0x18000b411  mov     rcx, [rbp+220h+var_260]
0x18000b415  mov     rax, [rcx]
0x18000b418  lea     r8, [rbp+220h+var_A0]
0x18000b41f  lea     rdx, DEVPKEY_Device_HardwareIds
0x18000b426  mov     rax, [rax+28h]
0x18000b42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b42f  test    eax, eax
0x18000b431  js      short loc_18000B454
0x18000b433  mov     eax, 101Fh
0x18000b438  cmp     word ptr [rbp+220h+var_A0], ax
0x18000b43f  jnz     short loc_18000B454
0x18000b441  cmp     dword ptr [rbp+220h+var_A0+8], r14d
0x18000b448  jz      short loc_18000B454
0x18000b44a  mov     rax, [rbp+220h+var_90]
0x18000b451  mov     r13, [rax]
0x18000b454  mov     rcx, [rbp+220h+var_260]
0x18000b458  mov     rax, [rcx]
0x18000b45b  lea     r8, [rbp+220h+var_70]
0x18000b462  lea     rdx, DEVPKEY_Device_Parent
0x18000b469  mov     rax, [rax+28h]
0x18000b46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b472  test    eax, eax
0x18000b474  js      short loc_18000B486
0x18000b476  cmp     word ptr [rbp+220h+var_70], 1Fh
0x18000b47e  cmovz   rsi, [rbp+220h+var_70+8]
0x18000b486  mov     rcx, [rbp+220h+var_260]
0x18000b48a  mov     rax, [rcx]
0x18000b48d  lea     r8, [rbp+220h+var_1C0]
0x18000b491  lea     rdx, DEVPKEY_Device_InstanceId
0x18000b498  mov     rax, [rax+28h]
0x18000b49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x18000b4a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x18000b4ad  test    al, al
0x18000b4af  jz      loc_18000B826
0x18000b4b5  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18000b4ba  mov     r14, rax
0x18000b4bd  mov     ecx, [rax]
0x18000b4bf  cmp     ecx, 4
0x18000b4c2  jbe     loc_18000BB7C
0x18000b4c8  mov     rdx, 800000000000h
0x18000b4d2  mov     rcx, rax
  ... truncated ...
```
