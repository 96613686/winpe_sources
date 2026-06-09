# CAvEndpointBuilder::OnApoStateChange(ushort const *)

- ea: `0x180050048`
- end: `0x180050851`
- name: `?OnApoStateChange@CAvEndpointBuilder@@QEAAJPEBG@Z`
- size: `2057`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043290`

## callees

- `0x18000128c`
- `0x180001f84`
- `0x180006b0c`
- `0x180008404`
- `0x18000fb60`
- `0x180010da8`
- `0x18001ef04`
- `0x18001f374`
- `0x180021030`
- `0x180023fbc`
- `0x180025340`
- `0x180048c24`
- `0x180050048`
- `0x180058cac`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050144`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005063a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800506ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050144`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005063a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800506ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050074`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050074`
- `MMDevAPI!__imp_mmdDevGetDeviceIdFromPnpInterface` at `0x1800503d9`
- `MMDevAPI!__imp_mmdDevGetDeviceIdFromPnpInterface` at `0x1800503d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800501af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800501af`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800504f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800505c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050687`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005071a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005078b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800507fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800504f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800505c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050687`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005071a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005078b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800507fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800505d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005072a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005079b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005080c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800505d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005072a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005079b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005080c`

## string_xrefs

- `0x180050106`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800501c2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180050237`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180050294`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005065d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180050704`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180050775`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800507e6`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CAvEndpointBuilder::OnApoStateChange(CAvEndpointBuilder *this, const unsigned __int16 *a2)
{
  LPCRITICAL_SECTION v2; // rsi
  const struct _tlgProvider_t *v3; // rax
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, const unsigned __int16 *, __int64 *); // rbx
  HRESULT v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, GUID *, __int64 **); // rbx
  int v15; // eax
  int v16; // eax
  const struct _tlgProvider_t *v17; // rax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // r14d
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, LPVOID *); // rbx
  int v27; // eax
  const struct _tlgProvider_t *v28; // rax
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  struct IMMDevice *v36; // r15
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // r12
  LPVOID v38; // rcx
  int v39; // eax
  unsigned int v40; // r15d
  int v41; // r15d
  const struct _tlgProvider_t *v42; // rax
  int v43; // r8d
  int v44; // r9d
  int ppv; // [rsp+20h] [rbp-B9h]
  int ppva; // [rsp+20h] [rbp-B9h]
  __int64 v47; // [rsp+40h] [rbp-99h] BYREF
  LPVOID v48; // [rsp+48h] [rbp-91h] BYREF
  __int64 *v49; // [rsp+50h] [rbp-89h] BYREF
  __int64 v50; // [rsp+58h] [rbp-81h] BYREF
  struct IMMDevice *v51; // [rsp+60h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-71h] BYREF
  __int64 v53; // [rsp+70h] [rbp-69h] BYREF
  __int64 v54; // [rsp+78h] [rbp-61h] BYREF
  LPVOID v55; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v56[3]; // [rsp+88h] [rbp-51h] BYREF
  char v57; // [rsp+A0h] [rbp-39h]
  PROPVARIANT v58[2]; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-21h]
  int v60[2]; // [rsp+C0h] [rbp-19h] BYREF
  LPVOID v61; // [rsp+C8h] [rbp-11h] BYREF
  PROPVARIANT pvar[2]; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v63; // [rsp+E0h] [rbp+7h]
  LPCRITICAL_SECTION v64; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]
  CAvEndpointBuilder *v66; // [rsp+140h] [rbp+67h] BYREF
  const unsigned __int16 *v67; // [rsp+148h] [rbp+6Fh] BYREF
  const unsigned __int16 *v68; // [rsp+150h] [rbp+77h] BYREF
  int v69; // [rsp+158h] [rbp+7Fh] BYREF

  v67 = a2;
  v66 = this;
  v2 = AvEndpointBuilder;
  EnterCriticalSection(AvEndpointBuilder);
  v64 = v2;
  v47 = 0;
  v50 = 0;
  LOBYTE(v66) = 0;
  v3 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v3 > 4u )
  {
    v68 = v67;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v3,
      (unsigned int)byte_180076CB3,
      v4,
      v5,
      (__int64)&v68);
  }
  v56[0] = &v66;
  v56[1] = v2;
  v56[2] = &v67;
  v57 = 1;
  v6 = v47;
  v47 = 0;
  v7 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v6, &v47);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8FF,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    v57 = 0;
    lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
LABEL_5:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
    if ( v2 )
      LeaveCriticalSection(v2);
    return v8;
  }
  v10 = v47;
  v11 = *(int (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v47 + 64LL);
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v50);
  if ( v11(v10, v67, &v50) < 0 )
  {
LABEL_45:
    v57 = 0;
    lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
  v49 = 0;
  LODWORD(v68) = 0;
  v48 = 0;
  v12 = CoCreateInstance(
          &GUID_06cca63e_9941_441b_b004_39f999ada412,
          0,
          0x17u,
          &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
          &v48);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x909,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v12,
      ppva);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    v57 = 0;
    lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
    goto LABEL_5;
  }
  v13 = v50;
  v14 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 **))(*(_QWORD *)v50 + 24LL);
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v49);
  v15 = v14(v13, &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196, &v49);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90C,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v15,
      ppva);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    v57 = 0;
    lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
    goto LABEL_5;
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 **))(*v49 + 24))(v49, &v68);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90D,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v16,
      ppva);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    v57 = 0;
    lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
    goto LABEL_5;
  }
  v17 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v17 > 4u )
  {
    v69 = (int)v68;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v17,
      (unsigned int)byte_180076C69,
      v18,
      v19,
      (__int64)&v69);
  }
  v20 = 0;
  if ( !(_DWORD)v68 )
  {
LABEL_44:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    goto LABEL_45;
  }
  while ( 1 )
  {
    v54 = 0;
    v53 = 0;
    pv = 0;
    *(_OWORD *)v58 = 0;
    v59 = 0;
    v21 = *v49;
    v54 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v21 + 32))(v49, v20, &v54);
    v8 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91D,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v22,
        ppva);
      PropVariantClear(v58);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_59;
    }
    v23 = v53;
    v53 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = wil::com_query_to_nothrow<IPnpInterface,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v54, &v53);
    v8 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91E,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v24,
        ppva);
      PropVariantClear(v58);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_59;
    }
    v25 = v54;
    v26 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v54 + 40LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    v27 = v26(v25, &pv);
    v8 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x921,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v27,
        ppva);
      PropVariantClear(v58);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_59:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
      v57 = 0;
      lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
      goto LABEL_5;
    }
    v28 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v28 > 4u )
    {
      v55 = pv;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v28,
        (unsigned int)&unk_180076C28,
        v29,
        v30,
        (__int64)&v55);
    }
    if ( (int)mmdDevGetDeviceIdFromPnpInterface(v53, v58) >= 0 )
    {
      v31 = 0;
      if ( LODWORD(v58[1]) )
        break;
    }
LABEL_41:
    PropVariantClear(v58);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
    if ( ++v20 >= (unsigned int)v68 )
      goto LABEL_44;
  }
  while ( 1 )
  {
    v51 = 0;
    if ( *(_QWORD *)(v59 + 8LL * v31) )
    {
      lpVtbl = g_DeviceEnumerator->lpVtbl;
      v51 = 0;
      if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, struct IMMDevice **))lpVtbl[1].Release)(
             g_DeviceEnumerator,
             *(_QWORD *)(v59 + 8LL * v31),
             &v51) >= 0 )
        break;
    }
LABEL_40:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
    if ( ++v31 >= LODWORD(v58[1]) )
      goto LABEL_41;
  }
  v55 = 0;
  v33 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v33 > 4u )
  {
    *(_QWORD *)v60 = *(_QWORD *)(v59 + 8LL * v31);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v33,
      (unsigned int)byte_180076BEB,
      v34,
      v35,
      (__int64)v60);
  }
  (*(void (__fastcall **)(LPVOID, struct IMMDevice *, __int64))(*(_QWORD *)v48 + 40LL))(v48, v51, 4);
  v36 = v51;
  OpenPropertyStore = v51->lpVtbl->OpenPropertyStore;
  v38 = v55;
  v55 = 0;
  if ( v38 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
  if ( ((int (__fastcall *)(struct IMMDevice *, __int64, LPVOID *))OpenPropertyStore)(v36, 1, &v55) >= 0 )
  {
    *(_OWORD *)pvar = 0;
    v63 = 0;
    LOWORD(pvar[0]) = 19;
    LODWORD(pvar[1]) = 64;
    (*(void (__fastcall **)(LPVOID, __int64 *, PROPVARIANT *))(*(_QWORD *)v55 + 48LL))(
      v55,
      PKEY_AudioEndpoint_MigrationReason,
      pvar);
    PropVariantClear(pvar);
  }
  CAudioDeviceManager::NotifyRemoveLocalAudioDevice((CAudioDeviceManager *)v2[2].LockSemaphore, v51);
  v39 = (*(__int64 (__fastcall **)(LPVOID, struct IMMDevice *, __int64))(*(_QWORD *)v48 + 56LL))(v48, v51, 1);
  v40 = v39;
  if ( v39 >= 0 )
  {
    v41 = (*(__int64 (__fastcall **)(LPVOID, struct IMMDevice *))(*(_QWORD *)v48 + 104LL))(v48, v51);
    if ( v41 < 0 )
    {
      v42 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v42 > 3u )
      {
        *(_QWORD *)v60 = *(_QWORD *)(v59 + 8LL * v31);
        v61 = pv;
        v69 = v41;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v42,
          (unsigned int)byte_180076B21,
          v43,
          v44,
          (__int64)&v69,
          (__int64)&v61,
          (__int64)v60);
      }
    }
    LOBYTE(v66) = 1;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
    goto LABEL_40;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x94A,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v39,
    ppva);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
  PropVariantClear(v58);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  v57 = 0;
  lambda_392b5c790ca148ea101e67676c2d4f52_::operator()(v56);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  LeaveCriticalSection(v2);
  return v40;
}

```

