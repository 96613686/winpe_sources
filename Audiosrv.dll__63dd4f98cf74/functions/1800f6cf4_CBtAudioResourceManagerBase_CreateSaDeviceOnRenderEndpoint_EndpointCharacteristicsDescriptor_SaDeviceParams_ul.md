# CBtAudioResourceManagerBase::CreateSaDeviceOnRenderEndpoint(EndpointCharacteristicsDescriptor *,SaDeviceParams *,ulong,_AUDCLNT_SHAREMODE,SaDeviceResourceParams &,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>> const &,ISaDeviceProxy * *)

- ea: `0x1800f6cf4`
- end: `0x1800f75c0`
- name: `?CreateSaDeviceOnRenderEndpoint@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@PEAUSaDeviceParams@@KW4_AUDCLNT_SHAREMODE@@AEAUSaDeviceResourceParams@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUISaDeviceProxy@@@Z`
- size: `2252`
- prototype: `__int64 __usercall@<rax>(CBtAudioResourceManagerBase *this@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f8f10`

## callees

- `0x18000313c`
- `0x18001280c`
- `0x180019998`
- `0x18001b520`
- `0x18001d8d8`
- `0x1800318d8`
- `0x180031c80`
- `0x18004f2fc`
- `0x180071250`
- `0x180072e10`
- `0x1800b35e8`
- `0x1800ba92c`
- `0x1800c3c70`
- `0x1800cb9dc`
- `0x1800cbd9c`
- `0x1800f6cf4`
- `0x1800f75c8`
- `0x1800f7800`
- `0x1800f9434`
- `0x1800fa90c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f700b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f708d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f70a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7109`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7123`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f719d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7249`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7263`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f72be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f72d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f734c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f73d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f73f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f748b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f74a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7577`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7591`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f700b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f708d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f70a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7109`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7123`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f719d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7249`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7263`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f72be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f72d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f734c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f73d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f73f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f748b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f74a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7577`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7591`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800f6d34`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800f6d34`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f74d0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f74d0`

## string_xrefs

