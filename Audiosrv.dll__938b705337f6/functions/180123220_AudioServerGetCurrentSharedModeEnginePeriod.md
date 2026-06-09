# AudioServerGetCurrentSharedModeEnginePeriod

- ea: `0x180123220`
- end: `0x180123bc3`
- name: `AudioServerGetCurrentSharedModeEnginePeriod`
- size: `2467`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x18000af90`
- `0x1800126bc`
- `0x180018198`
- `0x18001b3d0`
- `0x18001d69c`
- `0x18001e7dc`
- `0x18001f6b0`
- `0x18001fa40`
- `0x180025d64`
- `0x180031778`
- `0x180031b20`
- `0x18003cee0`
- `0x18003f11c`
- `0x180040938`
- `0x1800423cc`
- `0x180045068`
- `0x180050bc0`
- `0x180055f44`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x1800d2588`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x18011e20c`
- `0x180121e04`
- `0x180123220`
- `0x180141840`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180123298`
- `ntdll!EtwEventActivityIdControl` at `0x180123b82`
- `ntdll!EtwEventActivityIdControl` at `0x180123298`
- `ntdll!EtwEventActivityIdControl` at `0x180123b82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801235a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801237e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801237f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123aed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801235a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801237e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801237f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123aed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123b00`

## string_xrefs

- `0x180123373`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801233b8`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123488`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x18012357b`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801235d9`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123646`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801237ca`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123880`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801238e6`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x18012394a`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801239b1`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c
__int64 __fastcall AudioServerGetCurrentSharedModeEnginePeriod(
        __int64 a1,
        const unsigned __int16 *a2,
        __int128 *a3,
        _QWORD *a4,
        unsigned int *a5)
{
  __int128 v6; // xmm0
  void *v9; // r14
  struct _FILETIME v10; // rbx
  __int64 v11; // rax
  void *v12; // r14
  struct _FILETIME v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  int MixFormat; // ebx
  int EndpointCharacteristicsDescriptor; // eax
  __int64 v18; // rdx
  __int64 v19; // rax
  CEndpointStoreCache *v20; // rcx
  int EndpointStore; // eax
  struct CEndpointStore *v22; // rbx
  int v23; // eax
  struct _GUID v24; // xmm6
  __int64 v25; // rbx
  __int64 v26; // rdi
  struct _GUID v27; // xmm7
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v28; // edx
  void *v29; // rcx
  HRESULT AudioMediaType; // eax
  EffectPack *v31; // rbx
  struct _GUID v32; // xmm8
  int SharedModeEnginePeriodicity; // eax
  __int64 v34; // rdx
  unsigned __int64 v35; // r9
  const struct tWAVEFORMATEX *v36; // rax
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v37; // edx
  __int64 v38; // rdx
  void *v39; // rcx
  __int64 v40; // rax
  const struct tWAVEFORMATEX *v41; // rax
  __int64 v42; // rdx
  WAVEFORMATEX *v43; // rcx
  void *v44; // rcx
  HRESULT v45; // eax
  EffectPack *v46; // rbx
  struct _GUID v47; // xmm6
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v48; // r8d
  int v49; // eax
  EffectPack *v50; // rbx
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v51; // r8d
  int v52; // eax
  EffectPack *v53; // rbx
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v54; // r8d
  int v55; // eax
  unsigned __int64 v56; // r9
  __int64 v57; // rdx
  const struct tWAVEFORMATEX *v58; // rax
  _QWORD *v59; // rbx
  double v60; // xmm6_8
  unsigned __int16 *v61; // r9
  DWORD nSamplesPerSec; // edx
  unsigned int v63; // r8d
  void *v64; // rax
  WAVEFORMATEX *v65; // rcx
  void *v66; // rcx
  BOOL pftDueTime; // [rsp+28h] [rbp-E0h]
  int pftDueTimea; // [rsp+28h] [rbp-E0h]
  int pftDueTimeb; // [rsp+28h] [rbp-E0h]
  int v71; // [rsp+38h] [rbp-D0h]
  WAVEFORMATEX *pAudioFormat; // [rsp+88h] [rbp-80h] BYREF
  LPVOID Src; // [rsp+90h] [rbp-78h] BYREF
  __int128 v74; // [rsp+98h] [rbp-70h] BYREF
  __int64 v75; // [rsp+A8h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-58h] BYREF
  IAudioMediaType *v77; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD *v78; // [rsp+C0h] [rbp-48h] BYREF
  struct CEndpointStore *v79; // [rsp+C8h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D0h] [rbp-38h] BYREF
  IAudioMediaType *ppIAudioMediaType[2]; // [rsp+D8h] [rbp-30h] BYREF
  EffectPack *v82[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v83; // [rsp+F8h] [rbp-10h]
  struct _GUID v84; // [rsp+108h] [rbp+0h] BYREF
  struct _GUID v85; // [rsp+118h] [rbp+10h] BYREF
  char v86; // [rsp+128h] [rbp+20h]
  struct tWAVEFORMATEX *v87[2]; // [rsp+138h] [rbp+30h] BYREF
  _QWORD **v88; // [rsp+148h] [rbp+40h]
  struct _GUID v89; // [rsp+158h] [rbp+50h] BYREF
  __int64 v90; // [rsp+168h] [rbp+60h] BYREF
  __int64 v91; // [rsp+170h] [rbp+68h] BYREF
  __int128 v92; // [rsp+178h] [rbp+70h]
  _QWORD v93[2]; // [rsp+188h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+210h] [rbp+108h]

  v6 = *a3;
  v93[0] = *(_QWORD *)a3;
  v93[1] = *((_QWORD *)a3 + 1);
  v92 = v6;
  EtwEventActivityIdControl(4, v93);
  v91 = 0;
  v90 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v9 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
    {
      v10 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v11 = CWatchdogTimer<1>::CWatchdogTimer<1>(v9, v10);
    }
    else
    {
      v11 = 0;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v91, v11);
  }
  else
  {
    v12 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v12 )
    {
      v13 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v14 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v12, v13);
    }
    else
    {
      v14 = 0;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v90, v14);
  }
  v15 = ValidateVadServerSettings((struct VadServerSettings *)a3);
  MixFormat = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104C,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)v15,
      pftDueTime);
    goto LABEL_84;
  }
  v83 = 0;
  *(_OWORD *)v82 = 0;
  EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                        a2,
                                        0,
                                        (struct EndpointCharacteristicsDescriptor *)v82);
  MixFormat = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    v18 = 4178;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
      pftDueTime);
