# CAudioResourceManager::FindAppropriateStreamGroupAndSaDeviceForStream(EndpointCharacteristicsDescriptor *,ushort const *,IAudioStreamInfo *)

- ea: `0x1800e2d10`
- end: `0x1800e3439`
- name: `?FindAppropriateStreamGroupAndSaDeviceForStream@CAudioResourceManager@@UEAAJPEAUEndpointCharacteristicsDescriptor@@PEBGPEAUIAudioStreamInfo@@@Z`
- size: `1833`
- prototype: `__int64 __fastcall(CAudioResourceManager *this, CEndpointCharacteristics **, unsigned __int16 *, struct IAudioStreamInfo *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e2834`

## callees

- `0x180002198`
- `0x180002ca8`
- `0x180009864`
- `0x18000ae1c`
- `0x18001280c`
- `0x18001b520`
- `0x1800318d8`
- `0x180031c80`
- `0x1800424ec`
- `0x18004f2fc`
- `0x180061d20`
- `0x180063564`
- `0x180072e10`
- `0x1800e2d10`
- `0x1800eb5f0`
- `0x1800ebd40`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2dd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2e18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2ed0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2f05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3033`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3050`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e33dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e33eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e33f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3411`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2dd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2e18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2ed0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2f05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3033`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3050`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e33dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e33eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e33f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3411`

## string_xrefs