- `0x1800f6d7b`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6e17`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6f05`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6f64`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f7063`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f70ed`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f715e`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f7219`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f728e`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f7330`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f7461`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBtAudioResourceManagerBase::CreateSaDeviceOnRenderEndpoint(
        CBtAudioResourceManagerBase *this,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        struct ISaDeviceProxy **a8)
{
  bool v11; // r14
  char v12; // r15
  CEndpointStoreCache *v13; // rcx
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  const unsigned __int16 *v15; // rdx
  int EndpointStore; // eax
  unsigned int v17; // ebx
  const char *v18; // r9
  __int64 result; // rax
  struct CEndpointStore *v20; // rbx
  __int64 v21; // rax
  CBtAudioResourceManagerBase *v22; // rcx
  int v23; // eax
  unsigned int v24; // edi
  struct CEndpointStore *v25; // rdi
  __int64 (__fastcall *v26)(CBtAudioResourceManagerBase *, __int128 *); // rax
  char v27; // al
  CBtAudioResourceManagerBase *v28; // rcx
  int SaDeviceWrapper; // eax
  unsigned int v30; // edi
  int SecondaryProfileRenderSaDeviceWithDefaultParameters; // eax
  unsigned int v32; // edi
  int v33; // eax
  unsigned int v34; // edi
  int v35; // eax
  unsigned int v36; // edi
  int v37; // eax
  unsigned int v38; // edi
  int v39; // eax
  unsigned int v40; // edi
  _DWORD *v41; // r8
  int v42; // r8d
  int v43; // r9d
  int v44; // [rsp+20h] [rbp-A8h]
  int v45; // [rsp+20h] [rbp-A8h]
  int v46; // [rsp+20h] [rbp-A8h]
  int v47; // [rsp+20h] [rbp-A8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-78h] BYREF
  LPCRITICAL_SECTION v49; // [rsp+58h] [rbp-70h] BYREF
  struct CEndpointStore *v50; // [rsp+60h] [rbp-68h] BYREF
  struct _RTL_CRITICAL_SECTION *v51; // [rsp+68h] [rbp-60h] BYREF
  __int128 v52; // [rsp+70h] [rbp-58h] BYREF
  __int64 v53; // [rsp+80h] [rbp-48h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-40h] BYREF
  LARGE_INTEGER v55[2]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  struct ISaDeviceProxy *v57; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v58; // [rsp+D8h] [rbp+10h]

  v58 = a2;
  v11 = 0;
  v12 = 0;
  LOBYTE(v57) = 0;
  PerformanceCount.QuadPart = 0;
  v53 = 0;
  QueryPerformanceFrequency(v55);
  CQPCStopWatch::Start((CQPCStopWatch *)&v53);
  try
  {
    v14 = 0;
    v51 = 0;
    v15 = (const unsigned __int16 *)*((_QWORD *)this + 8);
    if ( v15 )
    {
      v50 = 0;
      EndpointStore = CEndpointStoreCache::GetEndpointStore(v13, v15, &v50);
      v17 = EndpointStore;
      if ( EndpointStore < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x361,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)(unsigned int)EndpointStore,
          v44);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v50);
        return v17;
      }
      v20 = v50;
      v21 = (*(__int64 (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v50 + 13) + 128LL))(
              *((_QWORD *)v50 + 13),
              &lpCriticalSection);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
        &v51,
        v21);
      v22 = (CBtAudioResourceManagerBase *)lpCriticalSection;
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      v11 = CBtAudioResourceManagerBase::DoMicrophoneSaDevicesExist(v22, v20);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v50);
      v14 = v51;
    }
    lpCriticalSection = 0;
    v23 = CEndpointStoreCache::GetEndpointStore(
            v13,
            *((const unsigned __int16 **)this + 7),
            (struct CEndpointStore **)&lpCriticalSection);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
        (const char *)(unsigned int)v23,
        v44);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
      if ( v14 )
        LeaveCriticalSection(v14);
      return v24;
    }
    v25 = (struct CEndpointStore *)lpCriticalSection;
    (*(void (__fastcall **)(HANDLE, LPCRITICAL_SECTION *))(*(_QWORD *)lpCriticalSection[2].LockSemaphore + 128LL))(
      lpCriticalSection[2].LockSemaphore,
      &v49);
    v26 = *(__int64 (__fastcall **)(CBtAudioResourceManagerBase *, __int128 *))(*(_QWORD *)this + 152LL);
    v52 = *(_OWORD *)(a3 + 48);
    v27 = v26(this, &v52);
    if ( v11 )
    {
      if ( v27 )
      {
        SaDeviceWrapper = CBtAudioResourceManagerBase::GetSaDeviceWrapper(
                            (_DWORD)this,
                            v58,
                            a3,
                            a4,
                            a5,
                            a6,
                            a7,
                            0,
                            0,
                            (__int64)a8);
        v30 = SaDeviceWrapper;
        if ( SaDeviceWrapper < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x375,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
            (const char *)(unsigned int)SaDeviceWrapper,
            v45);
          if ( v49 )
            LeaveCriticalSection(v49);
          wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
          if ( v14 )
            LeaveCriticalSection(v14);
          return v30;
        }
        goto LABEL_88;
      }
      if ( CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(v28, v25) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37E,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)0x887C007ALL,
          v44);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return 2289827962LL;
      }
      v57 = 0;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
      if ( CBtAudioResourceManagerBase::DoSecondaryProfileSharedModeRenderSaDevicesExist(this, v25, &v57) )
      {
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v57);
        *a8 = v57;
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return 0;
      }
      SecondaryProfileRenderSaDeviceWithDefaultParameters = CBtAudioResourceManagerBase::CreateSecondaryProfileRenderSaDeviceWithDefaultParameters(this);
      v32 = SecondaryProfileRenderSaDeviceWithDefaultParameters;
      if ( SecondaryProfileRenderSaDeviceWithDefaultParameters < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38A,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)(unsigned int)SecondaryProfileRenderSaDeviceWithDefaultParameters,
          v44);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return v32;
      }
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
LABEL_88:
      if ( v49 )
        LeaveCriticalSection(v49);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
      if ( v14 )
        LeaveCriticalSection(v14);
      return 0;
    }
    if ( v27 )
    {
      if ( CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(v28, v25) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x396,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)0x887C005CLL,
          v44);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return 2289827932LL;
      }
      *(_QWORD *)&v52 = this;
      BYTE8(v52) = 1;
      v33 = CBtAudioResourceManagerBase::FreePrimaryProfileRenderSaDevicesAndSaveDisplacedStreamGroups(
              this,
              v25,
              (bool *)&v57);
      v34 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39F,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)(unsigned int)v33,
          v44);
        CBtAudioResourceManagerBase::RestoreDisplacedPrimaryProfileStreamGroups(this);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return v34;
      }
      v50 = 0;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v50);
      v35 = CBtAudioResourceManagerBase::GetSaDeviceWrapper((_DWORD)this, v58, a3, a4, a5, a6, a7, 0, 0, (__int64)&v50);
      v36 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A3,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)(unsigned int)v35,
          v46);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v50);
        CBtAudioResourceManagerBase::RestoreDisplacedPrimaryProfileStreamGroups(this);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return v36;
      }
      v37 = CBtAudioResourceManagerBase::MoveDisplacedPrimaryProfileStreamGroupsToSaDevice(this, v50);
      v38 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A6,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)(unsigned int)v37,
          v46);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v50);
        CBtAudioResourceManagerBase::RestoreDisplacedPrimaryProfileStreamGroups(this);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        return v38;
      }
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v50);
      *a8 = v50;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v50);
      v12 = (char)v57;