LABEL_15:
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v82);
    goto LABEL_84;
  }
  v84 = 0;
  v19 = *(_QWORD *)v82[0];
  v89 = 0;
  *(_OWORD *)ppIAudioMediaType = 0;
  pftDueTime = (*(__int64 (__fastcall **)(EffectPack *))(v19 + 56))(v82[0]) == 1;
  EndpointCharacteristicsDescriptor = DeriveAudioProcessingModeConfiguration(
                                        *((unsigned int *)a3 + 12),
                                        *((unsigned int *)a3 + 14),
                                        *((unsigned int *)a3 + 32),
                                        v82);
  MixFormat = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    v18 = 4200;
    goto LABEL_14;
  }
  v79 = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(v20, a2, &v79);
  MixFormat = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106E,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)EndpointStore,
      pftDueTime);
LABEL_20:
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v79);
    goto LABEL_15;
  }
  v22 = v79;
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v79 + 13) + 128LL))(
    *((_QWORD *)v79 + 13),
    &lpCriticalSection);
  v78 = 0;
  v75 = 0;
  v74 = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)v22 + 13) + 96LL))(*((_QWORD *)v22 + 13), &v74);
  v24 = v84;
  if ( v23 >= 0 )
  {
    v26 = *((_QWORD *)&v74 + 1);
    v25 = v74;
    v88 = &v78;
    *(struct _GUID *)v87 = v84;
    while ( v25 != v26 )
    {
      lambda_8758ae7f98e4e08b9091e4a99aebcd74_::operator()(v87, v25);
      v25 += 8;
    }
  }
  Src = 0;
  pAudioFormat = 0;
  if ( v78 )
  {
    v87[1] = 0;
    v87[0] = (struct tWAVEFORMATEX *)&pAudioFormat;
    v40 = *v78;
    LOBYTE(v88) = 1;
    v41 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(_QWORD *))(v40 + 48))(v78);
    MixFormat = CloneWaveFormat(v41, &v87[1]);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v87);
    if ( MixFormat < 0 )
    {
      v42 = 4231;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
        (const char *)(unsigned int)MixFormat,
        pftDueTime);