## disassembly

```asm
0x180050048  mov     [rsp-8+arg_8], rdx
0x18005004d  mov     [rsp-8+arg_0], rcx
0x180050052  push    rbp
0x180050053  push    rbx
0x180050054  push    rsi
0x180050055  push    rdi
0x180050056  push    r12
0x180050058  push    r13
0x18005005a  push    r14
0x18005005c  push    r15
0x18005005e  lea     rbp, [rsp-1Fh]
0x180050063  sub     rsp, 0F8h
0x18005006a  mov     rsi, cs:?AvEndpointBuilder@@3PEAVCAvEndpointBuilder@@EA; CAvEndpointBuilder * AvEndpointBuilder
0x180050071  mov     rcx, rsi; lpCriticalSection
0x180050074  call    cs:__imp_EnterCriticalSection
0x18005007a  mov     [rbp+57h+var_48], rsi
0x18005007e  xor     r13d, r13d
0x180050081  mov     [rsp+130h+var_F0], r13
0x180050086  mov     [rsp+130h+var_D8], r13
0x18005008b  mov     byte ptr [rbp+57h+arg_0], r13b
0x18005008f  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180050094  mov     ecx, [rax]
0x180050096  cmp     ecx, 4
0x180050099  jbe     short loc_1800500BB
0x18005009b  mov     rcx, [rbp+57h+arg_8]
0x18005009f  mov     [rbp+57h+arg_10], rcx
0x1800500a3  lea     rcx, [rbp+57h+arg_10]
0x1800500a7  mov     [rsp+130h+ppv], rcx; int
0x1800500ac  lea     rdx, byte_180076CB3
0x1800500b3  mov     rcx, rax
0x1800500b6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800500bb  lea     rax, [rbp+57h+arg_0]
0x1800500bf  mov     [rbp+57h+var_A8], rax
0x1800500c3  mov     [rbp+57h+var_A0], rsi
0x1800500c7  lea     rax, [rbp+57h+arg_8]
0x1800500cb  mov     [rbp+57h+var_98], rax
0x1800500cf  mov     [rbp+57h+var_90], 1
0x1800500d3  mov     rcx, [rsp+130h+var_F0]
0x1800500d8  mov     [rsp+130h+var_F0], r13
0x1800500dd  test    rcx, rcx
0x1800500e0  jz      short loc_1800500EF
0x1800500e2  mov     rax, [rcx]
0x1800500e5  mov     rax, [rax+10h]
0x1800500e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500ee  nop
0x1800500ef  lea     rdx, [rsp+130h+var_F0]
0x1800500f4  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x1800500f9  mov     ebx, eax
0x1800500fb  test    eax, eax
0x1800500fd  jns     short loc_180050151
0x1800500ff  mov     rcx, [rbp+5Fh]; this
0x180050103  mov     r9d, eax; char *
0x180050106  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18005010d  mov     edx, 8FFh; void *
0x180050112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050117  nop
0x180050118  mov     [rbp+57h+var_90], r13b
0x18005011c  lea     rcx, [rbp+57h+var_A8]
0x180050120  call    _lambda_392b5c790ca148ea101e67676c2d4f52___operator__
0x180050125  nop
0x180050126  lea     rcx, [rsp+130h+var_D8]
0x18005012b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050130  nop
0x180050131  lea     rcx, [rsp+130h+var_F0]
0x180050136  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005013b  nop
0x18005013c  test    rsi, rsi
0x18005013f  jz      short loc_18005014A
0x180050141  mov     rcx, rsi; lpCriticalSection
0x180050144  call    cs:__imp_LeaveCriticalSection
0x18005014a  mov     eax, ebx
0x18005014c  jmp     loc_180050642
0x180050151  mov     rdi, [rsp+130h+var_F0]
0x180050156  mov     rax, [rdi]
0x180050159  mov     rbx, [rax+40h]
0x18005015d  lea     rcx, [rsp+130h+var_D8]
0x180050162  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180050167  lea     r8, [rsp+130h+var_D8]
0x18005016c  mov     rdx, [rbp+57h+arg_8]
0x180050170  mov     rcx, rdi
0x180050173  mov     rax, rbx
0x180050176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005017b  test    eax, eax
0x18005017d  js      loc_18005060E
0x180050183  mov     [rsp+130h+var_E0], r13
0x180050188  mov     dword ptr [rbp+57h+arg_10], r13d
0x18005018c  mov     [rsp+130h+var_E8], r13
0x180050191  lea     rax, [rsp+130h+var_E8]
0x180050196  mov     [rsp+130h+ppv], rax; int
0x18005019b  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x1800501a2  xor     edx, edx; pUnkOuter
0x1800501a4  lea     r8d, [rdx+17h]; dwClsContext
0x1800501a8  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x1800501af  call    cs:__imp_CoCreateInstance
0x1800501b5  mov     ebx, eax
0x1800501b7  test    eax, eax
0x1800501b9  jns     short loc_1800501FD
0x1800501bb  mov     rcx, [rbp+5Fh]; this
0x1800501bf  mov     r9d, eax; char *
0x1800501c2  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800501c9  mov     edx, 909h; void *
0x1800501ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800501d3  nop
0x1800501d4  lea     rcx, [rsp+130h+var_E8]
0x1800501d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800501de  nop
0x1800501df  lea     rcx, [rsp+130h+var_E0]
0x1800501e4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800501e9  nop
0x1800501ea  mov     [rbp+57h+var_90], r13b
0x1800501ee  lea     rcx, [rbp+57h+var_A8]
0x1800501f2  call    _lambda_392b5c790ca148ea101e67676c2d4f52___operator__
0x1800501f7  nop
0x1800501f8  jmp     loc_180050126
0x1800501fd  mov     rdi, [rsp+130h+var_D8]
0x180050202  mov     rax, [rdi]
0x180050205  mov     rbx, [rax+18h]
0x180050209  lea     rcx, [rsp+130h+var_E0]
0x18005020e  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x180050213  lea     r8, [rsp+130h+var_E0]
0x180050218  lea     rdx, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x18005021f  mov     rcx, rdi
0x180050222  mov     rax, rbx
0x180050225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005022a  mov     ebx, eax
0x18005022c  test    eax, eax
0x18005022e  jns     short loc_180050272
0x180050230  mov     rcx, [rbp+5Fh]; this
0x180050234  mov     r9d, eax; char *
0x180050237  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18005023e  mov     edx, 90Ch; void *
0x180050243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050248  nop
0x180050249  lea     rcx, [rsp+130h+var_E8]
0x18005024e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050253  nop
0x180050254  lea     rcx, [rsp+130h+var_E0]
0x180050259  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005025e  nop
0x18005025f  mov     [rbp+57h+var_90], r13b
0x180050263  lea     rcx, [rbp+57h+var_A8]
0x180050267  call    _lambda_392b5c790ca148ea101e67676c2d4f52___operator__
0x18005026c  nop
0x18005026d  jmp     loc_180050126
0x180050272  mov     rcx, [rsp+130h+var_E0]
0x180050277  mov     rax, [rcx]
0x18005027a  lea     rdx, [rbp+57h+arg_10]
0x18005027e  mov     rax, [rax+18h]
0x180050282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050287  mov     ebx, eax
0x180050289  test    eax, eax
0x18005028b  jns     short loc_1800502CF
0x18005028d  mov     rcx, [rbp+5Fh]; this
0x180050291  mov     r9d, eax; char *
0x180050294  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18005029b  mov     edx, 90Dh; void *
0x1800502a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800502a5  nop
0x1800502a6  lea     rcx, [rsp+130h+var_E8]
0x1800502ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800502b0  nop
0x1800502b1  lea     rcx, [rsp+130h+var_E0]
0x1800502b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800502bb  nop
0x1800502bc  mov     [rbp+57h+var_90], r13b
0x1800502c0  lea     rcx, [rbp+57h+var_A8]
0x1800502c4  call    _lambda_392b5c790ca148ea101e67676c2d4f52___operator__
0x1800502c9  nop
0x1800502ca  jmp     loc_180050126
0x1800502cf  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800502d4  mov     ecx, [rax]
0x1800502d6  cmp     ecx, 4
0x1800502d9  jbe     short loc_1800502F9
0x1800502db  mov     ecx, dword ptr [rbp+57h+arg_10]
0x1800502de  mov     [rbp+57h+arg_18], ecx
0x1800502e1  lea     rcx, [rbp+57h+arg_18]
0x1800502e5  mov     [rsp+130h+ppv], rcx; int
0x1800502ea  lea     rdx, byte_180076C69
0x1800502f1  mov     rcx, rax
0x1800502f4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800502f9  mov     r14d, r13d
0x1800502fc  cmp     dword ptr [rbp+57h+arg_10], r13d
0x180050300  jbe     loc_1800505F8
0x180050306  mov     [rbp+57h+var_B8], r13
0x18005030a  mov     [rbp+57h+var_C0], r13
0x18005030e  mov     [rbp+57h+pv], r13
0x180050312  xorps   xmm0, xmm0
0x180050315  xor     eax, eax
0x180050317  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18005031b  mov     [rbp+57h+var_78], rax
0x18005031f  mov     rcx, [rsp+130h+var_E0]
0x180050324  mov     rax, [rcx]
0x180050327  mov     [rbp+57h+var_B8], r13
0x18005032b  lea     r8, [rbp+57h+var_B8]
0x18005032f  mov     edx, r14d
0x180050332  mov     rax, [rax+20h]
0x180050336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005033b  mov     ebx, eax
0x18005033d  test    eax, eax
0x18005033f  js      loc_1800507DF
0x180050345  mov     rcx, [rbp+57h+var_C0]
0x180050349  mov     [rbp+57h+var_C0], r13
0x18005034d  test    rcx, rcx
0x180050350  jz      short loc_18005035F
0x180050352  mov     rax, [rcx]
0x180050355  mov     rax, [rax+10h]
0x180050359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005035e  nop
0x18005035f  lea     rdx, [rbp+57h+var_C0]
0x180050363  lea     rcx, [rbp+57h+var_B8]
0x180050367  call    ??$com_query_to_nothrow@UIPnpInterface@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIPnpInterface@@@Z; wil::com_query_to_nothrow<IPnpInterface,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IPnpInterface * *)
0x18005036c  mov     ebx, eax
0x18005036e  test    eax, eax
0x180050370  js      loc_18005076E
0x180050376  mov     rdi, [rbp+57h+var_B8]
0x18005037a  mov     rax, [rdi]
0x18005037d  mov     rbx, [rax+28h]
0x180050381  xor     edx, edx
0x180050383  lea     rcx, [rbp+57h+pv]
0x180050387  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005038c  lea     rdx, [rbp+57h+pv]
0x180050390  mov     rcx, rdi
0x180050393  mov     rax, rbx
0x180050396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005039b  mov     ebx, eax
0x18005039d  test    eax, eax
0x18005039f  js      loc_1800506FD
0x1800503a5  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800503aa  mov     ecx, [rax]
0x1800503ac  cmp     ecx, 4
0x1800503af  jbe     short loc_1800503D1
0x1800503b1  mov     rcx, [rbp+57h+pv]
0x1800503b5  mov     [rbp+57h+var_B0], rcx
0x1800503b9  lea     rcx, [rbp+57h+var_B0]
0x1800503bd  mov     [rsp+130h+ppv], rcx
0x1800503c2  lea     rdx, unk_180076C28
0x1800503c9  mov     rcx, rax
0x1800503cc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800503d1  lea     rdx, [rbp+57h+var_88]
0x1800503d5  mov     rcx, [rbp+57h+var_C0]
0x1800503d9  call    cs:__imp_mmdDevGetDeviceIdFromPnpInterface
0x1800503df  test    eax, eax
0x1800503e1  js      loc_1800505BD
0x1800503e7  mov     ebx, r13d
0x1800503ea  cmp     dword ptr [rbp+57h+var_88+8], r13d
0x1800503ee  jbe     loc_1800505BD
0x1800503f4  mov     [rbp+57h+var_D0], r13
0x1800503f8  mov     edi, ebx
0x1800503fa  mov     rdx, [rbp+57h+var_78]
0x1800503fe  cmp     [rdx+rdi*8], r13
0x180050402  jz      loc_1800505A9
0x180050408  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18005040f  mov     rax, [rcx]
0x180050412  mov     [rbp+57h+var_D0], r13
0x180050416  lea     r8, [rbp+57h+var_D0]
0x18005041a  mov     rdx, [rdx+rdi*8]
0x18005041e  mov     rax, [rax+28h]
0x180050422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050427  test    eax, eax
0x180050429  js      loc_1800505A9
0x18005042f  mov     [rbp+57h+var_B0], r13
0x180050433  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180050438  mov     ecx, [rax]
0x18005043a  cmp     ecx, 4
0x18005043d  jbe     short loc_180050463
0x18005043f  mov     rcx, [rbp+57h+var_78]
0x180050443  mov     rdx, [rcx+rdi*8]
0x180050447  mov     qword ptr [rbp+57h+var_70], rdx
0x18005044b  lea     rcx, [rbp+57h+var_70]
0x18005044f  mov     [rsp+130h+ppv], rcx; int
0x180050454  lea     rdx, byte_180076BEB
0x18005045b  mov     rcx, rax
0x18005045e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180050463  mov     rcx, [rsp+130h+var_E8]
0x180050468  mov     rax, [rcx]
0x18005046b  mov     r8d, 4
0x180050471  mov     rdx, [rbp+57h+var_D0]
0x180050475  mov     rax, [rax+28h]
0x180050479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005047e  mov     r15, [rbp+57h+var_D0]
0x180050482  mov     rax, [r15]
0x180050485  mov     r12, [rax+20h]
0x180050489  mov     rcx, [rbp+57h+var_B0]
0x18005048d  mov     [rbp+57h+var_B0], r13
0x180050491  test    rcx, rcx
0x180050494  jz      short loc_1800504A3
0x180050496  mov     rdx, [rcx]
0x180050499  mov     rax, [rdx+10h]
0x18005049d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504a2  nop
0x1800504a3  lea     r8, [rbp+57h+var_B0]
0x1800504a7  mov     edx, 1
0x1800504ac  mov     rcx, r15
0x1800504af  mov     rax, r12
0x1800504b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504b7  test    eax, eax
0x1800504b9  js      short loc_1800504FE
0x1800504bb  xorps   xmm0, xmm0
0x1800504be  xor     eax, eax
0x1800504c0  movups  xmmword ptr [rbp+57h+pvar], xmm0
  ... truncated ...
```