LABEL_84:
      if ( v12 )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v41 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *v41 > 4u )
        {
          if ( (unsigned __int8)tlgKeywordOn(v41, 0x400000004000LL) )
          {
            v57 = COERCE_STRUCT_ISADEVICEPROXY_(CQPCStopWatch::GetTimeSec((CQPCStopWatch *)&v53));
            v51 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 8);
            v50 = (struct CEndpointStore *)*((_QWORD *)this + 7);
            *(_QWORD *)&v52 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
              v42,
              (unsigned int)&dword_1801A46F4,
              v42,
              v43,
              (__int64)&v52,
              (__int64)&v50,
              (__int64)&v51,
              (__int64)&v57);
          }
        }
      }
      goto LABEL_88;
    }
    if ( CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(v28, v25) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B2,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
        (const char *)0x887C005CLL,
        v44);
      if ( v49 )
        LeaveCriticalSection(v49);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
      if ( v14 )
        LeaveCriticalSection(v14);
      result = 2289827932LL;
    }
    else
    {
      v57 = 0;
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
      if ( CBtAudioResourceManagerBase::DoSecondaryProfileSharedModeRenderSaDevicesExist(this, v25, &v57) )
      {
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v57);
        *a8 = v57;
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        result = 0;
      }
      else
      {
        v39 = CBtAudioResourceManagerBase::GetSaDeviceWrapper((_DWORD)this, v58, a3, a4, a5, a6, a7, 0, 0, (__int64)a8);
        v40 = v39;
        if ( v39 >= 0 )
        {
          Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
          goto LABEL_84;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3BF,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
          (const char *)(unsigned int)v39,
          v47);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v57);
        if ( v49 )
          LeaveCriticalSection(v49);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&lpCriticalSection);
        if ( v14 )
          LeaveCriticalSection(v14);
        result = v40;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v57) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x3D3,
                     (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btaudioresourcemanagerbase.cpp",
                     v18);
    return (unsigned int)v57;
  }
  return result;
}