LABEL_48:
      v43 = pAudioFormat;
      pAudioFormat = 0;
      if ( v43 )
        CoTaskMemFree(v43);
      v44 = Src;
      Src = 0;
      if ( v44 )
        CoTaskMemFree(v44);
      if ( (_QWORD)v74 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(v74, *((_QWORD *)&v74 + 1));
        std::_Deallocate<16>(v74, (v75 - v74) & 0xFFFFFFFFFFFFFFF8uLL);
        v75 = 0;
        v74 = 0;
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v78);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      goto LABEL_20;
    }
    v77 = 0;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v77);
    v45 = CreateAudioMediaType(pAudioFormat, pAudioFormat->cbSize + 18, &v77);
    MixFormat = v45;
    if ( v45 >= 0 )
    {
      v46 = v82[1];
      *(_QWORD *)&v84.Data1 = 0;
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v84);
      v47 = v89;
      v48 = *((_DWORD *)a3 + 13);
      v85 = v89;
      v49 = EffectPack::DeriveDevicePipeFormatFromConnectorFormat(v46, &v85, v48, v77, (struct IAudioMediaType **)&v84);
      MixFormat = v49;
      if ( v49 >= 0 )
      {
        v50 = v82[1];
        ppIAudioMediaType[0] = 0;
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(ppIAudioMediaType);
        v51 = *((_DWORD *)a3 + 13);
        v85 = v47;
        v52 = EffectPack::DeriveMixFormatFromDevicePipeFormat(
                v50,
                &v85,
                v51,
                *(struct IAudioMediaType **)&v84.Data1,
                ppIAudioMediaType,
                0);
        MixFormat = v52;
        if ( v52 >= 0 )
        {
          v53 = v82[1];
          pv = 0;
          wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&pv);
          v54 = *((_DWORD *)a3 + 13);
          v85 = v47;
          v55 = EffectPack::DeriveStreamFormatFromMixFormat(
                  v53,
                  &v85,
                  v54,
                  ppIAudioMediaType[0],
                  (struct IAudioMediaType **)&pv);
          MixFormat = v55;
          if ( v55 >= 0 )
          {
            v87[0] = (struct tWAVEFORMATEX *)&Src;
            v87[1] = 0;
            LOBYTE(v88) = 1;
            v58 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 40LL))(pv);
            MixFormat = CloneWaveFormat(v58, &v87[1]);
            wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v87);
            if ( MixFormat >= 0 )
            {
              v59 = v78;
              v60 = (double)*(int *)(((__int64 (__fastcall *)(IAudioMediaType *))v77->lpVtbl->GetAudioFormat)(v77) + 4);
              *a5 = (int)((double)(*(int (__fastcall **)(_QWORD *))(*v59 + 32LL))(v59) * v60 / 10000000.0 + 0.5);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pv);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(ppIAudioMediaType);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v77);
              goto LABEL_71;
            }
            v56 = (unsigned int)MixFormat;
            v57 = 4249;
          }
          else
          {
            v56 = (unsigned int)v55;
            v57 = 4247;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v57,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
            (const char *)v56,
            pftDueTime);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pv);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1094,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
            (const char *)(unsigned int)v52,
            pftDueTimeb);
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(ppIAudioMediaType);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1091,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
          (const char *)(unsigned int)v49,
          pftDueTimea);
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108C,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
        (const char *)(unsigned int)v45,
        pftDueTime);
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v77);
    goto LABEL_48;
  }
  v27 = *(struct _GUID *)ppIAudioMediaType;
  v28 = *((_DWORD *)a3 + 13);
  *(_QWORD *)&v85.Data1 = &pv;
  v84 = *(struct _GUID *)ppIAudioMediaType;
  pv = 0;
  *(_QWORD *)v85.Data4 = 0;
  v86 = 1;
  MixFormat = EffectPack::GetMixFormat(v82[1], v28, &v84, (struct tWAVEFORMATEX **)v85.Data4);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
  if ( MixFormat < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A2,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)MixFormat,
      pftDueTime);
    goto LABEL_28;
  }
  ppIAudioMediaType[0] = 0;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(ppIAudioMediaType);
  AudioMediaType = CreateAudioMediaType((const WAVEFORMATEX *)pv, *((unsigned __int16 *)pv + 8) + 18, ppIAudioMediaType);
  MixFormat = AudioMediaType;
  if ( AudioMediaType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)AudioMediaType,
      pftDueTime);
