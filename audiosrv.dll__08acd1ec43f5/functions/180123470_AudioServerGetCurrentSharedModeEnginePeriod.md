# AudioServerGetCurrentSharedModeEnginePeriod

- ea: `0x180123470`
- end: `0x180123e13`
- name: `AudioServerGetCurrentSharedModeEnginePeriod`
- size: `2467`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18000b0e0`
- `0x18001280c`
- `0x1800182e8`
- `0x18001b520`
- `0x18001d7ec`
- `0x18001e92c`
- `0x18001f800`
- `0x18001fb90`
- `0x180025eb4`
- `0x1800318d8`
- `0x180031c80`
- `0x18003d040`
- `0x18003f28c`
- `0x180040aa8`
- `0x1800424ec`
- `0x180044bd8`
- `0x180050730`
- `0x180055ab4`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1800d0598`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x18011e45c`
- `0x180122054`
- `0x180123470`
- `0x180142154`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1801234e8`
- `ntdll!EtwEventActivityIdControl` at `0x180123dd2`
- `ntdll!EtwEventActivityIdControl` at `0x1801234e8`
- `ntdll!EtwEventActivityIdControl` at `0x180123dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123d9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801237f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801239c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123d50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801237f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801239c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123d50`

## string_xrefs

- `0x1801235c3`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123608`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801236d8`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801237cb`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123829`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123896`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123a1a`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123ad0`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123b36`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123b9a`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180123c01`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x180123470  mov     rax, rsp
0x180123473  mov     [rax+8], rbx
0x180123477  push    rbp
0x180123478  push    rsi
0x180123479  push    rdi
0x18012347a  push    r12
0x18012347c  push    r13
0x18012347e  push    r14
0x180123480  push    r15
0x180123482  lea     rbp, [rax-108h]
0x180123489  sub     rsp, 1D0h
0x180123490  movaps  xmmword ptr [rax-48h], xmm6
0x180123494  movaps  xmmword ptr [rax-58h], xmm7
0x180123498  movaps  xmmword ptr [rax-68h], xmm8
0x18012349d  mov     rax, cs:__security_cookie
0x1801234a4  xor     rax, rsp
0x1801234a7  mov     [rbp+100h+var_70], rax
0x1801234ae  mov     rax, [r8]
0x1801234b1  mov     r15, rdx
0x1801234b4  movups  xmm0, xmmword ptr [r8]
0x1801234b8  mov     r12, [rbp+100h+arg_20]
0x1801234bf  lea     rdx, [rbp+100h+var_80]
0x1801234c6  mov     [rbp+100h+var_80], rax
0x1801234cd  mov     ecx, 4
0x1801234d2  mov     rax, [r8+8]
0x1801234d6  mov     r13, r9
0x1801234d9  mov     [rbp+100h+var_78], rax
0x1801234e0  mov     rsi, r8
0x1801234e3  movdqu  [rbp+100h+var_90], xmm0
0x1801234e8  call    cs:__imp_EtwEventActivityIdControl
0x1801234ee  xor     edi, edi
0x1801234f0  mov     [rbp+100h+var_98], rdi
0x1801234f4  mov     [rbp+100h+var_A0], rdi
0x1801234f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x1801234ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180123504  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012350b  lea     ecx, [rdi+38h]; unsigned __int64
0x18012350e  test    al, al
0x180123510  jz      short loc_180123561
0x180123512  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180123517  mov     r14, rax
0x18012351a  test    rax, rax
0x18012351d  jz      short loc_180123550
0x18012351f  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180123526  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18012352c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180123531  lea     r9, aAudioserverget_19; "AudioServerGetCurrentSharedModeEnginePe"...
0x180123538  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18012353d  mov     r8d, edi
0x180123540  mov     rcx, r14; pv
0x180123543  mov     rdx, [rax+8]
0x180123547  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x18012354c  xor     edi, edi
0x18012354e  jmp     short loc_180123553
0x180123550  mov     rax, rdi
0x180123553  mov     rdx, rax
0x180123556  lea     rcx, [rbp+100h+var_98]
0x18012355a  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x18012355f  jmp     short loc_1801235AE
0x180123561  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180123566  mov     r14, rax
0x180123569  test    rax, rax
0x18012356c  jz      short loc_18012359F
0x18012356e  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180123575  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18012357b  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180123580  lea     r9, aAudioserverget_19; "AudioServerGetCurrentSharedModeEnginePe"...
0x180123587  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18012358c  mov     r8d, edi
0x18012358f  mov     rcx, r14; pv
0x180123592  mov     rdx, [rax+8]
0x180123596  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x18012359b  xor     edi, edi
0x18012359d  jmp     short loc_1801235A2
0x18012359f  mov     rax, rdi
0x1801235a2  mov     rdx, rax
0x1801235a5  lea     rcx, [rbp+100h+var_A0]
0x1801235a9  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x1801235ae  mov     rcx, rsi; struct VadServerSettings *
0x1801235b1  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x1801235b6  mov     ebx, eax
0x1801235b8  test    eax, eax
0x1801235ba  jns     short loc_1801235DC
0x1801235bc  mov     rcx, [rbp+108h]; this
0x1801235c3  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801235ca  mov     r9d, eax; char *
0x1801235cd  mov     edx, 104Ch; void *
0x1801235d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801235d7  jmp     loc_180123DB4
0x1801235dc  xorps   xmm0, xmm0
0x1801235df  mov     [rbp+100h+var_110], rdi
0x1801235e3  lea     r8, [rbp+100h+var_120]; struct EndpointCharacteristicsDescriptor *
0x1801235e7  xor     edx, edx; int
0x1801235e9  mov     rcx, r15; unsigned __int16 *
0x1801235ec  movdqu  xmmword ptr [rbp+100h+var_120], xmm0
0x1801235f1  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x1801235f6  mov     ebx, eax
0x1801235f8  test    eax, eax
0x1801235fa  jns     short loc_180123625
0x1801235fc  mov     edx, 1052h; void *
0x180123601  mov     rcx, [rbp+108h]; this
0x180123608  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18012360f  mov     r9d, eax; char *
0x180123612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123617  lea     rcx, [rbp+100h+var_120]; this
0x18012361b  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x180123620  jmp     loc_180123DB4
0x180123625  mov     rcx, [rbp+100h+var_120]
0x180123629  xorps   xmm0, xmm0
0x18012362c  mov     ebx, [rsi+34h]
0x18012362f  xorps   xmm1, xmm1
0x180123632  movups  xmmword ptr [rbp+100h+var_100.Data1], xmm0
0x180123636  mov     rax, [rcx]
0x180123639  movups  xmmword ptr [rbp+100h+var_B0.Data1], xmm1
0x18012363d  movups  xmmword ptr [rbp+100h+ppIAudioMediaType], xmm0
0x180123641  mov     rax, [rax+38h]
0x180123645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012364a  mov     r8d, [rsi+80h]
0x180123651  lea     r9, [rbp+100h+var_120]
0x180123655  mov     edx, [rsi+38h]
0x180123658  cmp     eax, 1
0x18012365b  mov     [rsp+200h+var_188], rdi
0x180123660  lea     rax, [rbp+100h+ppIAudioMediaType]
0x180123664  mov     [rsp+200h+var_190], rdi
0x180123669  mov     ecx, edi
0x18012366b  mov     [rsp+200h+var_198], rax
0x180123670  setz    cl
0x180123673  lea     rax, [rbp+100h+var_B0]
0x180123677  mov     [rsp+200h+var_1A0], rax
0x18012367c  lea     rax, [rbp+100h+var_100]
0x180123680  mov     [rsp+200h+var_1A8], rax
0x180123685  mov     [rsp+200h+var_1B0], rdi
0x18012368a  mov     dword ptr [rsp+200h+var_1B8], edi
0x18012368e  mov     [rsp+200h+var_1C0], edi
0x180123692  mov     [rsp+200h+var_1C8], rdi
0x180123697  mov     [rsp+200h+var_1D0], ebx
0x18012369b  mov     dword ptr [rsp+200h+var_1D8], edi
0x18012369f  mov     [rsp+200h+pftDueTime.dwLowDateTime], ecx; int
0x1801236a3  mov     ecx, [rsi+30h]
0x1801236a6  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x1801236ab  mov     ebx, eax
0x1801236ad  test    eax, eax
0x1801236af  jns     short loc_1801236BB
0x1801236b1  mov     edx, 1068h
0x1801236b6  jmp     loc_180123601
0x1801236bb  lea     r8, [rbp+100h+var_140]; struct CEndpointStore **
0x1801236bf  mov     [rbp+100h+var_140], rdi
0x1801236c3  mov     rdx, r15; unsigned __int16 *
0x1801236c6  call    ?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z; CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)
0x1801236cb  mov     ebx, eax
0x1801236cd  test    eax, eax
0x1801236cf  jns     short loc_1801236FA
0x1801236d1  mov     rcx, [rbp+108h]; this
0x1801236d8  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801236df  mov     r9d, eax; char *
0x1801236e2  mov     edx, 106Eh; void *
0x1801236e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801236ec  lea     rcx, [rbp+100h+var_140]
0x1801236f0  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x1801236f5  jmp     loc_180123617
0x1801236fa  mov     rbx, [rbp+100h+var_140]
0x1801236fe  lea     rdx, [rbp+100h+lpCriticalSection]
0x180123702  mov     rcx, [rbx+68h]
0x180123706  mov     rax, [rcx]
0x180123709  mov     rax, [rax+80h]
0x180123710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123715  mov     [rbp+100h+var_148], rdi
0x180123719  lea     rdx, [rbp+100h+var_170]
0x18012371d  mov     [rbp+100h+var_160], rdi
0x180123721  xorps   xmm0, xmm0
0x180123724  movdqu  [rbp+100h+var_170], xmm0
0x180123729  mov     rcx, [rbx+68h]
0x18012372d  mov     rax, [rcx]
0x180123730  mov     rax, [rax+60h]
0x180123734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123739  movaps  xmm6, xmmword ptr [rbp+100h+var_100.Data1]
0x18012373d  test    eax, eax
0x18012373f  js      short loc_18012376F
0x180123741  mov     rbx, qword ptr [rbp+100h+var_170]
0x180123745  lea     rax, [rbp+100h+var_148]
0x180123749  mov     rdi, qword ptr [rbp+100h+var_170+8]
0x18012374d  mov     [rbp+100h+var_C0], rax
0x180123751  movdqa  xmmword ptr [rbp+100h+var_D0], xmm6
0x180123756  cmp     rbx, rdi
0x180123759  jz      short loc_18012376D
0x18012375b  mov     rdx, rbx
0x18012375e  lea     rcx, [rbp+100h+var_D0]
0x180123762  call    _lambda_8758ae7f98e4e08b9091e4a99aebcd74___operator__
0x180123767  add     rbx, 8
0x18012376b  jmp     short loc_180123756
0x18012376d  xor     edi, edi
0x18012376f  mov     rcx, [rbp+100h+var_148]
0x180123773  mov     [rbp+100h+Src], rdi
0x180123777  mov     [rbp+100h+pAudioFormat], rdi
0x18012377b  test    rcx, rcx
0x18012377e  jnz     loc_1801239D3
0x180123784  movaps  xmm7, xmmword ptr [rbp+100h+ppIAudioMediaType]
0x180123788  lea     rax, [rbp+100h+pv]
0x18012378c  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18012378f  lea     r9, [rbp+100h+var_F0.Data4]; struct tWAVEFORMATEX **
0x180123793  mov     rcx, [rbp+100h+var_120+8]; this
0x180123797  lea     r8, [rbp+100h+var_100]; struct _GUID
0x18012379b  mov     qword ptr [rbp+100h+var_F0.Data1], rax
0x18012379f  movdqa  xmmword ptr [rbp+100h+var_100.Data1], xmm7
0x1801237a4  mov     [rbp+100h+pv], rdi
0x1801237a8  mov     qword ptr [rbp+100h+var_F0.Data4], rdi
0x1801237ac  mov     [rbp+100h+var_E0], 1
0x1801237b0  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x1801237b5  lea     rcx, [rbp+100h+var_F0]
0x1801237b9  mov     ebx, eax
0x1801237bb  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801237c0  test    ebx, ebx
0x1801237c2  jns     short loc_1801237FB
0x1801237c4  mov     rcx, [rbp+108h]; this
0x1801237cb  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801237d2  mov     r9d, ebx; char *
0x1801237d5  mov     edx, 10A2h; void *
0x1801237da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801237df  mov     rcx, [rbp+100h+pv]; pv
0x1801237e3  mov     [rbp+100h+pv], rdi
0x1801237e7  test    rcx, rcx
0x1801237ea  jz      loc_180123A29
0x1801237f0  call    cs:__imp_CoTaskMemFree
0x1801237f6  jmp     loc_180123A29
0x1801237fb  lea     rcx, [rbp+100h+ppIAudioMediaType]
0x1801237ff  mov     [rbp+100h+ppIAudioMediaType], rdi
0x180123803  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180123808  mov     rcx, [rbp+100h+pv]; pAudioFormat
0x18012380c  lea     r8, [rbp+100h+ppIAudioMediaType]; ppIAudioMediaType
0x180123810  movzx   edx, word ptr [rcx+10h]
0x180123814  add     edx, 12h; cbAudioFormatSize
0x180123817  call    CreateAudioMediaType
0x18012381c  mov     ebx, eax
0x18012381e  test    eax, eax
0x180123820  jns     short loc_180123848
0x180123822  mov     rcx, [rbp+108h]; this
0x180123829  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180123830  mov     r9d, eax; char *
0x180123833  mov     edx, 10A5h; void *
0x180123838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012383d  lea     rcx, [rbp+100h+ppIAudioMediaType]
0x180123841  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180123846  jmp     short loc_1801237DF
0x180123848  mov     rbx, [rbp+100h+var_120+8]
0x18012384c  lea     rcx, [rbp+100h+var_150]
0x180123850  mov     [rbp+100h+var_150], rdi
0x180123854  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180123859  movaps  xmm8, xmmword ptr [rbp+100h+var_B0.Data1]
0x18012385e  lea     rax, [rbp+100h+var_150]
0x180123862  mov     r9, [rbp+100h+ppIAudioMediaType]; struct IAudioMediaType *
0x180123866  lea     rdx, [rbp+100h+var_B0]; struct _GUID
0x18012386a  mov     r8d, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18012386e  mov     rcx, rbx; this
0x180123871  mov     qword ptr [rsp+200h+pftDueTime.dwLowDateTime], rax; int
0x180123876  movdqa  xmmword ptr [rbp+100h+var_B0.Data1], xmm8
0x18012387c  call    ?DeriveStreamFormatFromMixFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@@Z; EffectPack::DeriveStreamFormatFromMixFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *)
0x180123881  mov     ebx, eax
0x180123883  test    eax, eax
0x180123885  jns     short loc_1801238AD
0x180123887  mov     edx, 10A8h; void *
0x18012388c  mov     r9d, eax; char *
0x18012388f  mov     rcx, [rbp+108h]; this
0x180123896  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18012389d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801238a2  lea     rcx, [rbp+100h+var_150]
0x1801238a6  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801238ab  jmp     short loc_18012383D
0x1801238ad  mov     rcx, [rbp+100h+var_150]
0x1801238b1  lea     rax, [rbp+100h+Src]
0x1801238b5  mov     qword ptr [rbp+100h+var_F0.Data1], rax
0x1801238b9  mov     qword ptr [rbp+100h+var_F0.Data4], rdi
0x1801238bd  mov     [rbp+100h+var_E0], 1
0x1801238c1  mov     rax, [rcx]
0x1801238c4  mov     rax, [rax+28h]
0x1801238c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801238cd  lea     rdx, [rbp+100h+var_F0.Data4]; struct tWAVEFORMATEX **
0x1801238d1  mov     rcx, rax; Src
0x1801238d4  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x1801238d9  lea     rcx, [rbp+100h+var_F0]
0x1801238dd  mov     ebx, eax
0x1801238df  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801238e4  test    ebx, ebx
0x1801238e6  jns     short loc_1801238F2
0x1801238e8  mov     r9d, ebx
0x1801238eb  mov     edx, 10AAh
0x1801238f0  jmp     short loc_18012388F
0x1801238f2  mov     r8, [rbp+100h+pv]; Src
0x1801238f6  lea     rax, [rbp+100h+pAudioFormat]
0x1801238fa  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801238fd  lea     r9, [rbp+100h+var_F0]; struct _GUID
0x180123901  mov     [rbp+100h+var_D0], rax
0x180123905  lea     rcx, [rbp+100h+var_120]; struct EndpointCharacteristicsDescriptor *
0x180123909  lea     rax, [rbp+100h+var_D0+8]
0x18012390d  mov     [rbp+100h+var_D0+8], rdi
0x180123911  mov     [rsp+200h+var_1C8], rax; struct tWAVEFORMATEX **
0x180123916  mov     eax, [rsi+44h]
0x180123919  mov     [rsp+200h+var_1D0], eax; int
0x18012391d  lea     rax, [rbp+100h+var_B0]
0x180123921  mov     [rsp+200h+var_1D8], rax; struct _GUID *
0x180123926  lea     rax, [rbp+100h+var_100]
  ... truncated ...
```