```

## disassembly

```asm
0x1800f6cf4  mov     rax, rsp
0x1800f6cf7  mov     [rax+18h], rbx
0x1800f6cfb  mov     [rax+20h], rsi
0x1800f6cff  mov     [rax+10h], rdx
0x1800f6d03  push    rdi
0x1800f6d04  push    r12
0x1800f6d06  push    r13
0x1800f6d08  push    r14
0x1800f6d0a  push    r15
0x1800f6d0c  sub     rsp, 0A0h
0x1800f6d13  mov     r13d, r9d
0x1800f6d16  mov     r12, r8
0x1800f6d19  mov     rsi, rcx
0x1800f6d1c  xor     edi, edi
0x1800f6d1e  mov     r14b, dil
0x1800f6d21  mov     r15b, dil
0x1800f6d24  mov     [rax+8], dil
0x1800f6d28  mov     [rax-40h], rdi
0x1800f6d2c  mov     [rax-48h], rdi
0x1800f6d30  lea     rcx, [rax-38h]; lpFrequency
0x1800f6d34  call    cs:__imp_QueryPerformanceFrequency
0x1800f6d3a  lea     rcx, [rsp+0C8h+var_48]; this
0x1800f6d42  call    ?Start@CQPCStopWatch@@QEAAHXZ; CQPCStopWatch::Start(void)
0x1800f6d47  mov     ebx, edi
0x1800f6d49  mov     [rsp+0C8h+var_60], rbx
0x1800f6d4e  mov     rdx, [rsi+40h]; unsigned __int16 *
0x1800f6d52  test    rdx, rdx
0x1800f6d55  jz      loc_1800F6DF3
0x1800f6d5b  mov     [rsp+0C8h+var_68], rdi
0x1800f6d60  lea     r8, [rsp+0C8h+var_68]; struct CEndpointStore **
0x1800f6d65  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1800f6d6a  mov     ebx, eax
0x1800f6d6c  test    eax, eax
0x1800f6d6e  jns     short loc_1800F6D9F
0x1800f6d70  mov     rcx, [rsp+0C8h]; this
0x1800f6d78  mov     r9d, eax; char *
0x1800f6d7b  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6d82  mov     edx, 361h; void *
0x1800f6d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6d8c  nop
0x1800f6d8d  lea     rcx, [rsp+0C8h+var_68]
0x1800f6d92  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6d97  nop
0x1800f6d98  mov     eax, ebx
0x1800f6d9a  jmp     loc_1800F75A2
0x1800f6d9f  mov     rbx, [rsp+0C8h+var_68]
0x1800f6da4  mov     rcx, [rbx+68h]
0x1800f6da8  mov     rax, [rcx]
0x1800f6dab  lea     rdx, [rsp+0C8h+lpCriticalSection]
0x1800f6db0  mov     rax, [rax+80h]
0x1800f6db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6dbc  mov     rdx, rax
0x1800f6dbf  lea     rcx, [rsp+0C8h+var_60]
0x1800f6dc4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x1800f6dc9  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x1800f6dce  test    rcx, rcx
0x1800f6dd1  jz      short loc_1800F6DD9
0x1800f6dd3  call    cs:__imp_LeaveCriticalSection
0x1800f6dd9  mov     rdx, rbx; struct CEndpointStore *
0x1800f6ddc  call    ?DoMicrophoneSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@@Z; CBtAudioResourceManagerBase::DoMicrophoneSaDevicesExist(CEndpointStore *)
0x1800f6de1  mov     r14b, al
0x1800f6de4  lea     rcx, [rsp+0C8h+var_68]
0x1800f6de9  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6dee  mov     rbx, [rsp+0C8h+var_60]
0x1800f6df3  mov     [rsp+0C8h+lpCriticalSection], rdi
0x1800f6df8  lea     r8, [rsp+0C8h+lpCriticalSection]; struct CEndpointStore **
0x1800f6dfd  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1800f6e01  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1800f6e06  mov     edi, eax
0x1800f6e08  test    eax, eax
0x1800f6e0a  jns     short loc_1800F6E49
0x1800f6e0c  mov     rcx, [rsp+0C8h]; this
0x1800f6e14  mov     r9d, eax; char *
0x1800f6e17  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6e1e  mov     edx, 36Ah; void *
0x1800f6e23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6e28  nop
0x1800f6e29  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6e2e  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6e33  nop
0x1800f6e34  test    rbx, rbx
0x1800f6e37  jz      short loc_1800F6E42
0x1800f6e39  mov     rcx, rbx; lpCriticalSection
0x1800f6e3c  call    cs:__imp_LeaveCriticalSection
0x1800f6e42  mov     eax, edi
0x1800f6e44  jmp     loc_1800F75A2
0x1800f6e49  mov     rdi, [rsp+0C8h+lpCriticalSection]
0x1800f6e4e  mov     rcx, [rdi+68h]
0x1800f6e52  mov     rax, [rcx]
0x1800f6e55  lea     rdx, [rsp+0C8h+var_70]
0x1800f6e5a  mov     rax, [rax+80h]
0x1800f6e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6e66  nop
0x1800f6e67  mov     rax, [rsi]
0x1800f6e6a  mov     rax, [rax+98h]
0x1800f6e71  movups  xmm0, xmmword ptr [r12+30h]
0x1800f6e77  lea     rdx, [rsp+0C8h+var_58]
0x1800f6e7c  mov     rcx, rsi
0x1800f6e7f  movdqu  [rsp+0C8h+var_58], xmm0
0x1800f6e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6e8a  test    r14b, r14b
0x1800f6e8d  jz      loc_1800F70C6
0x1800f6e93  xor     r14d, r14d
0x1800f6e96  test    al, al
0x1800f6e98  jz      loc_1800F6F48
0x1800f6e9e  mov     rax, [rsp+0C8h+arg_38]
0x1800f6ea6  mov     [rsp+0C8h+var_80], rax
0x1800f6eab  mov     [rsp+0C8h+var_88], r14
0x1800f6eb0  mov     [rsp+0C8h+var_90], r14
0x1800f6eb5  mov     rax, [rsp+0C8h+arg_30]
0x1800f6ebd  mov     [rsp+0C8h+var_98], rax
0x1800f6ec2  mov     rax, [rsp+0C8h+arg_28]
0x1800f6eca  mov     [rsp+0C8h+var_A0], rax
0x1800f6ecf  mov     eax, [rsp+0C8h+arg_20]
0x1800f6ed6  mov     [rsp+0C8h+var_A8], eax; int
0x1800f6eda  mov     r9d, r13d
0x1800f6edd  mov     r8, r12
0x1800f6ee0  mov     rdx, [rsp+0C8h+arg_8]
0x1800f6ee8  mov     rcx, rsi
0x1800f6eeb  call    ?GetSaDeviceWrapper@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@PEAUSaDeviceParams@@KW4_AUDCLNT_SHAREMODE@@AEAUSaDeviceResourceParams@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEBU_GUID@@5PEAPEAUISaDeviceProxy@@@Z; CBtAudioResourceManagerBase::GetSaDeviceWrapper(EndpointCharacteristicsDescriptor *,SaDeviceParams *,ulong,_AUDCLNT_SHAREMODE,SaDeviceResourceParams &,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &,_GUID const *,_GUID const *,ISaDeviceProxy * *)
0x1800f6ef0  mov     edi, eax
0x1800f6ef2  test    eax, eax
0x1800f6ef4  jns     loc_1800F756D
0x1800f6efa  mov     rcx, [rsp+0C8h]; this
0x1800f6f02  mov     r9d, eax; char *
0x1800f6f05  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6f0c  mov     edx, 375h; void *
0x1800f6f11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6f16  nop
0x1800f6f17  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6f1c  test    rcx, rcx
0x1800f6f1f  jz      short loc_1800F6F28
0x1800f6f21  call    cs:__imp_LeaveCriticalSection
0x1800f6f27  nop
0x1800f6f28  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6f2d  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6f32  nop
0x1800f6f33  test    rbx, rbx
0x1800f6f36  jz      short loc_1800F6F41
0x1800f6f38  mov     rcx, rbx; lpCriticalSection
0x1800f6f3b  call    cs:__imp_LeaveCriticalSection
0x1800f6f41  mov     eax, edi
0x1800f6f43  jmp     loc_1800F75A2
0x1800f6f48  mov     rdx, rdi; struct CEndpointStore *
0x1800f6f4b  call    ?DoExclusiveModeSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@@Z; CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(CEndpointStore *)
0x1800f6f50  test    al, al
0x1800f6f52  jz      short loc_1800F6FA7
0x1800f6f54  mov     rcx, [rsp+0C8h]; this
0x1800f6f5c  mov     edi, 887C007Ah
0x1800f6f61  mov     r9d, edi; char *
0x1800f6f64  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6f6b  mov     edx, 37Eh; void *
0x1800f6f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6f75  nop
0x1800f6f76  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6f7b  test    rcx, rcx
0x1800f6f7e  jz      short loc_1800F6F87
0x1800f6f80  call    cs:__imp_LeaveCriticalSection
0x1800f6f86  nop
0x1800f6f87  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6f8c  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6f91  nop
0x1800f6f92  test    rbx, rbx
0x1800f6f95  jz      short loc_1800F6FA0
0x1800f6f97  mov     rcx, rbx; lpCriticalSection
0x1800f6f9a  call    cs:__imp_LeaveCriticalSection
0x1800f6fa0  mov     eax, edi
0x1800f6fa2  jmp     loc_1800F75A2
0x1800f6fa7  mov     [rsp+0C8h+arg_0], r14
0x1800f6faf  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6fb7  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f6fbc  lea     r8, [rsp+0C8h+arg_0]; struct ISaDeviceProxy **
0x1800f6fc4  mov     rdx, rdi; struct CEndpointStore *
0x1800f6fc7  mov     rcx, rsi; this
0x1800f6fca  call    ?DoSecondaryProfileSharedModeRenderSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@PEAPEAUISaDeviceProxy@@@Z; CBtAudioResourceManagerBase::DoSecondaryProfileSharedModeRenderSaDevicesExist(CEndpointStore *,ISaDeviceProxy * *)
0x1800f6fcf  test    al, al
0x1800f6fd1  jz      short loc_1800F7032
0x1800f6fd3  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6fdb  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800f6fe0  mov     rcx, [rsp+0C8h+arg_38]
0x1800f6fe8  mov     rax, [rsp+0C8h+arg_0]
0x1800f6ff0  mov     [rcx], rax
0x1800f6ff3  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6ffb  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f7000  nop
0x1800f7001  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f7006  test    rcx, rcx
0x1800f7009  jz      short loc_1800F7012
0x1800f700b  call    cs:__imp_LeaveCriticalSection
0x1800f7011  nop
0x1800f7012  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f7017  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f701c  nop
0x1800f701d  test    rbx, rbx
0x1800f7020  jz      short loc_1800F702B
0x1800f7022  mov     rcx, rbx; lpCriticalSection
0x1800f7025  call    cs:__imp_LeaveCriticalSection
0x1800f702b  xor     eax, eax
0x1800f702d  jmp     loc_1800F75A2
0x1800f7032  mov     r9, [rsp+0C8h+arg_38]
0x1800f703a  mov     r8, [rsp+0C8h+arg_30]
0x1800f7042  mov     rdx, [rsp+0C8h+arg_28]
0x1800f704a  mov     rcx, rsi; this
0x1800f704d  call    ?CreateSecondaryProfileRenderSaDeviceWithDefaultParameters@CBtAudioResourceManagerBase@@IEAAJAEAUSaDeviceResourceParams@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUISaDeviceProxy@@@Z; CBtAudioResourceManagerBase::CreateSecondaryProfileRenderSaDeviceWithDefaultParameters(SaDeviceResourceParams &,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &,ISaDeviceProxy * *)
0x1800f7052  mov     edi, eax
0x1800f7054  test    eax, eax
0x1800f7056  jns     short loc_1800F70B4
0x1800f7058  mov     rcx, [rsp+0C8h]; this
0x1800f7060  mov     r9d, eax; char *
0x1800f7063  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f706a  mov     edx, 38Ah; void *
0x1800f706f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7074  nop
0x1800f7075  lea     rcx, [rsp+0C8h+arg_0]
0x1800f707d  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f7082  nop
0x1800f7083  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f7088  test    rcx, rcx
0x1800f708b  jz      short loc_1800F7094
0x1800f708d  call    cs:__imp_LeaveCriticalSection
0x1800f7093  nop
0x1800f7094  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f7099  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f709e  nop
0x1800f709f  test    rbx, rbx
0x1800f70a2  jz      short loc_1800F70AD
0x1800f70a4  mov     rcx, rbx; lpCriticalSection
0x1800f70a7  call    cs:__imp_LeaveCriticalSection
0x1800f70ad  mov     eax, edi
0x1800f70af  jmp     loc_1800F75A2
0x1800f70b4  lea     rcx, [rsp+0C8h+arg_0]
0x1800f70bc  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f70c1  jmp     loc_1800F756D
0x1800f70c6  xor     r14d, r14d
0x1800f70c9  mov     rdx, rdi; struct CEndpointStore *
0x1800f70cc  test    al, al
0x1800f70ce  jz      loc_1800F7317
0x1800f70d4  call    ?DoExclusiveModeSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@@Z; CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(CEndpointStore *)
0x1800f70d9  test    al, al
0x1800f70db  jz      short loc_1800F7130
0x1800f70dd  mov     rcx, [rsp+0C8h]; this
0x1800f70e5  mov     edi, 887C005Ch
0x1800f70ea  mov     r9d, edi; char *
0x1800f70ed  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f70f4  mov     edx, 396h; void *
0x1800f70f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f70fe  nop
0x1800f70ff  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f7104  test    rcx, rcx
0x1800f7107  jz      short loc_1800F7110
0x1800f7109  call    cs:__imp_LeaveCriticalSection
0x1800f710f  nop
0x1800f7110  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f7115  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f711a  nop
0x1800f711b  test    rbx, rbx
0x1800f711e  jz      short loc_1800F7129
0x1800f7120  mov     rcx, rbx; lpCriticalSection
0x1800f7123  call    cs:__imp_LeaveCriticalSection
0x1800f7129  mov     eax, edi
0x1800f712b  jmp     loc_1800F75A2
0x1800f7130  mov     qword ptr [rsp+0C8h+var_58], rsi
0x1800f7135  mov     byte ptr [rsp+0C8h+var_58+8], 1
0x1800f713a  lea     r8, [rsp+0C8h+arg_0]; bool *
0x1800f7142  mov     rdx, rdi; struct CEndpointStore *
0x1800f7145  mov     rcx, rsi; this
0x1800f7148  call    ?FreePrimaryProfileRenderSaDevicesAndSaveDisplacedStreamGroups@CBtAudioResourceManagerBase@@IEAAJPEAVCEndpointStore@@PEA_N@Z; CBtAudioResourceManagerBase::FreePrimaryProfileRenderSaDevicesAndSaveDisplacedStreamGroups(CEndpointStore *,bool *)
0x1800f714d  mov     edi, eax
0x1800f714f  test    eax, eax
0x1800f7151  jns     short loc_1800F71AA
0x1800f7153  mov     rcx, [rsp+0C8h]; this
0x1800f715b  mov     r9d, eax; char *
0x1800f715e  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f7165  mov     edx, 39Fh; void *
0x1800f716a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f716f  nop
0x1800f7170  mov     rcx, rsi; this
0x1800f7173  call    ?RestoreDisplacedPrimaryProfileStreamGroups@CBtAudioResourceManagerBase@@IEAAJXZ; CBtAudioResourceManagerBase::RestoreDisplacedPrimaryProfileStreamGroups(void)
0x1800f7178  nop
0x1800f7179  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f717e  test    rcx, rcx
0x1800f7181  jz      short loc_1800F718A
0x1800f7183  call    cs:__imp_LeaveCriticalSection
0x1800f7189  nop
0x1800f718a  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f718f  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f7194  nop
0x1800f7195  test    rbx, rbx
0x1800f7198  jz      short loc_1800F71A3
0x1800f719a  mov     rcx, rbx; lpCriticalSection
0x1800f719d  call    cs:__imp_LeaveCriticalSection
0x1800f71a3  mov     eax, edi
0x1800f71a5  jmp     loc_1800F75A2
0x1800f71aa  mov     [rsp+0C8h+var_68], r14
0x1800f71af  lea     rcx, [rsp+0C8h+var_68]
0x1800f71b4  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f71b9  lea     rax, [rsp+0C8h+var_68]
0x1800f71be  mov     [rsp+0C8h+var_80], rax
0x1800f71c3  mov     [rsp+0C8h+var_88], r14
0x1800f71c8  mov     [rsp+0C8h+var_90], r14
  ... truncated ...
```