LABEL_32:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(ppIAudioMediaType);
LABEL_28:
    v29 = pv;
    pv = 0;
    if ( v29 )
      CoTaskMemFree(v29);
    goto LABEL_48;
  }
  v31 = v82[1];
  v77 = 0;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v77);
  v32 = v89;
  SharedModeEnginePeriodicity = EffectPack::DeriveStreamFormatFromMixFormat(
                                  v31,
                                  &v89,
                                  (enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)*((_DWORD *)a3 + 13),
                                  ppIAudioMediaType[0],
                                  &v77);
  MixFormat = SharedModeEnginePeriodicity;
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v34 = 4264;
LABEL_35:
    v35 = (unsigned int)SharedModeEnginePeriodicity;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)v35,
      pftDueTime);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v77);
    goto LABEL_32;
  }
  *(_QWORD *)&v85.Data1 = &Src;
  *(_QWORD *)v85.Data4 = 0;
  v86 = 1;
  v36 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))v77->lpVtbl->GetAudioFormat)(v77);
  MixFormat = CloneWaveFormat(v36, (struct tWAVEFORMATEX **)v85.Data4);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
  if ( MixFormat < 0 )
  {
    v35 = (unsigned int)MixFormat;
    v34 = 4266;
    goto LABEL_36;
  }
  v37 = *((_DWORD *)a3 + 13);
  v87[0] = (struct tWAVEFORMATEX *)&pAudioFormat;
  v87[1] = 0;
  v71 = *((_DWORD *)a3 + 17);
  LOBYTE(v88) = 1;
  v89 = v24;
  v84 = v32;
  v85 = v27;
  MixFormat = DeriveConnectorFormatFromStreamFormat(v82, v37, (IAudioMediaType *)pv, &v85, &v84, &v89, v71, &v87[1]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v87);
  if ( MixFormat < 0 )
  {
    v35 = (unsigned int)MixFormat;
    v34 = 4277;
    goto LABEL_36;
  }
  v38 = *((unsigned int *)a3 + 13);
  pftDueTime = 0;
  v85 = v24;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(v82[1], v38, pAudioFormat, &v85);
  MixFormat = SharedModeEnginePeriodicity;
  if ( SharedModeEnginePeriodicity < 0 )
  {
    v34 = 4279;
    goto LABEL_35;
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v77);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(ppIAudioMediaType);
  v39 = pv;
  pv = 0;
  if ( v39 )
    CoTaskMemFree(v39);
LABEL_71:
  v61 = (unsigned __int16 *)Src;
  nSamplesPerSec = pAudioFormat->nSamplesPerSec;
  v63 = *((_DWORD *)Src + 1);
  if ( v63 != nSamplesPerSec )
    *a5 = TranslateFrameCountBetweenSamplingRates(*a5, nSamplesPerSec, v63);
  v64 = MIDL_user_allocate(v61[8] + 18LL);
  *a4 = v64;
  if ( !v64 )
  {
    MixFormat = -2147024882;
    v42 = 4294;
    goto LABEL_47;
  }
  memcpy_0(v64, Src, *((unsigned __int16 *)Src + 8) + 18LL);
  v65 = pAudioFormat;
  pAudioFormat = 0;
  if ( v65 )
    CoTaskMemFree(v65);
  v66 = Src;
  Src = 0;
  if ( v66 )
    CoTaskMemFree(v66);
  if ( (_QWORD)v74 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(v74, *((_QWORD *)&v74 + 1));
    std::_Deallocate<16>(v74, (v75 - v74) & 0xFFFFFFFFFFFFFFF8uLL);
    v75 = 0;
    v74 = 0;
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v78);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v79);
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v82);
  MixFormat = 0;
