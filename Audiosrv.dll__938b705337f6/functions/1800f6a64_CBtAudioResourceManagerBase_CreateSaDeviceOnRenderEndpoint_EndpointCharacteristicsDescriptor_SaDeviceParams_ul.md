# CBtAudioResourceManagerBase::CreateSaDeviceOnRenderEndpoint(EndpointCharacteristicsDescriptor *,SaDeviceParams *,ulong,_AUDCLNT_SHAREMODE,SaDeviceResourceParams &,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>> const &,ISaDeviceProxy * *)

- ea: `0x1800f6a64`
- end: `0x1800f7330`
- name: `?CreateSaDeviceOnRenderEndpoint@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@PEAUSaDeviceParams@@KW4_AUDCLNT_SHAREMODE@@AEAUSaDeviceResourceParams@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUISaDeviceProxy@@@Z`
- size: `2252`
- prototype: `__int64 __usercall@<rax>(CBtAudioResourceManagerBase *this@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f8c80`

## callees

- `0x180002f30`
- `0x1800126bc`
- `0x180019848`
- `0x18001b3d0`
- `0x18001d788`
- `0x180031778`
- `0x180031b20`
- `0x18004f78c`
- `0x180071750`
- `0x180073310`
- `0x1800b52d8`
- `0x1800bc47c`
- `0x1800c5b00`
- `0x1800cd9cc`
- `0x1800cdd8c`
- `0x1800f6a64`
- `0x1800f7338`
- `0x1800f7570`
- `0x1800f91a4`
- `0x1800fa67c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6bac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6c91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6cf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6dfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6ef3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6fb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6fd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f702e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f70bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f70d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7147`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f71fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7215`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f72e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7301`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6bac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6c91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6cf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6dfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6ef3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6f0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6fb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6fd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f702e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f70bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f70d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7147`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f71fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7215`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f72e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7301`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800f6aa4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800f6aa4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f7240`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f7240`

## string_xrefs

- `0x1800f6aeb`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6b87`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6c75`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6cd4`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6dd3`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6e5d`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6ece`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6f89`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f6ffe`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f70a0`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`
- `0x1800f71d1`: `avcore\audiocore\server\audiosrv\dll\btaudioresourcemanagerbase.cpp`

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
              (unsigned int)&unk_1801A34B1,
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
0x1800f6a64  mov     rax, rsp
0x1800f6a67  mov     [rax+18h], rbx
0x1800f6a6b  mov     [rax+20h], rsi
0x1800f6a6f  mov     [rax+10h], rdx
0x1800f6a73  push    rdi
0x1800f6a74  push    r12
0x1800f6a76  push    r13
0x1800f6a78  push    r14
0x1800f6a7a  push    r15
0x1800f6a7c  sub     rsp, 0A0h
0x1800f6a83  mov     r13d, r9d
0x1800f6a86  mov     r12, r8
0x1800f6a89  mov     rsi, rcx
0x1800f6a8c  xor     edi, edi
0x1800f6a8e  mov     r14b, dil
0x1800f6a91  mov     r15b, dil
0x1800f6a94  mov     [rax+8], dil
0x1800f6a98  mov     [rax-40h], rdi
0x1800f6a9c  mov     [rax-48h], rdi
0x1800f6aa0  lea     rcx, [rax-38h]; lpFrequency
0x1800f6aa4  call    cs:__imp_QueryPerformanceFrequency
0x1800f6aaa  lea     rcx, [rsp+0C8h+var_48]; this
0x1800f6ab2  call    ?Start@CQPCStopWatch@@QEAAHXZ; CQPCStopWatch::Start(void)
0x1800f6ab7  mov     ebx, edi
0x1800f6ab9  mov     [rsp+0C8h+var_60], rbx
0x1800f6abe  mov     rdx, [rsi+40h]; unsigned __int16 *
0x1800f6ac2  test    rdx, rdx
0x1800f6ac5  jz      loc_1800F6B63
0x1800f6acb  mov     [rsp+0C8h+var_68], rdi
0x1800f6ad0  lea     r8, [rsp+0C8h+var_68]; struct CEndpointStore **
0x1800f6ad5  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1800f6ada  mov     ebx, eax
0x1800f6adc  test    eax, eax
0x1800f6ade  jns     short loc_1800F6B0F
0x1800f6ae0  mov     rcx, [rsp+0C8h]; this
0x1800f6ae8  mov     r9d, eax; char *
0x1800f6aeb  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6af2  mov     edx, 361h; void *
0x1800f6af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6afc  nop
0x1800f6afd  lea     rcx, [rsp+0C8h+var_68]
0x1800f6b02  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6b07  nop
0x1800f6b08  mov     eax, ebx
0x1800f6b0a  jmp     loc_1800F7312
0x1800f6b0f  mov     rbx, [rsp+0C8h+var_68]
0x1800f6b14  mov     rcx, [rbx+68h]
0x1800f6b18  mov     rax, [rcx]
0x1800f6b1b  lea     rdx, [rsp+0C8h+lpCriticalSection]
0x1800f6b20  mov     rax, [rax+80h]
0x1800f6b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b2c  mov     rdx, rax
0x1800f6b2f  lea     rcx, [rsp+0C8h+var_60]
0x1800f6b34  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x1800f6b39  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x1800f6b3e  test    rcx, rcx
0x1800f6b41  jz      short loc_1800F6B49
0x1800f6b43  call    cs:__imp_LeaveCriticalSection
0x1800f6b49  mov     rdx, rbx; struct CEndpointStore *
0x1800f6b4c  call    ?DoMicrophoneSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@@Z; CBtAudioResourceManagerBase::DoMicrophoneSaDevicesExist(CEndpointStore *)
0x1800f6b51  mov     r14b, al
0x1800f6b54  lea     rcx, [rsp+0C8h+var_68]
0x1800f6b59  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6b5e  mov     rbx, [rsp+0C8h+var_60]
0x1800f6b63  mov     [rsp+0C8h+lpCriticalSection], rdi
0x1800f6b68  lea     r8, [rsp+0C8h+lpCriticalSection]; struct CEndpointStore **
0x1800f6b6d  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1800f6b71  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1800f6b76  mov     edi, eax
0x1800f6b78  test    eax, eax
0x1800f6b7a  jns     short loc_1800F6BB9
0x1800f6b7c  mov     rcx, [rsp+0C8h]; this
0x1800f6b84  mov     r9d, eax; char *
0x1800f6b87  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6b8e  mov     edx, 36Ah; void *
0x1800f6b93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6b98  nop
0x1800f6b99  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6b9e  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6ba3  nop
0x1800f6ba4  test    rbx, rbx
0x1800f6ba7  jz      short loc_1800F6BB2
0x1800f6ba9  mov     rcx, rbx; lpCriticalSection
0x1800f6bac  call    cs:__imp_LeaveCriticalSection
0x1800f6bb2  mov     eax, edi
0x1800f6bb4  jmp     loc_1800F7312
0x1800f6bb9  mov     rdi, [rsp+0C8h+lpCriticalSection]
0x1800f6bbe  mov     rcx, [rdi+68h]
0x1800f6bc2  mov     rax, [rcx]
0x1800f6bc5  lea     rdx, [rsp+0C8h+var_70]
0x1800f6bca  mov     rax, [rax+80h]
0x1800f6bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6bd6  nop
0x1800f6bd7  mov     rax, [rsi]
0x1800f6bda  mov     rax, [rax+98h]
0x1800f6be1  movups  xmm0, xmmword ptr [r12+30h]
0x1800f6be7  lea     rdx, [rsp+0C8h+var_58]
0x1800f6bec  mov     rcx, rsi
0x1800f6bef  movdqu  [rsp+0C8h+var_58], xmm0
0x1800f6bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6bfa  test    r14b, r14b
0x1800f6bfd  jz      loc_1800F6E36
0x1800f6c03  xor     r14d, r14d
0x1800f6c06  test    al, al
0x1800f6c08  jz      loc_1800F6CB8
0x1800f6c0e  mov     rax, [rsp+0C8h+arg_38]
0x1800f6c16  mov     [rsp+0C8h+var_80], rax
0x1800f6c1b  mov     [rsp+0C8h+var_88], r14
0x1800f6c20  mov     [rsp+0C8h+var_90], r14
0x1800f6c25  mov     rax, [rsp+0C8h+arg_30]
0x1800f6c2d  mov     [rsp+0C8h+var_98], rax
0x1800f6c32  mov     rax, [rsp+0C8h+arg_28]
0x1800f6c3a  mov     [rsp+0C8h+var_A0], rax
0x1800f6c3f  mov     eax, [rsp+0C8h+arg_20]
0x1800f6c46  mov     [rsp+0C8h+var_A8], eax; int
0x1800f6c4a  mov     r9d, r13d
0x1800f6c4d  mov     r8, r12
0x1800f6c50  mov     rdx, [rsp+0C8h+arg_8]
0x1800f6c58  mov     rcx, rsi
0x1800f6c5b  call    ?GetSaDeviceWrapper@CBtAudioResourceManagerBase@@IEAAJPEAUEndpointCharacteristicsDescriptor@@PEAUSaDeviceParams@@KW4_AUDCLNT_SHAREMODE@@AEAUSaDeviceResourceParams@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEBU_GUID@@5PEAPEAUISaDeviceProxy@@@Z; CBtAudioResourceManagerBase::GetSaDeviceWrapper(EndpointCharacteristicsDescriptor *,SaDeviceParams *,ulong,_AUDCLNT_SHAREMODE,SaDeviceResourceParams &,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &,_GUID const *,_GUID const *,ISaDeviceProxy * *)
0x1800f6c60  mov     edi, eax
0x1800f6c62  test    eax, eax
0x1800f6c64  jns     loc_1800F72DD
0x1800f6c6a  mov     rcx, [rsp+0C8h]; this
0x1800f6c72  mov     r9d, eax; char *
0x1800f6c75  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6c7c  mov     edx, 375h; void *
0x1800f6c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6c86  nop
0x1800f6c87  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6c8c  test    rcx, rcx
0x1800f6c8f  jz      short loc_1800F6C98
0x1800f6c91  call    cs:__imp_LeaveCriticalSection
0x1800f6c97  nop
0x1800f6c98  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6c9d  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6ca2  nop
0x1800f6ca3  test    rbx, rbx
0x1800f6ca6  jz      short loc_1800F6CB1
0x1800f6ca8  mov     rcx, rbx; lpCriticalSection
0x1800f6cab  call    cs:__imp_LeaveCriticalSection
0x1800f6cb1  mov     eax, edi
0x1800f6cb3  jmp     loc_1800F7312
0x1800f6cb8  mov     rdx, rdi; struct CEndpointStore *
0x1800f6cbb  call    ?DoExclusiveModeSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@@Z; CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(CEndpointStore *)
0x1800f6cc0  test    al, al
0x1800f6cc2  jz      short loc_1800F6D17
0x1800f6cc4  mov     rcx, [rsp+0C8h]; this
0x1800f6ccc  mov     edi, 887C007Ah
0x1800f6cd1  mov     r9d, edi; char *
0x1800f6cd4  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6cdb  mov     edx, 37Eh; void *
0x1800f6ce0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6ce5  nop
0x1800f6ce6  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6ceb  test    rcx, rcx
0x1800f6cee  jz      short loc_1800F6CF7
0x1800f6cf0  call    cs:__imp_LeaveCriticalSection
0x1800f6cf6  nop
0x1800f6cf7  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6cfc  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6d01  nop
0x1800f6d02  test    rbx, rbx
0x1800f6d05  jz      short loc_1800F6D10
0x1800f6d07  mov     rcx, rbx; lpCriticalSection
0x1800f6d0a  call    cs:__imp_LeaveCriticalSection
0x1800f6d10  mov     eax, edi
0x1800f6d12  jmp     loc_1800F7312
0x1800f6d17  mov     [rsp+0C8h+arg_0], r14
0x1800f6d1f  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6d27  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f6d2c  lea     r8, [rsp+0C8h+arg_0]; struct ISaDeviceProxy **
0x1800f6d34  mov     rdx, rdi; struct CEndpointStore *
0x1800f6d37  mov     rcx, rsi; this
0x1800f6d3a  call    ?DoSecondaryProfileSharedModeRenderSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@PEAPEAUISaDeviceProxy@@@Z; CBtAudioResourceManagerBase::DoSecondaryProfileSharedModeRenderSaDevicesExist(CEndpointStore *,ISaDeviceProxy * *)
0x1800f6d3f  test    al, al
0x1800f6d41  jz      short loc_1800F6DA2
0x1800f6d43  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6d4b  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800f6d50  mov     rcx, [rsp+0C8h+arg_38]
0x1800f6d58  mov     rax, [rsp+0C8h+arg_0]
0x1800f6d60  mov     [rcx], rax
0x1800f6d63  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6d6b  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f6d70  nop
0x1800f6d71  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6d76  test    rcx, rcx
0x1800f6d79  jz      short loc_1800F6D82
0x1800f6d7b  call    cs:__imp_LeaveCriticalSection
0x1800f6d81  nop
0x1800f6d82  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6d87  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6d8c  nop
0x1800f6d8d  test    rbx, rbx
0x1800f6d90  jz      short loc_1800F6D9B
0x1800f6d92  mov     rcx, rbx; lpCriticalSection
0x1800f6d95  call    cs:__imp_LeaveCriticalSection
0x1800f6d9b  xor     eax, eax
0x1800f6d9d  jmp     loc_1800F7312
0x1800f6da2  mov     r9, [rsp+0C8h+arg_38]
0x1800f6daa  mov     r8, [rsp+0C8h+arg_30]
0x1800f6db2  mov     rdx, [rsp+0C8h+arg_28]
0x1800f6dba  mov     rcx, rsi; this
0x1800f6dbd  call    ?CreateSecondaryProfileRenderSaDeviceWithDefaultParameters@CBtAudioResourceManagerBase@@IEAAJAEAUSaDeviceResourceParams@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUISaDeviceProxy@@@Z; CBtAudioResourceManagerBase::CreateSecondaryProfileRenderSaDeviceWithDefaultParameters(SaDeviceResourceParams &,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &,ISaDeviceProxy * *)
0x1800f6dc2  mov     edi, eax
0x1800f6dc4  test    eax, eax
0x1800f6dc6  jns     short loc_1800F6E24
0x1800f6dc8  mov     rcx, [rsp+0C8h]; this
0x1800f6dd0  mov     r9d, eax; char *
0x1800f6dd3  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6dda  mov     edx, 38Ah; void *
0x1800f6ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6de4  nop
0x1800f6de5  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6ded  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f6df2  nop
0x1800f6df3  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6df8  test    rcx, rcx
0x1800f6dfb  jz      short loc_1800F6E04
0x1800f6dfd  call    cs:__imp_LeaveCriticalSection
0x1800f6e03  nop
0x1800f6e04  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6e09  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6e0e  nop
0x1800f6e0f  test    rbx, rbx
0x1800f6e12  jz      short loc_1800F6E1D
0x1800f6e14  mov     rcx, rbx; lpCriticalSection
0x1800f6e17  call    cs:__imp_LeaveCriticalSection
0x1800f6e1d  mov     eax, edi
0x1800f6e1f  jmp     loc_1800F7312
0x1800f6e24  lea     rcx, [rsp+0C8h+arg_0]
0x1800f6e2c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f6e31  jmp     loc_1800F72DD
0x1800f6e36  xor     r14d, r14d
0x1800f6e39  mov     rdx, rdi; struct CEndpointStore *
0x1800f6e3c  test    al, al
0x1800f6e3e  jz      loc_1800F7087
0x1800f6e44  call    ?DoExclusiveModeSaDevicesExist@CBtAudioResourceManagerBase@@IEAA_NPEAVCEndpointStore@@@Z; CBtAudioResourceManagerBase::DoExclusiveModeSaDevicesExist(CEndpointStore *)
0x1800f6e49  test    al, al
0x1800f6e4b  jz      short loc_1800F6EA0
0x1800f6e4d  mov     rcx, [rsp+0C8h]; this
0x1800f6e55  mov     edi, 887C005Ch
0x1800f6e5a  mov     r9d, edi; char *
0x1800f6e5d  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6e64  mov     edx, 396h; void *
0x1800f6e69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6e6e  nop
0x1800f6e6f  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6e74  test    rcx, rcx
0x1800f6e77  jz      short loc_1800F6E80
0x1800f6e79  call    cs:__imp_LeaveCriticalSection
0x1800f6e7f  nop
0x1800f6e80  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6e85  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6e8a  nop
0x1800f6e8b  test    rbx, rbx
0x1800f6e8e  jz      short loc_1800F6E99
0x1800f6e90  mov     rcx, rbx; lpCriticalSection
0x1800f6e93  call    cs:__imp_LeaveCriticalSection
0x1800f6e99  mov     eax, edi
0x1800f6e9b  jmp     loc_1800F7312
0x1800f6ea0  mov     qword ptr [rsp+0C8h+var_58], rsi
0x1800f6ea5  mov     byte ptr [rsp+0C8h+var_58+8], 1
0x1800f6eaa  lea     r8, [rsp+0C8h+arg_0]; bool *
0x1800f6eb2  mov     rdx, rdi; struct CEndpointStore *
0x1800f6eb5  mov     rcx, rsi; this
0x1800f6eb8  call    ?FreePrimaryProfileRenderSaDevicesAndSaveDisplacedStreamGroups@CBtAudioResourceManagerBase@@IEAAJPEAVCEndpointStore@@PEA_N@Z; CBtAudioResourceManagerBase::FreePrimaryProfileRenderSaDevicesAndSaveDisplacedStreamGroups(CEndpointStore *,bool *)
0x1800f6ebd  mov     edi, eax
0x1800f6ebf  test    eax, eax
0x1800f6ec1  jns     short loc_1800F6F1A
0x1800f6ec3  mov     rcx, [rsp+0C8h]; this
0x1800f6ecb  mov     r9d, eax; char *
0x1800f6ece  lea     r8, aAvcoreAudiocor_19; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f6ed5  mov     edx, 39Fh; void *
0x1800f6eda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6edf  nop
0x1800f6ee0  mov     rcx, rsi; this
0x1800f6ee3  call    ?RestoreDisplacedPrimaryProfileStreamGroups@CBtAudioResourceManagerBase@@IEAAJXZ; CBtAudioResourceManagerBase::RestoreDisplacedPrimaryProfileStreamGroups(void)
0x1800f6ee8  nop
0x1800f6ee9  mov     rcx, [rsp+0C8h+var_70]; lpCriticalSection
0x1800f6eee  test    rcx, rcx
0x1800f6ef1  jz      short loc_1800F6EFA
0x1800f6ef3  call    cs:__imp_LeaveCriticalSection
0x1800f6ef9  nop
0x1800f6efa  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800f6eff  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1800f6f04  nop
0x1800f6f05  test    rbx, rbx
0x1800f6f08  jz      short loc_1800F6F13
0x1800f6f0a  mov     rcx, rbx; lpCriticalSection
0x1800f6f0d  call    cs:__imp_LeaveCriticalSection
0x1800f6f13  mov     eax, edi
0x1800f6f15  jmp     loc_1800F7312
0x1800f6f1a  mov     [rsp+0C8h+var_68], r14
0x1800f6f1f  lea     rcx, [rsp+0C8h+var_68]
0x1800f6f24  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f6f29  lea     rax, [rsp+0C8h+var_68]
0x1800f6f2e  mov     [rsp+0C8h+var_80], rax
0x1800f6f33  mov     [rsp+0C8h+var_88], r14
0x1800f6f38  mov     [rsp+0C8h+var_90], r14
  ... truncated ...
```
