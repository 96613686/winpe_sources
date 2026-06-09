# CAudioResourceManager::FindAppropriateStreamGroupAndSaDeviceForStream(EndpointCharacteristicsDescriptor *,ushort const *,IAudioStreamInfo *)

- ea: `0x1800e3490`
- end: `0x1800e3bb9`
- name: `?FindAppropriateStreamGroupAndSaDeviceForStream@CAudioResourceManager@@UEAAJPEAUEndpointCharacteristicsDescriptor@@PEBGPEAUIAudioStreamInfo@@@Z`
- size: `1833`
- prototype: `int(CAudioResourceManager *__hidden this, struct EndpointCharacteristicsDescriptor *, const unsigned __int16 *, struct IAudioStreamInfo *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e2fb0`

## callees

- `0x180002198`
- `0x180002a9c`
- `0x180009714`
- `0x18000accc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x180031778`
- `0x180031b20`
- `0x1800423cc`
- `0x18004f78c`
- `0x1800621b0`
- `0x1800639f4`
- `0x180073310`
- `0x1800e3490`
- `0x1800ebd70`
- `0x1800ec4c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e365f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e366d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3685`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e365f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e366d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3685`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e37e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3b91`

## string_xrefs

- `0x1800e34d9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e352f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e362c`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e36c8`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e3785`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e38cf`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e3900`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e3944`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e39df`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e3a8b`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioResourceManager::FindAppropriateStreamGroupAndSaDeviceForStream(
        CAudioResourceManager *this,
        CEndpointCharacteristics **a2,
        unsigned __int16 *a3,
        struct IAudioStreamInfo *a4)
{
  int EndpointStore; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  struct CEndpointStore *v11; // rdi
  int CustomResourceManagerService; // eax
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r14
  __int64 (__fastcall *v16)(__int64, _QWORD, struct IStreamGroupProxy **); // rsi
  int v17; // esi
  __int64 (__fastcall *v18)(struct IAudioStreamInfo *, struct IStreamGroupProxy **); // rsi
  int v19; // eax
  _DWORD *v20; // rdi
  int v21; // r8d
  int v22; // r9d
  int v23; // eax
  int v24; // edi
  _DWORD *v25; // r8
  __int64 v26; // r8
  _DWORD *v27; // r8
  __int64 v28; // r8
  struct IStreamGroupProxy *v29; // r14
  __int64 (__fastcall *v30)(struct IStreamGroupProxy *, __int64 *); // rsi
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rdx
  BOOL v34; // r12d
  int v35; // eax
  __int64 (__fastcall *v36)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, _QWORD); // r14
  __int64 v37; // rdx
  int v39; // [rsp+20h] [rbp-B9h]
  int v40; // [rsp+20h] [rbp-B9h]
  struct IStreamGroupProxy *v41; // [rsp+50h] [rbp-89h] BYREF
  LPCRITICAL_SECTION v42; // [rsp+58h] [rbp-81h] BYREF
  struct IStreamGroupProxy *v43; // [rsp+60h] [rbp-79h] BYREF
  void *v44; // [rsp+68h] [rbp-71h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-69h] BYREF
  LPCRITICAL_SECTION v46; // [rsp+78h] [rbp-61h] BYREF
  __int64 v47; // [rsp+80h] [rbp-59h] BYREF
  __int64 v48; // [rsp+88h] [rbp-51h] BYREF
  __int64 v49; // [rsp+90h] [rbp-49h] BYREF
  struct CEndpointStore *v50; // [rsp+98h] [rbp-41h] BYREF
  LPCRITICAL_SECTION v51; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v52; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-21h]
  struct IStreamGroupProxy *v54; // [rsp+C0h] [rbp-19h] BYREF
  int v55[2]; // [rsp+C8h] [rbp-11h] BYREF
  _QWORD v56[2]; // [rsp+D0h] [rbp-9h] BYREF
  char v57; // [rsp+E0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v50 = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(this, a3, &v50);
  v9 = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDDC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointStore,
      v39);
    goto LABEL_82;
  }
  v10 = *((_QWORD *)this + 6);
  v11 = v50;
  (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION *, struct CEndpointStore *))(*(_QWORD *)v10 + 80LL))(
    v10,
    &lpCriticalSection,
    v50);
  v44 = 0;
  CustomResourceManagerService = CEndpointCharacteristics::TryGetCustomResourceManagerService(
                                   *a2,
                                   &GUID_475d74a7_6824_4b91_89be_33d893b255ed,
                                   &v44);
  v9 = CustomResourceManagerService;
  if ( CustomResourceManagerService < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)CustomResourceManagerService,
      v39);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    goto LABEL_82;
  }
  v13 = 0;
  v42 = 0;
  if ( v44 )
  {
    v14 = (*(__int64 (__fastcall **)(void *, LPCRITICAL_SECTION *))(*(_QWORD *)v44 + 104LL))(v44, &v51);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v42,
      v14);
    if ( v51 )
      LeaveCriticalSection(v51);
    v13 = v42;
  }
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v11 + 13) + 128LL))(*((_QWORD *)v11 + 13), &v46);
  CAudioStream::LockConnectDisconnectFromStreamGroup(((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0), &v42);
  if ( !*(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 0x30) )
    goto LABEL_73;
  v43 = 0;
  v15 = *((_QWORD *)v11 + 13);
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IStreamGroupProxy **))(*(_QWORD *)v15 + 40LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v43);
  v17 = v16(v15, *(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 0x268), &v43);
  if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2147023728 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDFC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v17,
      v39);
LABEL_14:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
    if ( v42 )
      LeaveCriticalSection(v42);
    if ( v46 )
      LeaveCriticalSection(v46);
    if ( v13 )
      LeaveCriticalSection(v13);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v9 = v17;
    goto LABEL_82;
  }
  v41 = 0;
  v18 = *(__int64 (__fastcall **)(struct IAudioStreamInfo *, struct IStreamGroupProxy **))(*(_QWORD *)a4 + 120LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v41);
  v19 = v18(a4, &v41);
  v17 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDFF,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v19,
      v39);
LABEL_25:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
    goto LABEL_14;
  }
  if ( v43 )
  {
    v20 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v20 > 4u && (unsigned __int8)tlgKeywordOn(v20, 512) )
    {
      v51 = (LPCRITICAL_SECTION)a3;
      v54 = v41;
      *(_QWORD *)v55 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 80LL))(a4);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v20,
        (unsigned int)&unk_1801A1226,
        v21,
        v22,
        (__int64)v55,
        (__int64)&v54,
        (__int64)&v51);
    }
    if ( v43 != v41 )
    {
      v23 = CAudioStream::ConnectToNewStreamGroup(
              (CAudioStream *)(((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)),
              v43);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0D,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v23,
          v39);
LABEL_33:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
        if ( v42 )
          LeaveCriticalSection(v42);
        if ( v46 )
          LeaveCriticalSection(v46);
        if ( v13 )
          LeaveCriticalSection(v13);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        v9 = v24;
        goto LABEL_82;
      }
    }
    goto LABEL_72;
  }
  if ( (*(__int64 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v41 + 432LL))(v41) != 1 )
    goto LABEL_47;
  v25 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  if ( *v25 > 4u && (unsigned __int8)tlgKeywordOn(v25, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v26,
      &unk_1801A11D1);
  if ( (*(int (__fastcall **)(struct IStreamGroupProxy *, unsigned __int64))(*(_QWORD *)v41 + 448LL))(
         v41,
         (((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 576) < 0 )
  {
LABEL_47:
    v27 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v27 > 4u && (unsigned __int8)tlgKeywordOn(v27, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v28,
        &unk_1801A118B);
    v47 = 0;
    v29 = v41;
    v30 = *(__int64 (__fastcall **)(struct IStreamGroupProxy *, __int64 *))(*(_QWORD *)v41 + 224LL);
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v47);
    v31 = v30(v29, &v47);
    v17 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE28,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v31,
        v39);
LABEL_52:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
      goto LABEL_25;
    }
    if ( !v47 )
    {
      v24 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE29,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)0x8000FFFFLL,
        v39);
LABEL_55:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
      goto LABEL_33;
    }
    v32 = *(_QWORD *)a4;
    v48 = 0;
    v17 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *, __int64 *))(v32 + 192))(a4, &v48);
    if ( v17 < 0 )
    {
      v33 = 3628;
LABEL_58:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v17,
        v39);
LABEL_59:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
      goto LABEL_52;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, struct IAudioStreamInfo *, _QWORD))(*(_QWORD *)v48 + 72LL))(v48, a4, 0);
    if ( v17 < 0 )
    {
      v33 = 3630;
      goto LABEL_58;
    }
    v34 = (*(unsigned __int8 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v41 + 240LL))(v41) == 0;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v41);
    v52 = 0;
    v53 = 0;
    v35 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v47 + 240LL))(v47, &v52);
    v17 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE34,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v35,
        v39);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v52);
      goto LABEL_59;
    }
    v49 = 0;
    v36 = *(__int64 (__fastcall **)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, _QWORD))(*(_QWORD *)g_DeviceGraphManager + 56LL);
    v56[0] = &v49;
    v56[1] = 0;
    v57 = 1;
    v40 = (*(__int64 (**)(void))(*(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 8) + 72LL))();
    v24 = v36(
            g_DeviceGraphManager,
            a2,
            *((_QWORD *)v11 + 13),
            *(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 0x268));
    wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(v56);
    if ( v24 < 0 )
    {
      v37 = 3645;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v24,
        v40);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v49);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v52);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
      goto LABEL_55;
    }
    v40 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, __int64, BOOL, __int128 *))(*(_QWORD *)v49 + 208LL))(v49, v47, v34, &v52);
    if ( v24 < 0 )
    {
      v37 = 3647;
      goto LABEL_66;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, struct IAudioStreamInfo *, __int64, __int64))(*(_QWORD *)v48 + 64LL))(
            v48,
            a4,
            v49,
            1);
    if ( v24 < 0 )
    {
      v37 = 3649;
      goto LABEL_66;
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v49);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v52);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
  }
LABEL_72:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
LABEL_73:
  if ( v42 )
    LeaveCriticalSection(v42);
  if ( v46 )
    LeaveCriticalSection(v46);
  if ( v13 )
    LeaveCriticalSection(v13);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  v9 = 0;
LABEL_82:
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v50);
  return v9;
}

```