LABEL_84:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v90);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v91);
  EtwEventActivityIdControl(4, v93);
  return (unsigned int)MixFormat;
}

```

## disassembly

```asm
0x180123220  mov     rax, rsp
0x180123223  mov     [rax+8], rbx
0x180123227  push    rbp
0x180123228  push    rsi
0x180123229  push    rdi
0x18012322a  push    r12
0x18012322c  push    r13
0x18012322e  push    r14
0x180123230  push    r15
0x180123232  lea     rbp, [rax-108h]
0x180123239  sub     rsp, 1D0h
0x180123240  movaps  xmmword ptr [rax-48h], xmm6
0x180123244  movaps  xmmword ptr [rax-58h], xmm7
0x180123248  movaps  xmmword ptr [rax-68h], xmm8
0x18012324d  mov     rax, cs:__security_cookie
0x180123254  xor     rax, rsp
0x180123257  mov     [rbp+100h+var_70], rax
0x18012325e  mov     rax, [r8]
0x180123261  mov     r15, rdx
0x180123264  movups  xmm0, xmmword ptr [r8]
0x180123268  mov     r12, [rbp+100h+arg_20]
0x18012326f  lea     rdx, [rbp+100h+var_80]
0x180123276  mov     [rbp+100h+var_80], rax
0x18012327d  mov     ecx, 4
0x180123282  mov     rax, [r8+8]
0x180123286  mov     r13, r9
0x180123289  mov     [rbp+100h+var_78], rax
0x180123290  mov     rsi, r8
0x180123293  movdqu  [rbp+100h+var_90], xmm0
0x180123298  call    cs:__imp_EtwEventActivityIdControl
0x18012329e  xor     edi, edi
0x1801232a0  mov     [rbp+100h+var_98], rdi
0x1801232a4  mov     [rbp+100h+var_A0], rdi
0x1801232a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x1801232af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x1801232b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801232bb  lea     ecx, [rdi+38h]; unsigned __int64
0x1801232be  test    al, al
0x1801232c0  jz      short loc_180123311
0x1801232c2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801232c7  mov     r14, rax
0x1801232ca  test    rax, rax
0x1801232cd  jz      short loc_180123300
0x1801232cf  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1801232d6  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x1801232dc  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1801232e1  lea     r9, aAudioserverget_19; "AudioServerGetCurrentSharedModeEnginePe"...
0x1801232e8  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x1801232ed  mov     r8d, edi
0x1801232f0  mov     rcx, r14; pv
0x1801232f3  mov     rdx, [rax+8]
0x1801232f7  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x1801232fc  xor     edi, edi
0x1801232fe  jmp     short loc_180123303
0x180123300  mov     rax, rdi
0x180123303  mov     rdx, rax
0x180123306  lea     rcx, [rbp+100h+var_98]
0x18012330a  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x18012330f  jmp     short loc_18012335E
0x180123311  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180123316  mov     r14, rax
0x180123319  test    rax, rax
0x18012331c  jz      short loc_18012334F
0x18012331e  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180123325  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18012332b  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180123330  lea     r9, aAudioserverget_19; "AudioServerGetCurrentSharedModeEnginePe"...
0x180123337  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18012333c  mov     r8d, edi
0x18012333f  mov     rcx, r14; pv
0x180123342  mov     rdx, [rax+8]
0x180123346  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x18012334b  xor     edi, edi
0x18012334d  jmp     short loc_180123352
0x18012334f  mov     rax, rdi
0x180123352  mov     rdx, rax
0x180123355  lea     rcx, [rbp+100h+var_A0]
0x180123359  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x18012335e  mov     rcx, rsi; struct VadServerSettings *
0x180123361  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x180123366  mov     ebx, eax
0x180123368  test    eax, eax
0x18012336a  jns     short loc_18012338C
0x18012336c  mov     rcx, [rbp+108h]; this
0x180123373  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18012337a  mov     r9d, eax; char *
0x18012337d  mov     edx, 104Ch; void *
0x180123382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123387  jmp     loc_180123B64
0x18012338c  xorps   xmm0, xmm0
0x18012338f  mov     [rbp+100h+var_110], rdi
0x180123393  lea     r8, [rbp+100h+var_120]; struct EndpointCharacteristicsDescriptor *
0x180123397  xor     edx, edx; int
0x180123399  mov     rcx, r15; unsigned __int16 *
0x18012339c  movdqu  xmmword ptr [rbp+100h+var_120], xmm0
0x1801233a1  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x1801233a6  mov     ebx, eax
0x1801233a8  test    eax, eax
0x1801233aa  jns     short loc_1801233D5
0x1801233ac  mov     edx, 1052h; void *
0x1801233b1  mov     rcx, [rbp+108h]; this
0x1801233b8  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801233bf  mov     r9d, eax; char *
0x1801233c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801233c7  lea     rcx, [rbp+100h+var_120]; this
0x1801233cb  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1801233d0  jmp     loc_180123B64
0x1801233d5  mov     rcx, [rbp+100h+var_120]
0x1801233d9  xorps   xmm0, xmm0
0x1801233dc  mov     ebx, [rsi+34h]
0x1801233df  xorps   xmm1, xmm1
0x1801233e2  movups  xmmword ptr [rbp+100h+var_100.Data1], xmm0
0x1801233e6  mov     rax, [rcx]
0x1801233e9  movups  xmmword ptr [rbp+100h+var_B0.Data1], xmm1
0x1801233ed  movups  xmmword ptr [rbp+100h+ppIAudioMediaType], xmm0
0x1801233f1  mov     rax, [rax+38h]
0x1801233f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801233fa  mov     r8d, [rsi+80h]
0x180123401  lea     r9, [rbp+100h+var_120]
0x180123405  mov     edx, [rsi+38h]
0x180123408  cmp     eax, 1
0x18012340b  mov     [rsp+200h+var_188], rdi
0x180123410  lea     rax, [rbp+100h+ppIAudioMediaType]
0x180123414  mov     [rsp+200h+var_190], rdi
0x180123419  mov     ecx, edi
0x18012341b  mov     [rsp+200h+var_198], rax
0x180123420  setz    cl
0x180123423  lea     rax, [rbp+100h+var_B0]
0x180123427  mov     [rsp+200h+var_1A0], rax
0x18012342c  lea     rax, [rbp+100h+var_100]
0x180123430  mov     [rsp+200h+var_1A8], rax
0x180123435  mov     [rsp+200h+var_1B0], rdi
0x18012343a  mov     dword ptr [rsp+200h+var_1B8], edi
0x18012343e  mov     [rsp+200h+var_1C0], edi
0x180123442  mov     [rsp+200h+var_1C8], rdi
0x180123447  mov     [rsp+200h+var_1D0], ebx
0x18012344b  mov     dword ptr [rsp+200h+var_1D8], edi
0x18012344f  mov     [rsp+200h+pftDueTime.dwLowDateTime], ecx; int
0x180123453  mov     ecx, [rsi+30h]
0x180123456  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x18012345b  mov     ebx, eax
0x18012345d  test    eax, eax
0x18012345f  jns     short loc_18012346B
0x180123461  mov     edx, 1068h
0x180123466  jmp     loc_1801233B1
0x18012346b  lea     r8, [rbp+100h+var_140]; struct CEndpointStore **
0x18012346f  mov     [rbp+100h+var_140], rdi
0x180123473  mov     rdx, r15; unsigned __int16 *
0x180123476  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x18012347b  mov     ebx, eax
0x18012347d  test    eax, eax
0x18012347f  jns     short loc_1801234AA
0x180123481  mov     rcx, [rbp+108h]; this
0x180123488  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18012348f  mov     r9d, eax; char *
0x180123492  mov     edx, 106Eh; void *
0x180123497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012349c  lea     rcx, [rbp+100h+var_140]
0x1801234a0  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1801234a5  jmp     loc_1801233C7
0x1801234aa  mov     rbx, [rbp+100h+var_140]
0x1801234ae  lea     rdx, [rbp+100h+lpCriticalSection]
0x1801234b2  mov     rcx, [rbx+68h]
0x1801234b6  mov     rax, [rcx]
0x1801234b9  mov     rax, [rax+80h]
0x1801234c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801234c5  mov     [rbp+100h+var_148], rdi
0x1801234c9  lea     rdx, [rbp+100h+var_170]
0x1801234cd  mov     [rbp+100h+var_160], rdi
0x1801234d1  xorps   xmm0, xmm0
0x1801234d4  movdqu  [rbp+100h+var_170], xmm0
0x1801234d9  mov     rcx, [rbx+68h]
0x1801234dd  mov     rax, [rcx]
0x1801234e0  mov     rax, [rax+60h]
0x1801234e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801234e9  movaps  xmm6, xmmword ptr [rbp+100h+var_100.Data1]
0x1801234ed  test    eax, eax
0x1801234ef  js      short loc_18012351F
0x1801234f1  mov     rbx, qword ptr [rbp+100h+var_170]
0x1801234f5  lea     rax, [rbp+100h+var_148]
0x1801234f9  mov     rdi, qword ptr [rbp+100h+var_170+8]
0x1801234fd  mov     [rbp+100h+var_C0], rax
0x180123501  movdqa  xmmword ptr [rbp+100h+var_D0], xmm6
0x180123506  cmp     rbx, rdi
0x180123509  jz      short loc_18012351D
0x18012350b  mov     rdx, rbx
0x18012350e  lea     rcx, [rbp+100h+var_D0]
0x180123512  call    _lambda_8758ae7f98e4e08b9091e4a99aebcd74___operator__
0x180123517  add     rbx, 8
0x18012351b  jmp     short loc_180123506
0x18012351d  xor     edi, edi
0x18012351f  mov     rcx, [rbp+100h+var_148]
0x180123523  mov     [rbp+100h+Src], rdi
0x180123527  mov     [rbp+100h+pAudioFormat], rdi
0x18012352b  test    rcx, rcx
0x18012352e  jnz     loc_180123783
0x180123534  movaps  xmm7, xmmword ptr [rbp+100h+ppIAudioMediaType]
0x180123538  lea     rax, [rbp+100h+pv]
0x18012353c  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18012353f  lea     r9, [rbp+100h+var_F0.Data4]; struct tWAVEFORMATEX **
0x180123543  mov     rcx, [rbp+100h+var_120+8]; this
0x180123547  lea     r8, [rbp+100h+var_100]; struct _GUID
0x18012354b  mov     qword ptr [rbp+100h+var_F0.Data1], rax
0x18012354f  movdqa  xmmword ptr [rbp+100h+var_100.Data1], xmm7
0x180123554  mov     [rbp+100h+pv], rdi
0x180123558  mov     qword ptr [rbp+100h+var_F0.Data4], rdi
0x18012355c  mov     [rbp+100h+var_E0], 1
0x180123560  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x180123565  lea     rcx, [rbp+100h+var_F0]
0x180123569  mov     ebx, eax
0x18012356b  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180123570  test    ebx, ebx
0x180123572  jns     short loc_1801235AB
0x180123574  mov     rcx, [rbp+108h]; this
0x18012357b  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180123582  mov     r9d, ebx; char *
0x180123585  mov     edx, 10A2h; void *
0x18012358a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012358f  mov     rcx, [rbp+100h+pv]; pv
0x180123593  mov     [rbp+100h+pv], rdi
0x180123597  test    rcx, rcx
0x18012359a  jz      loc_1801237D9
0x1801235a0  call    cs:__imp_CoTaskMemFree
0x1801235a6  jmp     loc_1801237D9
0x1801235ab  lea     rcx, [rbp+100h+ppIAudioMediaType]
0x1801235af  mov     [rbp+100h+ppIAudioMediaType], rdi
0x1801235b3  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1801235b8  mov     rcx, [rbp+100h+pv]; pAudioFormat
0x1801235bc  lea     r8, [rbp+100h+ppIAudioMediaType]; ppIAudioMediaType
0x1801235c0  movzx   edx, word ptr [rcx+10h]
0x1801235c4  add     edx, 12h; cbAudioFormatSize
0x1801235c7  call    CreateAudioMediaType
0x1801235cc  mov     ebx, eax
0x1801235ce  test    eax, eax
0x1801235d0  jns     short loc_1801235F8
0x1801235d2  mov     rcx, [rbp+108h]; this
0x1801235d9  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801235e0  mov     r9d, eax; char *
0x1801235e3  mov     edx, 10A5h; void *
0x1801235e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801235ed  lea     rcx, [rbp+100h+ppIAudioMediaType]
0x1801235f1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801235f6  jmp     short loc_18012358F
0x1801235f8  mov     rbx, [rbp+100h+var_120+8]
0x1801235fc  lea     rcx, [rbp+100h+var_150]
0x180123600  mov     [rbp+100h+var_150], rdi
0x180123604  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180123609  movaps  xmm8, xmmword ptr [rbp+100h+var_B0.Data1]
0x18012360e  lea     rax, [rbp+100h+var_150]
0x180123612  mov     r9, [rbp+100h+ppIAudioMediaType]; struct IAudioMediaType *
0x180123616  lea     rdx, [rbp+100h+var_B0]; struct _GUID
0x18012361a  mov     r8d, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18012361e  mov     rcx, rbx; this
0x180123621  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rax; int
0x180123626  movdqa  xmmword ptr [rbp+100h+var_B0.Data1], xmm8
0x18012362c  call    ?DeriveStreamFormatFromMixFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@@Z; EffectPack::DeriveStreamFormatFromMixFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *)
0x180123631  mov     ebx, eax
0x180123633  test    eax, eax
0x180123635  jns     short loc_18012365D
0x180123637  mov     edx, 10A8h; void *
0x18012363c  mov     r9d, eax; char *
0x18012363f  mov     rcx, [rbp+108h]; this
0x180123646  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18012364d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123652  lea     rcx, [rbp+100h+var_150]
0x180123656  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012365b  jmp     short loc_1801235ED
0x18012365d  mov     rcx, [rbp+100h+var_150]
0x180123661  lea     rax, [rbp+100h+Src]
0x180123665  mov     qword ptr [rbp+100h+var_F0.Data1], rax
0x180123669  mov     qword ptr [rbp+100h+var_F0.Data4], rdi
0x18012366d  mov     [rbp+100h+var_E0], 1
0x180123671  mov     rax, [rcx]
0x180123674  mov     rax, [rax+28h]
0x180123678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012367d  lea     rdx, [rbp+100h+var_F0.Data4]; struct tWAVEFORMATEX **
0x180123681  mov     rcx, rax; Src
0x180123684  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180123689  lea     rcx, [rbp+100h+var_F0]
0x18012368d  mov     ebx, eax
0x18012368f  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180123694  test    ebx, ebx
0x180123696  jns     short loc_1801236A2
0x180123698  mov     r9d, ebx
0x18012369b  mov     edx, 10AAh
0x1801236a0  jmp     short loc_18012363F
0x1801236a2  mov     r8, [rbp+100h+pv]; Src
0x1801236a6  lea     rax, [rbp+100h+pAudioFormat]
0x1801236aa  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801236ad  lea     r9, [rbp+100h+var_F0]; struct _GUID
0x1801236b1  mov     [rbp+100h+var_D0], rax
0x1801236b5  lea     rcx, [rbp+100h+var_120]; struct EndpointCharacteristicsDescriptor *
0x1801236b9  lea     rax, [rbp+100h+var_D0+8]
0x1801236bd  mov     [rbp+100h+var_D0+8], rdi
0x1801236c1  mov     [rsp+200h+var_1C8], rax; struct tWAVEFORMATEX **
0x1801236c6  mov     eax, [rsi+44h]
0x1801236c9  mov     [rsp+200h+var_1D0], eax; int
0x1801236cd  lea     rax, [rbp+100h+var_B0]
0x1801236d1  mov     [rsp+200h+var_1D8], rax; struct _GUID *
0x1801236d6  lea     rax, [rbp+100h+var_100]
  ... truncated ...
```