- `0x1800e2d59`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e2daf`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e2eac`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e2f48`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e3005`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e314f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e3180`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e31c4`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e325f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800e330b`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
  __int64 v15; // rdx
  __int64 v16; // r14
  __int64 (__fastcall *v17)(__int64, _QWORD, struct IStreamGroupProxy **); // rsi
  __int64 v18; // rdx
  int v19; // esi
  __int64 (__fastcall *v20)(struct IAudioStreamInfo *, struct IStreamGroupProxy **); // rsi
  int v21; // eax
  _DWORD *v22; // rdi
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  int v26; // edi
  _DWORD *v27; // r8
  __int64 v28; // r8
  __int64 v29; // rdx
  _DWORD *v30; // r8
  __int64 v31; // r8
  struct IStreamGroupProxy *v32; // r14
  __int64 (__fastcall *v33)(struct IStreamGroupProxy *, __int64 *); // rsi
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rdx
  BOOL v37; // r12d
  __int64 v38; // rdx
  int v39; // eax
  __int64 (__fastcall *v40)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, _QWORD); // r14
  __int64 v41; // rdx
  int v43; // [rsp+20h] [rbp-B9h]
  int v44; // [rsp+20h] [rbp-B9h]
  struct IStreamGroupProxy *v45; // [rsp+50h] [rbp-89h] BYREF
  LPCRITICAL_SECTION v46; // [rsp+58h] [rbp-81h] BYREF
  struct IStreamGroupProxy *v47; // [rsp+60h] [rbp-79h] BYREF
  void *v48; // [rsp+68h] [rbp-71h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-69h] BYREF
  LPCRITICAL_SECTION v50; // [rsp+78h] [rbp-61h] BYREF
  __int64 v51; // [rsp+80h] [rbp-59h] BYREF
  __int64 v52; // [rsp+88h] [rbp-51h] BYREF
  __int64 v53; // [rsp+90h] [rbp-49h] BYREF
  struct CEndpointStore *v54; // [rsp+98h] [rbp-41h] BYREF
  LPCRITICAL_SECTION v55; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v56; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-21h]
  struct IStreamGroupProxy *v58; // [rsp+C0h] [rbp-19h] BYREF
  int v59[2]; // [rsp+C8h] [rbp-11h] BYREF
  _QWORD v60[2]; // [rsp+D0h] [rbp-9h] BYREF
  char v61; // [rsp+E0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v54 = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(this, a3, &v54);
  v9 = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDDC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointStore,
      v43);
    goto LABEL_82;
  }
  v10 = *((_QWORD *)this + 6);
  v11 = v54;
  (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION *, struct CEndpointStore *))(*(_QWORD *)v10 + 80LL))(
    v10,
    &lpCriticalSection,
    v54);
  v48 = 0;
  CustomResourceManagerService = CEndpointCharacteristics::TryGetCustomResourceManagerService(
                                   *a2,
                                   &GUID_475d74a7_6824_4b91_89be_33d893b255ed,
                                   &v48);
  v9 = CustomResourceManagerService;
  if ( CustomResourceManagerService < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)CustomResourceManagerService,
      v43);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    goto LABEL_82;
  }
  v13 = 0;
  v46 = 0;
  if ( v48 )
  {
    v14 = (*(__int64 (__fastcall **)(void *, LPCRITICAL_SECTION *))(*(_QWORD *)v48 + 104LL))(v48, &v55);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v46,
      v14);
    if ( v55 )
      LeaveCriticalSection(v55);
    v13 = v46;
  }
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v11 + 13) + 128LL))(*((_QWORD *)v11 + 13), &v50);
  CAudioStream::LockConnectDisconnectFromStreamGroup(((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0), &v46);
  if ( !*(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 0x30) )
    goto LABEL_73;
  v47 = 0;
  v16 = *((_QWORD *)v11 + 13);
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IStreamGroupProxy **))(*(_QWORD *)v16 + 40LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v47, v15);
  v19 = v17(v16, *(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 0x268), &v47);
  if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147023728 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDFC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v19,
      v43);
LABEL_14:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
    if ( v46 )
      LeaveCriticalSection(v46);
    if ( v50 )
      LeaveCriticalSection(v50);
    if ( v13 )
      LeaveCriticalSection(v13);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v9 = v19;
    goto LABEL_82;
  }
  v45 = 0;
  v20 = *(__int64 (__fastcall **)(struct IAudioStreamInfo *, struct IStreamGroupProxy **))(*(_QWORD *)a4 + 120LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v45, v18);
  v21 = v20(a4, &v45);
  v19 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDFF,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v21,
      v43);
LABEL_25:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
    goto LABEL_14;
  }
  if ( v47 )
  {
    v22 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v22 > 4u && (unsigned __int8)tlgKeywordOn(v22, 512) )
    {
      v55 = (LPCRITICAL_SECTION)a3;
      v58 = v45;
      *(_QWORD *)v59 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 80LL))(a4);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v22,
        (unsigned int)byte_1801A2469,
        v23,
        v24,
        (__int64)v59,
        (__int64)&v58,
        (__int64)&v55);
    }
    if ( v47 != v45 )
    {
      v25 = CAudioStream::ConnectToNewStreamGroup(
              (CAudioStream *)(((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)),
              v47);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0D,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v25,
          v43);
LABEL_33:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
        if ( v46 )
          LeaveCriticalSection(v46);
        if ( v50 )
          LeaveCriticalSection(v50);
        if ( v13 )
          LeaveCriticalSection(v13);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        v9 = v26;
        goto LABEL_82;
      }
    }
    goto LABEL_72;
  }
  if ( (*(__int64 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v45 + 432LL))(v45) != 1 )
    goto LABEL_47;
  v27 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  if ( *v27 > 4u && (unsigned __int8)tlgKeywordOn(v27, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v28,
      &dword_1801A2414);
  if ( (*(int (__fastcall **)(struct IStreamGroupProxy *, unsigned __int64))(*(_QWORD *)v45 + 448LL))(
         v45,
         (((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 576) < 0 )
  {
LABEL_47:
    v30 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v30 > 4u && (unsigned __int8)tlgKeywordOn(v30, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v31,
        &word_1801A23CE);
    v51 = 0;
    v32 = v45;
    v33 = *(__int64 (__fastcall **)(struct IStreamGroupProxy *, __int64 *))(*(_QWORD *)v45 + 224LL);
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v51, v29);
    v34 = v33(v32, &v51);
    v19 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE28,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v34,
        v43);
LABEL_52:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
      goto LABEL_25;
    }
    if ( !v51 )
    {
      v26 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE29,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)0x8000FFFFLL,
        v43);
LABEL_55:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
      goto LABEL_33;
    }
    v35 = *(_QWORD *)a4;
    v52 = 0;
    v19 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *, __int64 *))(v35 + 192))(a4, &v52);
    if ( v19 < 0 )
    {
      v36 = 3628;
LABEL_58:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v19,
        v43);
LABEL_59:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v52);
      goto LABEL_52;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, struct IAudioStreamInfo *, _QWORD))(*(_QWORD *)v52 + 72LL))(v52, a4, 0);
    if ( v19 < 0 )
    {
      v36 = 3630;
      goto LABEL_58;
    }
    v37 = (*(unsigned __int8 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v45 + 240LL))(v45) == 0;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v45, v38);
    v56 = 0;
    v57 = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v51 + 240LL))(v51, &v56);
    v19 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE34,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v39,
        v43);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v56);
      goto LABEL_59;
    }
    v53 = 0;
    v40 = *(__int64 (__fastcall **)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, _QWORD))(*(_QWORD *)g_DeviceGraphManager + 56LL);
    v60[0] = &v53;
    v60[1] = 0;
    v61 = 1;
    v44 = (*(__int64 (**)(void))(*(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 8) + 72LL))();
    v26 = v40(
            g_DeviceGraphManager,
            a2,
            *((_QWORD *)v11 + 13),
            *(_QWORD *)((((unsigned __int64)a4 - 8) & -(__int64)(a4 != 0)) + 0x268));
    wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(v60);
    if ( v26 < 0 )
    {
      v41 = 3645;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v26,
        v44);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v53);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v56);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v52);
      goto LABEL_55;
    }
    v44 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, __int64, BOOL, __int128 *))(*(_QWORD *)v53 + 208LL))(v53, v51, v37, &v56);
    if ( v26 < 0 )
    {
      v41 = 3647;
      goto LABEL_66;
    }
    v26 = (*(__int64 (__fastcall **)(__int64, struct IAudioStreamInfo *, __int64, __int64))(*(_QWORD *)v52 + 64LL))(
            v52,
            a4,
            v53,
            1);
    if ( v26 < 0 )
    {
      v41 = 3649;
      goto LABEL_66;
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v53);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v56);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v52);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
  }
LABEL_72:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
LABEL_73:
  if ( v46 )
    LeaveCriticalSection(v46);
  if ( v50 )
    LeaveCriticalSection(v50);
  if ( v13 )
    LeaveCriticalSection(v13);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v48);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  v9 = 0;
LABEL_82:
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v54);
  return v9;
}

```