## disassembly

```asm
0x1800e3490  mov     [rsp-8+arg_8], rdx
0x1800e3495  push    rbp
0x1800e3496  push    rbx
0x1800e3497  push    rsi
0x1800e3498  push    rdi
0x1800e3499  push    r12
0x1800e349b  push    r13
0x1800e349d  push    r14
0x1800e349f  push    r15
0x1800e34a1  lea     rbp, [rsp-1Fh]
0x1800e34a6  sub     rsp, 0F8h
0x1800e34ad  mov     r15, r9
0x1800e34b0  mov     r12, r8
0x1800e34b3  mov     rsi, rdx
0x1800e34b6  mov     rdi, rcx
0x1800e34b9  xor     r14d, r14d
0x1800e34bc  mov     [rbp+57h+var_98], r14
0x1800e34c0  lea     r8, [rbp+57h+var_98]; struct CEndpointStore **
0x1800e34c4  mov     rdx, r12; unsigned __int16 *
0x1800e34c7  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1800e34cc  mov     ebx, eax
0x1800e34ce  test    eax, eax
0x1800e34d0  jns     short loc_1800E34EF
0x1800e34d2  mov     rcx, [rbp+5Fh]; this
0x1800e34d6  mov     r9d, eax; char *
0x1800e34d9  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e34e0  mov     edx, 0DDCh; void *
0x1800e34e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e34ea  jmp     loc_1800E3B9A
0x1800e34ef  mov     rcx, [rdi+30h]
0x1800e34f3  mov     rax, [rcx]
0x1800e34f6  mov     rdi, [rbp+57h+var_98]
0x1800e34fa  mov     r8, rdi
0x1800e34fd  lea     rdx, [rbp+57h+lpCriticalSection]
0x1800e3501  mov     rax, [rax+50h]
0x1800e3505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e350a  nop
0x1800e350b  mov     [rbp+57h+var_C8], r14
0x1800e350f  lea     r8, [rbp+57h+var_C8]; void **
0x1800e3513  lea     rdx, _GUID_475d74a7_6824_4b91_89be_33d893b255ed; struct _GUID *
0x1800e351a  mov     rcx, [rsi]; this
0x1800e351d  call    ?TryGetCustomResourceManagerService@CEndpointCharacteristics@@QEAAJAEBU_GUID@@PEAPEAX@Z; CEndpointCharacteristics::TryGetCustomResourceManagerService(_GUID const &,void * *)
0x1800e3522  mov     ebx, eax
0x1800e3524  test    eax, eax
0x1800e3526  jns     short loc_1800E3561
0x1800e3528  mov     rcx, [rbp+5Fh]; this
0x1800e352c  mov     r9d, eax; char *
0x1800e352f  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e3536  mov     edx, 0DE5h; void *
0x1800e353b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3540  lea     rcx, [rbp+57h+var_C8]
0x1800e3544  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e3549  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800e354d  test    rcx, rcx
0x1800e3550  jz      loc_1800E3B9A
0x1800e3556  call    cs:__imp_LeaveCriticalSection
0x1800e355c  jmp     loc_1800E3B9A
0x1800e3561  mov     rbx, r14
0x1800e3564  mov     [rsp+130h+var_D8], rbx
0x1800e3569  mov     rcx, [rbp+57h+var_C8]
0x1800e356d  test    rcx, rcx
0x1800e3570  jz      short loc_1800E35A3
0x1800e3572  mov     rax, [rcx]
0x1800e3575  lea     rdx, [rbp+57h+var_90]
0x1800e3579  mov     rax, [rax+68h]
0x1800e357d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3582  mov     rdx, rax
0x1800e3585  lea     rcx, [rsp+130h+var_D8]
0x1800e358a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x1800e358f  mov     rcx, [rbp+57h+var_90]; lpCriticalSection
0x1800e3593  test    rcx, rcx
0x1800e3596  jz      short loc_1800E359E
0x1800e3598  call    cs:__imp_LeaveCriticalSection
0x1800e359e  mov     rbx, [rsp+130h+var_D8]
0x1800e35a3  mov     rcx, [rdi+68h]
0x1800e35a7  mov     rax, [rcx]
0x1800e35aa  lea     rdx, [rbp+57h+var_B8]
0x1800e35ae  mov     rax, [rax+80h]
0x1800e35b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e35ba  mov     rax, r15
0x1800e35bd  lea     rcx, [r15-8]
0x1800e35c1  neg     rax
0x1800e35c4  sbb     r13, r13
0x1800e35c7  and     r13, rcx
0x1800e35ca  lea     rdx, [rsp+130h+var_D8]
0x1800e35cf  mov     rcx, r13
0x1800e35d2  call    ?LockConnectDisconnectFromStreamGroup@CAudioStream@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CAudioStream::LockConnectDisconnectFromStreamGroup(void)
0x1800e35d7  cmp     [r13+30h], r14
0x1800e35db  jz      loc_1800E3B52
0x1800e35e1  mov     [rbp+57h+var_D0], r14
0x1800e35e5  mov     r14, [rdi+68h]
0x1800e35e9  mov     rax, [r14]
0x1800e35ec  mov     rsi, [rax+28h]
0x1800e35f0  lea     rcx, [rbp+57h+var_D0]
0x1800e35f4  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800e35f9  lea     r8, [rbp+57h+var_D0]
0x1800e35fd  mov     rdx, [r13+268h]
0x1800e3604  mov     rcx, r14
0x1800e3607  mov     rax, rsi
0x1800e360a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e360f  mov     esi, eax
0x1800e3611  mov     eax, 80000000h
0x1800e3616  lea     ecx, [rsi+rax]
0x1800e3619  test    eax, ecx
0x1800e361b  jnz     short loc_1800E3692
0x1800e361d  cmp     esi, 80070490h
0x1800e3623  jz      short loc_1800E3692
0x1800e3625  mov     rcx, [rbp+5Fh]; this
0x1800e3629  mov     r9d, esi; char *
0x1800e362c  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e3633  mov     edx, 0DFCh; void *
0x1800e3638  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e363d  lea     rcx, [rbp+57h+var_D0]
0x1800e3641  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e3646  mov     rcx, [rsp+130h+var_D8]; lpCriticalSection
0x1800e364b  test    rcx, rcx
0x1800e364e  jz      short loc_1800E3656
0x1800e3650  call    cs:__imp_LeaveCriticalSection
0x1800e3656  mov     rcx, [rbp+57h+var_B8]; lpCriticalSection
0x1800e365a  test    rcx, rcx
0x1800e365d  jz      short loc_1800E3665
0x1800e365f  call    cs:__imp_LeaveCriticalSection
0x1800e3665  test    rbx, rbx
0x1800e3668  jz      short loc_1800E3673
0x1800e366a  mov     rcx, rbx; lpCriticalSection
0x1800e366d  call    cs:__imp_LeaveCriticalSection
0x1800e3673  lea     rcx, [rbp+57h+var_C8]
0x1800e3677  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e367c  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800e3680  test    rcx, rcx
0x1800e3683  jz      short loc_1800E368B
0x1800e3685  call    cs:__imp_LeaveCriticalSection
0x1800e368b  mov     ebx, esi
0x1800e368d  jmp     loc_1800E3B9A
0x1800e3692  xor     r14d, r14d
0x1800e3695  mov     [rsp+130h+var_E0], r14
0x1800e369a  mov     rax, [r15]
0x1800e369d  mov     rsi, [rax+78h]
0x1800e36a1  lea     rcx, [rsp+130h+var_E0]
0x1800e36a6  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800e36ab  lea     rdx, [rsp+130h+var_E0]
0x1800e36b0  mov     rcx, r15
0x1800e36b3  mov     rax, rsi
0x1800e36b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e36bb  mov     esi, eax
0x1800e36bd  test    eax, eax
0x1800e36bf  jns     short loc_1800E36E8
0x1800e36c1  mov     rcx, [rbp+5Fh]; this
0x1800e36c5  mov     r9d, eax; char *
0x1800e36c8  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e36cf  mov     edx, 0DFFh; void *
0x1800e36d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e36d9  lea     rcx, [rsp+130h+var_E0]
0x1800e36de  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e36e3  jmp     loc_1800E363D
0x1800e36e8  cmp     [rbp+57h+var_D0], r14
0x1800e36ec  jz      loc_1800E37F5
0x1800e36f2  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800e36f7  mov     rdi, [rax+8]
0x1800e36fb  mov     eax, [rdi]
0x1800e36fd  cmp     eax, 4
0x1800e3700  jbe     short loc_1800E375D
0x1800e3702  mov     edx, 200h
0x1800e3707  mov     rcx, rdi
0x1800e370a  call    _tlgKeywordOn
0x1800e370f  test    al, al
0x1800e3711  jz      short loc_1800E375D
0x1800e3713  mov     [rbp+57h+var_90], r12
0x1800e3717  mov     rax, [rsp+130h+var_E0]
0x1800e371c  mov     [rbp+57h+var_70], rax
0x1800e3720  mov     rax, [r15]
0x1800e3723  mov     rcx, r15
0x1800e3726  mov     rax, [rax+50h]
0x1800e372a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e372f  mov     qword ptr [rbp+57h+var_68], rax
0x1800e3733  lea     rax, [rbp+57h+var_90]
0x1800e3737  mov     [rsp+130h+var_100], rax
0x1800e373c  lea     rax, [rbp+57h+var_70]
0x1800e3740  mov     [rsp+130h+var_108], rax
0x1800e3745  lea     rax, [rbp+57h+var_68]
0x1800e3749  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800e374e  lea     rdx, unk_1801A1226
0x1800e3755  mov     rcx, rdi
0x1800e3758  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800e375d  mov     rdx, [rbp+57h+var_D0]; struct IStreamGroupProxy *
0x1800e3761  cmp     rdx, [rsp+130h+var_E0]
0x1800e3766  jz      loc_1800E3B3F
0x1800e376c  mov     rcx, r13; this
0x1800e376f  call    ?ConnectToNewStreamGroup@CAudioStream@@QEAAJPEAUIStreamGroupProxy@@@Z; CAudioStream::ConnectToNewStreamGroup(IStreamGroupProxy *)
0x1800e3774  mov     edi, eax
0x1800e3776  test    eax, eax
0x1800e3778  jns     loc_1800E3B3F
0x1800e377e  mov     rcx, [rbp+5Fh]; this
0x1800e3782  mov     r9d, eax; char *
0x1800e3785  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e378c  mov     edx, 0E0Dh; void *
0x1800e3791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3796  lea     rcx, [rsp+130h+var_E0]
0x1800e379b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e37a0  lea     rcx, [rbp+57h+var_D0]
0x1800e37a4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e37a9  mov     rcx, [rsp+130h+var_D8]; lpCriticalSection
0x1800e37ae  test    rcx, rcx
0x1800e37b1  jz      short loc_1800E37B9
0x1800e37b3  call    cs:__imp_LeaveCriticalSection
0x1800e37b9  mov     rcx, [rbp+57h+var_B8]; lpCriticalSection
0x1800e37bd  test    rcx, rcx
0x1800e37c0  jz      short loc_1800E37C8
0x1800e37c2  call    cs:__imp_LeaveCriticalSection
0x1800e37c8  test    rbx, rbx
0x1800e37cb  jz      short loc_1800E37D6
0x1800e37cd  mov     rcx, rbx; lpCriticalSection
0x1800e37d0  call    cs:__imp_LeaveCriticalSection
0x1800e37d6  lea     rcx, [rbp+57h+var_C8]
0x1800e37da  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e37df  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800e37e3  test    rcx, rcx
0x1800e37e6  jz      short loc_1800E37EE
0x1800e37e8  call    cs:__imp_LeaveCriticalSection
0x1800e37ee  mov     ebx, edi
0x1800e37f0  jmp     loc_1800E3B9A
0x1800e37f5  mov     rcx, [rsp+130h+var_E0]
0x1800e37fa  mov     rax, [rcx]
0x1800e37fd  mov     rax, [rax+1B0h]
0x1800e3804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3809  mov     esi, 200h
0x1800e380e  cmp     rax, 1
0x1800e3812  jnz     short loc_1800E3865
0x1800e3814  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800e3819  mov     r8, [rax+8]
0x1800e381d  mov     eax, [r8]
0x1800e3820  cmp     eax, 4
0x1800e3823  jbe     short loc_1800E3842
0x1800e3825  mov     edx, esi
0x1800e3827  mov     rcx, r8
0x1800e382a  call    _tlgKeywordOn
0x1800e382f  test    al, al
0x1800e3831  jz      short loc_1800E3842
0x1800e3833  lea     rdx, unk_1801A11D1
0x1800e383a  mov     rcx, r8
0x1800e383d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e3842  mov     rcx, [rsp+130h+var_E0]
0x1800e3847  mov     rax, [rcx]
0x1800e384a  lea     rdx, [r13+240h]
0x1800e3851  mov     rax, [rax+1C0h]
0x1800e3858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e385d  test    eax, eax
0x1800e385f  jns     loc_1800E3B3F
0x1800e3865  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800e386a  mov     r8, [rax+8]
0x1800e386e  mov     eax, [r8]
0x1800e3871  cmp     eax, 4
0x1800e3874  jbe     short loc_1800E3894
0x1800e3876  mov     rdx, rsi
0x1800e3879  mov     rcx, r8
0x1800e387c  call    _tlgKeywordOn
0x1800e3881  test    al, al
0x1800e3883  jz      short loc_1800E3894
0x1800e3885  lea     rdx, unk_1801A118B
0x1800e388c  mov     rcx, r8
0x1800e388f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e3894  mov     [rbp+57h+var_B0], r14
0x1800e3898  mov     r14, [rsp+130h+var_E0]
0x1800e389d  mov     rax, [r14]
0x1800e38a0  mov     rsi, [rax+0E0h]
0x1800e38a7  lea     rcx, [rbp+57h+var_B0]
0x1800e38ab  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800e38b0  lea     rdx, [rbp+57h+var_B0]
0x1800e38b4  mov     rcx, r14
0x1800e38b7  mov     rax, rsi
0x1800e38ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e38bf  mov     esi, eax
0x1800e38c1  xor     r14d, r14d
0x1800e38c4  test    eax, eax
0x1800e38c6  jns     short loc_1800E38EE
0x1800e38c8  mov     rcx, [rbp+5Fh]; this
0x1800e38cc  mov     r9d, eax; char *
0x1800e38cf  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e38d6  mov     edx, 0E28h; void *
0x1800e38db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e38e0  lea     rcx, [rbp+57h+var_B0]
0x1800e38e4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e38e9  jmp     loc_1800E36D9
0x1800e38ee  cmp     [rbp+57h+var_B0], r14
0x1800e38f2  jnz     short loc_1800E391F
0x1800e38f4  mov     rcx, [rbp+5Fh]; this
0x1800e38f8  mov     edi, 8000FFFFh
0x1800e38fd  mov     r9d, edi; char *
0x1800e3900  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e3907  mov     edx, 0E29h; void *
0x1800e390c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3911  lea     rcx, [rbp+57h+var_B0]
0x1800e3915  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e391a  jmp     loc_1800E3796
0x1800e391f  mov     rax, [r15]
0x1800e3922  mov     [rbp+57h+var_A8], r14
0x1800e3926  lea     rdx, [rbp+57h+var_A8]
0x1800e392a  mov     rcx, r15
0x1800e392d  mov     rax, [rax+0C0h]
0x1800e3934  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