## disassembly

```asm
0x1800e2d10  mov     [rsp-8+arg_8], rdx
0x1800e2d15  push    rbp
0x1800e2d16  push    rbx
0x1800e2d17  push    rsi
0x1800e2d18  push    rdi
0x1800e2d19  push    r12
0x1800e2d1b  push    r13
0x1800e2d1d  push    r14
0x1800e2d1f  push    r15
0x1800e2d21  lea     rbp, [rsp-1Fh]
0x1800e2d26  sub     rsp, 0F8h
0x1800e2d2d  mov     r15, r9
0x1800e2d30  mov     r12, r8
0x1800e2d33  mov     rsi, rdx
0x1800e2d36  mov     rdi, rcx
0x1800e2d39  xor     r14d, r14d
0x1800e2d3c  mov     [rbp+57h+var_98], r14
0x1800e2d40  lea     r8, [rbp+57h+var_98]; struct CEndpointStore **
0x1800e2d44  mov     rdx, r12; unsigned __int16 *
0x1800e2d47  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1800e2d4c  mov     ebx, eax
0x1800e2d4e  test    eax, eax
0x1800e2d50  jns     short loc_1800E2D6F
0x1800e2d52  mov     rcx, [rbp+5Fh]; this
0x1800e2d56  mov     r9d, eax; char *
0x1800e2d59  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e2d60  mov     edx, 0DDCh; void *
0x1800e2d65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2d6a  jmp     loc_1800E341A
0x1800e2d6f  mov     rcx, [rdi+30h]
0x1800e2d73  mov     rax, [rcx]
0x1800e2d76  mov     rdi, [rbp+57h+var_98]
0x1800e2d7a  mov     r8, rdi
0x1800e2d7d  lea     rdx, [rbp+57h+lpCriticalSection]
0x1800e2d81  mov     rax, [rax+50h]
0x1800e2d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2d8a  nop
0x1800e2d8b  mov     [rbp+57h+var_C8], r14
0x1800e2d8f  lea     r8, [rbp+57h+var_C8]; void **
0x1800e2d93  lea     rdx, _GUID_475d74a7_6824_4b91_89be_33d893b255ed; struct _GUID *
0x1800e2d9a  mov     rcx, [rsi]; this
0x1800e2d9d  call    ?TryGetCustomResourceManagerService@CEndpointCharacteristics@@QEAAJAEBU_GUID@@PEAPEAX@Z; CEndpointCharacteristics::TryGetCustomResourceManagerService(_GUID const &,void * *)
0x1800e2da2  mov     ebx, eax
0x1800e2da4  test    eax, eax
0x1800e2da6  jns     short loc_1800E2DE1
0x1800e2da8  mov     rcx, [rbp+5Fh]; this
0x1800e2dac  mov     r9d, eax; char *
0x1800e2daf  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e2db6  mov     edx, 0DE5h; void *
0x1800e2dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2dc0  lea     rcx, [rbp+57h+var_C8]
0x1800e2dc4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e2dc9  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800e2dcd  test    rcx, rcx
0x1800e2dd0  jz      loc_1800E341A
0x1800e2dd6  call    cs:__imp_LeaveCriticalSection
0x1800e2ddc  jmp     loc_1800E341A
0x1800e2de1  mov     rbx, r14
0x1800e2de4  mov     [rsp+130h+var_D8], rbx
0x1800e2de9  mov     rcx, [rbp+57h+var_C8]
0x1800e2ded  test    rcx, rcx
0x1800e2df0  jz      short loc_1800E2E23
0x1800e2df2  mov     rax, [rcx]
0x1800e2df5  lea     rdx, [rbp+57h+var_90]
0x1800e2df9  mov     rax, [rax+68h]
0x1800e2dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e02  mov     rdx, rax
0x1800e2e05  lea     rcx, [rsp+130h+var_D8]
0x1800e2e0a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x1800e2e0f  mov     rcx, [rbp+57h+var_90]; lpCriticalSection
0x1800e2e13  test    rcx, rcx
0x1800e2e16  jz      short loc_1800E2E1E
0x1800e2e18  call    cs:__imp_LeaveCriticalSection
0x1800e2e1e  mov     rbx, [rsp+130h+var_D8]
0x1800e2e23  mov     rcx, [rdi+68h]
0x1800e2e27  mov     rax, [rcx]
0x1800e2e2a  lea     rdx, [rbp+57h+var_B8]
0x1800e2e2e  mov     rax, [rax+80h]
0x1800e2e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e3a  mov     rax, r15
0x1800e2e3d  lea     rcx, [r15-8]
0x1800e2e41  neg     rax
0x1800e2e44  sbb     r13, r13
0x1800e2e47  and     r13, rcx
0x1800e2e4a  lea     rdx, [rsp+130h+var_D8]
0x1800e2e4f  mov     rcx, r13
0x1800e2e52  call    ?LockConnectDisconnectFromStreamGroup@CAudioStream@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CAudioStream::LockConnectDisconnectFromStreamGroup(void)
0x1800e2e57  cmp     [r13+30h], r14
0x1800e2e5b  jz      loc_1800E33D2
0x1800e2e61  mov     [rbp+57h+var_D0], r14
0x1800e2e65  mov     r14, [rdi+68h]
0x1800e2e69  mov     rax, [r14]
0x1800e2e6c  mov     rsi, [rax+28h]
0x1800e2e70  lea     rcx, [rbp+57h+var_D0]
0x1800e2e74  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800e2e79  lea     r8, [rbp+57h+var_D0]
0x1800e2e7d  mov     rdx, [r13+268h]
0x1800e2e84  mov     rcx, r14
0x1800e2e87  mov     rax, rsi
0x1800e2e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e8f  mov     esi, eax
0x1800e2e91  mov     eax, 80000000h
0x1800e2e96  lea     ecx, [rsi+rax]
0x1800e2e99  test    eax, ecx
0x1800e2e9b  jnz     short loc_1800E2F12
0x1800e2e9d  cmp     esi, 80070490h
0x1800e2ea3  jz      short loc_1800E2F12
0x1800e2ea5  mov     rcx, [rbp+5Fh]; this
0x1800e2ea9  mov     r9d, esi; char *
0x1800e2eac  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e2eb3  mov     edx, 0DFCh; void *
0x1800e2eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2ebd  lea     rcx, [rbp+57h+var_D0]
0x1800e2ec1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e2ec6  mov     rcx, [rsp+130h+var_D8]; lpCriticalSection
0x1800e2ecb  test    rcx, rcx
0x1800e2ece  jz      short loc_1800E2ED6
0x1800e2ed0  call    cs:__imp_LeaveCriticalSection
0x1800e2ed6  mov     rcx, [rbp+57h+var_B8]; lpCriticalSection
0x1800e2eda  test    rcx, rcx
0x1800e2edd  jz      short loc_1800E2EE5
0x1800e2edf  call    cs:__imp_LeaveCriticalSection
0x1800e2ee5  test    rbx, rbx
0x1800e2ee8  jz      short loc_1800E2EF3
0x1800e2eea  mov     rcx, rbx; lpCriticalSection
0x1800e2eed  call    cs:__imp_LeaveCriticalSection
0x1800e2ef3  lea     rcx, [rbp+57h+var_C8]
0x1800e2ef7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e2efc  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800e2f00  test    rcx, rcx
0x1800e2f03  jz      short loc_1800E2F0B
0x1800e2f05  call    cs:__imp_LeaveCriticalSection
0x1800e2f0b  mov     ebx, esi
0x1800e2f0d  jmp     loc_1800E341A
0x1800e2f12  xor     r14d, r14d
0x1800e2f15  mov     [rsp+130h+var_E0], r14
0x1800e2f1a  mov     rax, [r15]
0x1800e2f1d  mov     rsi, [rax+78h]
0x1800e2f21  lea     rcx, [rsp+130h+var_E0]
0x1800e2f26  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800e2f2b  lea     rdx, [rsp+130h+var_E0]
0x1800e2f30  mov     rcx, r15
0x1800e2f33  mov     rax, rsi
0x1800e2f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f3b  mov     esi, eax
0x1800e2f3d  test    eax, eax
0x1800e2f3f  jns     short loc_1800E2F68
0x1800e2f41  mov     rcx, [rbp+5Fh]; this
0x1800e2f45  mov     r9d, eax; char *
0x1800e2f48  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e2f4f  mov     edx, 0DFFh; void *
0x1800e2f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2f59  lea     rcx, [rsp+130h+var_E0]
0x1800e2f5e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e2f63  jmp     loc_1800E2EBD
0x1800e2f68  cmp     [rbp+57h+var_D0], r14
0x1800e2f6c  jz      loc_1800E3075
0x1800e2f72  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800e2f77  mov     rdi, [rax+8]
0x1800e2f7b  mov     eax, [rdi]
0x1800e2f7d  cmp     eax, 4
0x1800e2f80  jbe     short loc_1800E2FDD
0x1800e2f82  mov     edx, 200h
0x1800e2f87  mov     rcx, rdi
0x1800e2f8a  call    _tlgKeywordOn
0x1800e2f8f  test    al, al
0x1800e2f91  jz      short loc_1800E2FDD
0x1800e2f93  mov     [rbp+57h+var_90], r12
0x1800e2f97  mov     rax, [rsp+130h+var_E0]
0x1800e2f9c  mov     [rbp+57h+var_70], rax
0x1800e2fa0  mov     rax, [r15]
0x1800e2fa3  mov     rcx, r15
0x1800e2fa6  mov     rax, [rax+50h]
0x1800e2faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2faf  mov     qword ptr [rbp+57h+var_68], rax
0x1800e2fb3  lea     rax, [rbp+57h+var_90]
0x1800e2fb7  mov     [rsp+130h+var_100], rax
0x1800e2fbc  lea     rax, [rbp+57h+var_70]
0x1800e2fc0  mov     [rsp+130h+var_108], rax
0x1800e2fc5  lea     rax, [rbp+57h+var_68]
0x1800e2fc9  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800e2fce  lea     rdx, byte_1801A2469
0x1800e2fd5  mov     rcx, rdi
0x1800e2fd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800e2fdd  mov     rdx, [rbp+57h+var_D0]; struct IStreamGroupProxy *
0x1800e2fe1  cmp     rdx, [rsp+130h+var_E0]
0x1800e2fe6  jz      loc_1800E33BF
0x1800e2fec  mov     rcx, r13; this
0x1800e2fef  call    ?ConnectToNewStreamGroup@CAudioStream@@QEAAJPEAUIStreamGroupProxy@@@Z; CAudioStream::ConnectToNewStreamGroup(IStreamGroupProxy *)
0x1800e2ff4  mov     edi, eax
0x1800e2ff6  test    eax, eax
0x1800e2ff8  jns     loc_1800E33BF
0x1800e2ffe  mov     rcx, [rbp+5Fh]; this
0x1800e3002  mov     r9d, eax; char *
0x1800e3005  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e300c  mov     edx, 0E0Dh; void *
0x1800e3011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3016  lea     rcx, [rsp+130h+var_E0]
0x1800e301b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e3020  lea     rcx, [rbp+57h+var_D0]
0x1800e3024  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e3029  mov     rcx, [rsp+130h+var_D8]; lpCriticalSection
0x1800e302e  test    rcx, rcx
0x1800e3031  jz      short loc_1800E3039
0x1800e3033  call    cs:__imp_LeaveCriticalSection
0x1800e3039  mov     rcx, [rbp+57h+var_B8]; lpCriticalSection
0x1800e303d  test    rcx, rcx
0x1800e3040  jz      short loc_1800E3048
0x1800e3042  call    cs:__imp_LeaveCriticalSection
0x1800e3048  test    rbx, rbx
0x1800e304b  jz      short loc_1800E3056
0x1800e304d  mov     rcx, rbx; lpCriticalSection
0x1800e3050  call    cs:__imp_LeaveCriticalSection
0x1800e3056  lea     rcx, [rbp+57h+var_C8]
0x1800e305a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e305f  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800e3063  test    rcx, rcx
0x1800e3066  jz      short loc_1800E306E
0x1800e3068  call    cs:__imp_LeaveCriticalSection
0x1800e306e  mov     ebx, edi
0x1800e3070  jmp     loc_1800E341A
0x1800e3075  mov     rcx, [rsp+130h+var_E0]
0x1800e307a  mov     rax, [rcx]
0x1800e307d  mov     rax, [rax+1B0h]
0x1800e3084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3089  mov     esi, 200h
0x1800e308e  cmp     rax, 1
0x1800e3092  jnz     short loc_1800E30E5
0x1800e3094  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800e3099  mov     r8, [rax+8]
0x1800e309d  mov     eax, [r8]
0x1800e30a0  cmp     eax, 4
0x1800e30a3  jbe     short loc_1800E30C2
0x1800e30a5  mov     edx, esi
0x1800e30a7  mov     rcx, r8
0x1800e30aa  call    _tlgKeywordOn
0x1800e30af  test    al, al
0x1800e30b1  jz      short loc_1800E30C2
0x1800e30b3  lea     rdx, dword_1801A2414
0x1800e30ba  mov     rcx, r8
0x1800e30bd  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e30c2  mov     rcx, [rsp+130h+var_E0]
0x1800e30c7  mov     rax, [rcx]
0x1800e30ca  lea     rdx, [r13+240h]
0x1800e30d1  mov     rax, [rax+1C0h]
0x1800e30d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e30dd  test    eax, eax
0x1800e30df  jns     loc_1800E33BF
0x1800e30e5  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800e30ea  mov     r8, [rax+8]
0x1800e30ee  mov     eax, [r8]
0x1800e30f1  cmp     eax, 4
0x1800e30f4  jbe     short loc_1800E3114
0x1800e30f6  mov     rdx, rsi
0x1800e30f9  mov     rcx, r8
0x1800e30fc  call    _tlgKeywordOn
0x1800e3101  test    al, al
0x1800e3103  jz      short loc_1800E3114
0x1800e3105  lea     rdx, word_1801A23CE
0x1800e310c  mov     rcx, r8
0x1800e310f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e3114  mov     [rbp+57h+var_B0], r14
0x1800e3118  mov     r14, [rsp+130h+var_E0]
0x1800e311d  mov     rax, [r14]
0x1800e3120  mov     rsi, [rax+0E0h]
0x1800e3127  lea     rcx, [rbp+57h+var_B0]
0x1800e312b  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800e3130  lea     rdx, [rbp+57h+var_B0]
0x1800e3134  mov     rcx, r14
0x1800e3137  mov     rax, rsi
0x1800e313a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e313f  mov     esi, eax
0x1800e3141  xor     r14d, r14d
0x1800e3144  test    eax, eax
0x1800e3146  jns     short loc_1800E316E
0x1800e3148  mov     rcx, [rbp+5Fh]; this
0x1800e314c  mov     r9d, eax; char *
0x1800e314f  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e3156  mov     edx, 0E28h; void *
0x1800e315b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3160  lea     rcx, [rbp+57h+var_B0]
0x1800e3164  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e3169  jmp     loc_1800E2F59
0x1800e316e  cmp     [rbp+57h+var_B0], r14
0x1800e3172  jnz     short loc_1800E319F
0x1800e3174  mov     rcx, [rbp+5Fh]; this
0x1800e3178  mov     edi, 8000FFFFh
0x1800e317d  mov     r9d, edi; char *
0x1800e3180  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800e3187  mov     edx, 0E29h; void *
0x1800e318c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3191  lea     rcx, [rbp+57h+var_B0]
0x1800e3195  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e319a  jmp     loc_1800E3016
0x1800e319f  mov     rax, [r15]
0x1800e31a2  mov     [rbp+57h+var_A8], r14
0x1800e31a6  lea     rdx, [rbp+57h+var_A8]
0x1800e31aa  mov     rcx, r15
0x1800e31ad  mov     rax, [rax+0C0h]
0x1800e31b4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
