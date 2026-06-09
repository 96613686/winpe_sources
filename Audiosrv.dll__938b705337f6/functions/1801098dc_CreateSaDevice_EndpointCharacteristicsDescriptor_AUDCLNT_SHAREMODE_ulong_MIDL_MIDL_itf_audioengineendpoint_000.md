# CreateSaDevice(EndpointCharacteristicsDescriptor *,_AUDCLNT_SHAREMODE,ulong,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,_GUID,__int64,__int64,tWAVEFORMATEX const *,tWAVEFORMATEX const *,_GUID,_GUID const *,_GUID const *,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>> const &,IAudioDeviceGraph * *)

- ea: `0x1801098dc`
- end: `0x18010a8e5`
- name: `?CreateSaDevice@@YAJPEAUEndpointCharacteristicsDescriptor@@W4_AUDCLNT_SHAREMODE@@KW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@3_J4PEBUtWAVEFORMATEX@@53PEBU4@6AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUIAudioDeviceGraph@@@Z`
- size: `4105`
- prototype: `__int64 __fastcall(int, int, int, int, void *Buf1, __int64, __int64, __int64, __int64, __int64, __int64, void *, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010d8b8`

## callees

- `0x180001d90`
- `0x180003518`
- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001c29c`
- `0x18001c5bc`
- `0x18001e850`
- `0x1800200e8`
- `0x180020160`
- `0x180020598`
- `0x180020bdc`
- `0x180020d68`
- `0x180020f74`
- `0x180022e20`
- `0x180022fb0`
- `0x18002c360`
- `0x1800393b0`
- `0x180039db0`
- `0x1800423cc`
- `0x1800626c8`
- `0x180068bd8`
- `0x18006b0e4`
- `0x18007254c`
- `0x180073310`
- `0x1800a5600`
- `0x1800b5964`
- `0x1800b724c`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x1800d0764`
- `0x180108454`
- `0x18010850c`
- `0x180108670`
- `0x1801087c4`
- `0x1801098dc`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180109eb5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180109f3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180109f73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180109eb5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180109f3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180109f73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180109e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180109e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180109e1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180109f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a87b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180109e1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180109f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a87b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18010a066`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18010a066`

## string_xrefs

- `0x180109a21`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109c65`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109e3b`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109ed4`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109fbf`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109ffc`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a29d`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a541`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a7ef`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109e6a`: `SaDevice_CoCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall CreateSaDevice(
        CEndpointCharacteristics **a1,
        int a2,
        int a3,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a4,
        IID *Buf1,
        _OWORD *a6,
        __int64 a7,
        __int64 a8,
        struct tWAVEFORMATEX *a9,
        __int64 a10,
        _OWORD *a11,
        IID *a12,
        _OWORD *a13,
        __int64 a14,
        IUnknown **a15)
{
  _OWORD *v16; // r14
  IID *v17; // r13
  struct ICompositeSystemEffect *v18; // rdi
  struct ICompositeSystemEffect *v19; // rbx
  unsigned int v20; // esi
  BOOL v21; // r15d
  __int32 v22; // r9d
  __int32 v23; // r9d
  struct IVolumeProvider *v24; // r14
  __int64 (__fastcall *v25)(struct IVolumeProvider *, _QWORD, __int64 *); // rsi
  int v26; // eax
  unsigned int v27; // esi
  char v28; // al
  struct IAudioProcessingObject *v29; // rsi
  struct _GUID *v30; // rbx
  int v31; // edx
  struct IAudioProcessingObject *v32; // r14
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // edx
  int v36; // eax
  SIZE_T v37; // rbx
  void *v38; // rax
  struct AudioSrvTelemetryProvider *v39; // rax
  HRESULT ContainerProperty; // ebx
  __int64 v41; // rdx
  void *v42; // rcx
  __int64 v43; // rdx
  void *v44; // rcx
  __int64 v45; // rcx
  int v46; // edi
  IID *p_rclsid; // rax
  int v48; // ecx
  __int64 v49; // rdx
  _OWORD *v50; // rbx
  int v51; // edi
  __int64 v52; // rdx
  __int64 v53; // rdx
  int v54; // edi
  _DWORD *v55; // r8
  int v56; // r8d
  int v57; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v58; // edx
  int DeviceFormatAndSpatialSettings; // ebx
  struct ICompositeSystemEffect *v60; // rcx
  bool v61; // al
  _DWORD *v62; // r8
  int v63; // r8d
  int v64; // r9d
  void *v65; // rcx
  bool v66; // al
  __int64 AudioPumpDspResourceTokenFromTokenList; // rax
  __int64 v68; // rbx
  struct AudioSrvTelemetryProvider *v69; // rax
  int v70; // eax
  IUnknown *v71; // rax
  void *v72; // rcx
  struct IAudioSystemEffects2 **ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  struct IAudioSystemEffects2 **dwImpLevel; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v79; // [rsp+78h] [rbp-88h] BYREF
  char v80; // [rsp+80h] [rbp-80h] BYREF
  char v81; // [rsp+81h] [rbp-7Fh] BYREF
  char v82; // [rsp+82h] [rbp-7Eh] BYREF
  char v83; // [rsp+83h] [rbp-7Dh] BYREF
  LPVOID v84; // [rsp+88h] [rbp-78h] BYREF
  int v85; // [rsp+90h] [rbp-70h] BYREF
  CEndpointCharacteristics **v86; // [rsp+98h] [rbp-68h] BYREF
  IUnknown *pProxy; // [rsp+A0h] [rbp-60h] BYREF
  char v88; // [rsp+A8h] [rbp-58h] BYREF
  char v89; // [rsp+A9h] [rbp-57h] BYREF
  char v90; // [rsp+AAh] [rbp-56h] BYREF
  char v91[5]; // [rsp+ABh] [rbp-55h] BYREF
  struct ICompositeSystemEffect *v92; // [rsp+B0h] [rbp-50h] BYREF
  struct IAudioProcessingObject *v93; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v94; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v95; // [rsp+D0h] [rbp-30h]
  int v96; // [rsp+E0h] [rbp-20h] BYREF
  int v97; // [rsp+E4h] [rbp-1Ch] BYREF
  int v98; // [rsp+E8h] [rbp-18h] BYREF
  struct IAudioProcessingObject *v99; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v100; // [rsp+F8h] [rbp-8h] BYREF
  struct ICompositeSystemEffect *v101; // [rsp+100h] [rbp+0h] BYREF
  struct ICompositeSystemEffect *v102; // [rsp+108h] [rbp+8h] BYREF
  IID rclsid; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v104; // [rsp+120h] [rbp+20h]
  struct tWAVEFORMATEX *v105; // [rsp+130h] [rbp+30h] BYREF
  __int64 v106; // [rsp+138h] [rbp+38h] BYREF
  __int64 v107; // [rsp+140h] [rbp+40h] BYREF
  __int64 v108; // [rsp+148h] [rbp+48h] BYREF
  CEndpointCharacteristics ***v109; // [rsp+150h] [rbp+50h] BYREF
  struct SpatialAudioSettings *v110; // [rsp+158h] [rbp+58h] BYREF
  void *p_pv; // [rsp+160h] [rbp+60h]
  IID *v112; // [rsp+168h] [rbp+68h]
  __int64 *v113; // [rsp+170h] [rbp+70h]
  char *v114; // [rsp+178h] [rbp+78h]
  _QWORD v115[2]; // [rsp+180h] [rbp+80h] BYREF
  IUnknown **v116; // [rsp+190h] [rbp+90h]
  LARGE_INTEGER PerformanceCount; // [rsp+1A0h] [rbp+A0h] BYREF
  LARGE_INTEGER v118; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v98 = a3;
  v86 = a1;
  v79 = a4;
  v16 = a6;
  *(_QWORD *)&rclsid.Data1 = a6;
  v105 = a9;
  v17 = a12;
  v115[0] = a14;
  v116 = a15;
  v83 = 0;
  v82 = 0;
  v81 = 0;
  v80 = 0;
  v18 = 0;
  v102 = 0;
  v19 = 0;
  v101 = 0;
  v108 = 0;
  v97 = 0;
  v107 = 0;
  v96 = 0;
  v20 = 0;
  v100 = 0;
  if ( ((a4 - 2) & 0xFFFFFFFD) != 0 )
  {
    v85 = (*(__int64 (__fastcall **)(CEndpointCharacteristics *))(*(_QWORD *)*a1 + 56LL))(*a1);
    a4 = v79;
  }
  else
  {
    v85 = 1;
  }
  v21 = 0;
  if ( (a4 == eHostProcessConnector || (v22 = a4 - 1) == 0 || (v23 = v22 - 1) == 0 || (unsigned int)(v23 - 1) <= 1)
    && !a2 )
  {
    v24 = g_pVolumeProvider;
    v25 = *(__int64 (__fastcall **)(struct IVolumeProvider *, _QWORD, __int64 *))(*(_QWORD *)g_pVolumeProvider + 40LL);
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v100);
    v26 = v25(v24, *((_QWORD *)*v86 + 6), &v100);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x981,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
        (const char *)(unsigned int)v26,
        (int)ppv);
      goto LABEL_144;
    }
    v83 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v100 + 224LL))(v100);
    v82 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v100 + 208LL))(v100);
    v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v100 + 216LL))(v100);
    if ( !(*(unsigned int (__fastcall **)(struct IAudioPolicyManager *))(*(_QWORD *)g_PolicyManager + 200LL))(g_PolicyManager)
      || (v28 = 1, v85) )
    {
      v28 = 0;
    }
    v80 = v28;
    if ( (v79 & 0xFFFFFFFC) == 0 && v79 != eLoopbackConnector )
    {
      if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v86[1], v79) )
      {
        v29 = 0;
        v99 = 0;
        v93 = 0;
        v30 = *(struct _GUID **)&rclsid.Data1;
        v94 = *(struct _GUID *)*(_QWORD *)&rclsid.Data1;
        if ( !EffectPack::CanProcessingModeBeParameterized(v86[1], &v94, v79)
          && (memcmp_0(Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u)
           || !(unsigned int)EffectPack::CanBuildProcessingModesOnRawConnector(v86[1], (unsigned int)v79, 0)
           || v79 == eOffloadConnector) )
        {
          v99 = 0;
          v102 = 0;
          v94 = *v30;
          EffectPack::GetModeEffect(v86[1], &v94, 0, v79, &v102, &v99, 0);
          v18 = v102;
          v29 = v99;
        }
        v93 = 0;
        v101 = 0;
        EffectPack::GetEndpointEffect(v86[1], 0, v79, &v101, &v93, 0);
        if ( memcmp_0(Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u) || v79 )
        {
          v19 = v101;
        }
        else
        {
          *(_QWORD *)&v94.Data1 = 0;
          v92 = 0;
          EffectPack::GetRawModePostMixEffect(
            v86[1],
            v31,
            eHostProcessConnector,
            &v92,
            (struct IAudioProcessingObject **)&v94,
            dwImpLevel);
          v19 = v92;
          if ( v92 )
          {
            if ( v101 )
            {
              v27 = -2147418113;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9BB,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
                (const char *)0x8000FFFFLL,
                (int)ppv);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v92);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v94);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v93);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v99);
              goto LABEL_144;
            }
            v101 = v92;
            (*(void (__fastcall **)(struct ICompositeSystemEffect *))(*(_QWORD *)v92 + 8LL))(v92);
            v32 = v93;
            v93 = *(struct IAudioProcessingObject **)&v94.Data1;
            if ( *(_QWORD *)&v94.Data1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v94.Data1 + 8LL))(*(_QWORD *)&v94.Data1);
            if ( v32 )
              ((void (__fastcall *)(struct IAudioProcessingObject *))v32->lpVtbl->Release)(v32);
          }
          else
          {
            v19 = v101;
          }
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v92);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v94);
        }
        if ( IsFixedFormatApo(v29) || (v21 = 0, IsFixedFormatApo(v93)) )
          v21 = 1;
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v93);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v99);
      }
      else
      {
        *(_QWORD *)&v94.Data1 = 0;
        v102 = 0;
        EffectPack::GetGfx(v86[1], v79, &v102, (struct IAudioProcessingObject **)&v94, ppv);
        v21 = IsFixedFormatApo(*(struct IAudioProcessingObject **)&v94.Data1);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v94);
        v18 = v102;
      }
      if ( v18 )
      {
        v33 = *(_QWORD *)v18;
        *(_QWORD *)&v94.Data1 = &v108;
        *(_QWORD *)v94.Data4 = 0;
        LOBYTE(v95) = 1;
        (*(void (__fastcall **)(struct ICompositeSystemEffect *, int *, unsigned __int8 *))(v33 + 32))(
          v18,
          &v97,
          v94.Data4);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v94);
      }
      if ( v19 )
      {
        v34 = *(_QWORD *)v19;
        *(_QWORD *)&v94.Data1 = &v107;
        *(_QWORD *)v94.Data4 = 0;
        LOBYTE(v95) = 1;
        (*(void (__fastcall **)(struct ICompositeSystemEffect *, int *, unsigned __int8 *))(v34 + 32))(
          v19,
          &v96,
          v94.Data4);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v94);
      }
    }
    if ( v83 || (v35 = 0, v82) )
      v35 = 1;
    v20 = v97 + v96 + v35 + (v80 != 0) + (v81 != 0);
    v16 = *(_OWORD **)&rclsid.Data1;
  }
  pv = 0;
  v36 = v20;
  if ( !v20 )
    v36 = 1;
  v37 = 16 * v36 + 216;
  v38 = CoTaskMemAlloc(v37);
  pv = v38;
  if ( !v38 )
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D9,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
LABEL_70:
    v44 = pv;
    pv = 0;
    goto LABEL_71;
  }
  memset_0(v38, 0, v37);
  v84 = 0;
  v39 = AudioSrvTelemetryProvider::Instance();
  CPerfTracker::CPerfTracker(&PerformanceCount, *((const struct _tlgProvider_t **)v39 + 1), "SaDevice_CoCreate", 0);
  if ( a2 == 1 )
  {
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v84);
    ContainerProperty = CoCreateInstance(
                          &GUID_75269c13_41e1_4d0e_b8a0_9f8f22e246c9,
                          0,
                          0x17u,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v84);
    if ( ContainerProperty < 0 )
    {
      v41 = 2542;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
        (const char *)(unsigned int)ContainerProperty,
        ppva);
      CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
LABEL_56:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
      v42 = pv;
      pv = 0;
LABEL_57:
      if ( v42 )
        CoTaskMemFree(v42);
      v27 = ContainerProperty;
      goto LABEL_144;
    }
  }
  else if ( v79 == eOffloadConnector )
  {
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v84);
    ContainerProperty = CoCreateInstance(
                          &GUID_c994009c_34d3_4c9d_90ae_8dd53f521058,
                          0,
                          0x17u,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v84);
    if ( ContainerProperty < 0 )
    {
      v41 = 2548;
      goto LABEL_55;
    }
  }
  else
  {
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v84);
    ContainerProperty = CoCreateInstance(
                          &GUID_89115307_8248_448f_ada0_f3f3718a9b2a,
                          0,
                          0x17u,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v84);
    if ( ContainerProperty < 0 )
    {
      v41 = 2552;
      goto LABEL_55;
    }
  }
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  pProxy = 0;
  ContainerProperty = (**(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))v84)(
                        v84,
                        &GUID_359f1fc4_4a4b_42d0_b75d_a021af7de2ee,
                        &pProxy);
  if ( ContainerProperty < 0 )
  {
    v43 = 2559;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
      (const char *)(unsigned int)ContainerProperty,
      ppva);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
    goto LABEL_56;
  }
  if ( !pProxy )
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA00,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
      (const char *)0x8007000ELL,
      ppva);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
    goto LABEL_70;
  }
  ContainerProperty = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 3u, 0, 0x40u);
  if ( ContainerProperty < 0 )
  {
    v43 = 2566;
    goto LABEL_67;
  }
  *((_QWORD *)pv + 1) = v105;
  *(_DWORD *)pv = v105->cbSize + 18;
  v45 = a10;
  if ( a10 )
  {
    *((_QWORD *)pv + 3) = a10;
    *((_DWORD *)pv + 4) = *(unsigned __int16 *)(v45 + 16) + 18;
  }
  else
  {
    *((_QWORD *)pv + 3) = 0;
    *((_DWORD *)pv + 4) = 0;
  }
  v46 = v85;
  *((_DWORD *)pv + 18) = v85;
  *((_QWORD *)pv + 7) = *((_QWORD *)*v86 + 6);
  *((_QWORD *)pv + 4) = a7;
  *((_QWORD *)pv + 5) = a8;
  *((_DWORD *)pv + 24) = 0;
  *((_DWORD *)pv + 20) = 0;
  *((_DWORD *)pv + 19) = v98;
  *((_DWORD *)pv + 25) = v79;
  *((_DWORD *)pv + 22) = -1;
  *((_DWORD *)pv + 23) = 0;
  *((_DWORD *)pv + 21) = -1;
  if ( ((v79 - 2) & 0xFFFFFFFD) != 0 && (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v86[1], v79) )
  {
    rclsid = *Buf1;
    p_rclsid = EffectPack::TranslateDeviceConnectorModeToStreamingConnectorMode(v86[1], &v94, v79, &rclsid);
  }
  else
  {
    rclsid = GUID_00000000_0000_0000_0000_000000000000;
    p_rclsid = &rclsid;
  }
  *(IID *)((char *)pv + 104) = *p_rclsid;
  *(_OWORD *)((char *)pv + 120) = *v16;
  *((_DWORD *)pv + 34) = CEndpointCharacteristics::HasHardwareAudioEngine(*v86);
  *((_DWORD *)pv + 12) = *((_DWORD *)*v86 + 58);
  if ( !(unsigned int)CEndpointCharacteristics::AreEnhancementsEnabled(*v86) || (v48 = 0, a2 == 1) )
    v48 = 1;
  *((_DWORD *)pv + 35) = v48;
  *(_OWORD *)((char *)pv + 148) = *a11;
  *((_DWORD *)pv + 36) = v21;
  if ( v17 )
  {
    if ( memcmp_0(v17, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    {
      rclsid = *v17;
      ContainerProperty = GetContainerProperty(&rclsid, &PKEY_Audio_CPEventManager, (struct _GUID *)((char *)pv + 164));
      if ( ContainerProperty < 0 )
      {
        v49 = 2614;
LABEL_89:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v49,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
          (const char *)(unsigned int)ContainerProperty,
          ppva);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
        v42 = pv;
        pv = 0;
        goto LABEL_57;
      }
    }
  }
  v50 = a13;
  if ( a13 && memcmp_0(a13, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    *(_OWORD *)((char *)pv + 180) = *v50;
  v109 = (CEndpointCharacteristics ***)&v79;
  v110 = (struct SpatialAudioSettings *)&v81;
  p_pv = &pv;
  v112 = (IID *)&v83;
  v113 = (__int64 *)&v82;
  v114 = &v80;
  *(_QWORD *)&v94.Data1 = &v97;
  *(_QWORD *)v94.Data4 = &pv;
  v95 = &v108;
  *(_QWORD *)&rclsid.Data1 = &v96;
  *(_QWORD *)rclsid.Data4 = &pv;
  v104 = &v107;
  if ( (v79 & 0xFFFFFFFC) == 0 && v79 != eLoopbackConnector )
  {
    if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v86[1], v79) )
    {
      ContainerProperty = lambda_4d47e4b1195443ce5ef14f7026d1d081_::operator()(&v94, 0);
      if ( ContainerProperty < 0 )
      {
        v49 = 2681;
        goto LABEL_89;
      }
      v51 = ValidateUncompressedWaveFormatEx(v105);
      if ( !v51 )
      {
        ContainerProperty = lambda_3f48f908354d0a377503ef9be61a0c4e_::operator()(&rclsid, 0);
        if ( ContainerProperty < 0 )
        {
          v49 = 2686;
          goto LABEL_89;
        }
      }
      lambda_c327f0ba139a0c7bdef6b59ff99923d9_::operator()(&v109);
      if ( v51 == 1 )
      {
        LOBYTE(v52) = 1;
        ContainerProperty = lambda_3f48f908354d0a377503ef9be61a0c4e_::operator()(&rclsid, v52);
        if ( ContainerProperty < 0 )
        {
          v49 = 2695;
          goto LABEL_89;
        }
      }
    }
    else
    {
      v54 = ValidateUncompressedWaveFormatEx(v105);
      if ( v54 == 1 )
        lambda_c327f0ba139a0c7bdef6b59ff99923d9_::operator()(&v109);
      LOBYTE(v53) = v54 == 1;
      ContainerProperty = lambda_4d47e4b1195443ce5ef14f7026d1d081_::operator()(&v94, v53);
      if ( ContainerProperty < 0 )
      {
        v49 = 2721;
        goto LABEL_89;
      }
      if ( !v54 )
        lambda_c327f0ba139a0c7bdef6b59ff99923d9_::operator()(&v109);
    }
    v46 = v85;
  }
  if ( *((_DWORD *)pv + 24) > v20 )
  {
    v55 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v55 > 2u && (unsigned __int8)tlgKeywordOn(v55, 0x400000000400LL) )
    {
      v98 = *((_DWORD *)pv + 24);
      v85 = v96;
      LODWORD(v92) = v97;
      v88 = v80;
      v89 = v81;
      v90 = v82;
      v91[0] = v83;
      LODWORD(v99) = a2;
      LODWORD(v93) = v79;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v56,
        (unsigned int)&unk_1801A48FD,
        v56,
        v57,
        (__int64)&v93,
        (__int64)&v99,
        (__int64)v91,
        (__int64)&v90,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)&v98);
    }
    v27 = -2005139341;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xABC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
      (const char *)0x887C0073LL,
      ppva);
    goto LABEL_116;
  }
  v109 = &v86;
  v110 = (struct SpatialAudioSettings *)&v79;
  p_pv = &v105;
  v112 = Buf1;
  v113 = &a7;
  *(GUID *)((char *)pv + 196) = GUID_00000000_0000_0000_0000_000000000000;
  if ( !v46 )
  {
    v58 = v79;
    if ( ((v79 - 2) & 0xFFFFFFFD) != 0 )
    {
      if ( g_DisableSpatialOnLowLatency )
      {
        if ( (unsigned __int8)lambda_9bf885da0abb1dc890da24065742d1f0_::operator()(&v109) )
          goto LABEL_136;
        v58 = v79;
      }
      *(_QWORD *)&v94.Data1 = 0;
      v92 = 0;
      v109 = (CEndpointCharacteristics ***)&v92;
      v110 = 0;
      LOBYTE(p_pv) = 1;
      *(_QWORD *)&rclsid.Data1 = &v94;
      *(_QWORD *)rclsid.Data4 = 0;
      LOBYTE(v104) = 1;
      DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                         v86[1],
                                         v58,
                                         0,
                                         (struct tWAVEFORMATEX **)rclsid.Data4,
                                         &v110,
                                         0,
                                         0);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&rclsid);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v109);
      if ( DeviceFormatAndSpatialSettings < 0 )
      {
        v62 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *v62 > 3u && (unsigned __int8)tlgKeywordOn(v62, 1024) )
        {
          LODWORD(v93) = a2;
          LODWORD(v99) = v79;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v63,
            (unsigned int)&unk_1801A48A2,
            v63,
            v64,
            (__int64)&v99,
            (__int64)&v93);
        }
      }
      else
      {
        v60 = v92;
        if ( !*(_DWORD *)v92 )
          goto LABEL_132;
        v61 = IsCompressedSpatialFormat(v105);
        v60 = v92;
        if ( !v61
          && (*(_OWORD *)((char *)v92 + 12) == DOLBY_ATMOS_MAT_SPATIAL_ENCODER
           || *(_OWORD *)((char *)v92 + 12) == DTSX_HDMI_SPATIAL_ENCODER) )
        {
          goto LABEL_132;
        }
        *(_OWORD *)((char *)pv + 196) = *(_OWORD *)((char *)v92 + 12);
      }
      v60 = v92;
LABEL_132:
      v92 = 0;
      if ( v60 )
        CoTaskMemFree(v60);
      v65 = *(void **)&v94.Data1;
      *(_QWORD *)&v94.Data1 = 0;
      if ( v65 )
        CoTaskMemFree(v65);
    }
  }
LABEL_136:
  v66 = CEndpointCharacteristics::DisablePumpBackupTimer(*v86);
  *((_DWORD *)pv + 53) = v66;
  v106 = 0;
  if ( v100 )
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v100)(v100, &GUID_2f732065_eff0_4c7c_8fc1_363851b1f1d7, &v106);
  else
    v106 = 0;
  AudioPumpDspResourceTokenFromTokenList = TryGetAudioPumpDspResourceTokenFromTokenList(v115, v115[0]);
  v68 = *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8);
  *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8) = 0;
  *(_QWORD *)&rclsid.Data1 = v68;
  AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair((AudioPumpDspResourceTokenPair *)v115);
  v69 = AudioSrvTelemetryProvider::Instance();
  CPerfTracker::CPerfTracker(&v118, *((const struct _tlgProvider_t **)v69 + 1), "SaDevice_Initialize", 0);
  ppvb = v98;
  v70 = ((__int64 (__fastcall *)(IUnknown *, LPVOID, __int64, __int64))pProxy->lpVtbl[1].QueryInterface)(
          pProxy,
          pv,
          v68,
          v106);
  v27 = v70;
  if ( v70 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB05,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
      (const char *)(unsigned int)v70,
      ppvb);
    CPerfTracker::~CPerfTracker((CPerfTracker *)&v118);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&rclsid);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v106);
LABEL_116:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
    v44 = pv;
    pv = 0;
LABEL_71:
    if ( v44 )
      CoTaskMemFree(v44);
    goto LABEL_144;
  }
  CPerfTracker::~CPerfTracker((CPerfTracker *)&v118);
  v71 = pProxy;
  pProxy = 0;
  *v116 = v71;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&rclsid);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v106);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v84);
  v72 = pv;
  pv = 0;
  if ( v72 )
    CoTaskMemFree(v72);
  v27 = 0;
LABEL_144:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v100);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v107, 0);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v108, 0);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v101);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v102);
  return v27;
}

```

## disassembly

```asm
0x1801098dc  mov     [rsp-8+arg_8], rbx
0x1801098e1  push    rbp
0x1801098e2  push    rsi
0x1801098e3  push    rdi
0x1801098e4  push    r12
0x1801098e6  push    r13
0x1801098e8  push    r14
0x1801098ea  push    r15
0x1801098ec  lea     rbp, [rsp-290h]
0x1801098f4  sub     rsp, 390h
0x1801098fb  mov     rax, cs:__security_cookie
0x180109902  xor     rax, rsp
0x180109905  mov     [rbp+2C0h+var_40], rax
0x18010990c  mov     [rbp+2C0h+var_2D8], r8d
0x180109910  mov     r12d, edx
0x180109913  mov     [rbp+2C0h+var_328], rcx
0x180109917  mov     [rsp+3C0h+var_348], r9d
0x18010991c  mov     r14, [rbp+2C0h+arg_28]
0x180109923  mov     qword ptr [rbp+2C0h+rclsid.Data1], r14
0x180109927  mov     rax, [rbp+2C0h+arg_40]
0x18010992e  mov     [rbp+2C0h+var_290], rax
0x180109932  mov     r13, [rbp+2C0h+arg_58]
0x180109939  mov     rax, [rbp+2C0h+arg_68]
0x180109940  mov     [rbp+2C0h+var_240], rax
0x180109947  mov     rax, [rbp+2C0h+arg_70]
0x18010994e  mov     [rbp+2C0h+var_230], rax
0x180109955  xor     edx, edx
0x180109957  mov     [rbp+2C0h+var_33D], dl
0x18010995a  mov     [rbp+2C0h+var_33E], dl
0x18010995d  mov     [rbp+2C0h+var_33F], dl
0x180109960  mov     [rbp+2C0h+var_340], dl
0x180109963  mov     edi, edx
0x180109965  mov     [rbp+2C0h+var_2B8], rdx
0x180109969  mov     ebx, edx
0x18010996b  mov     [rbp+2C0h+var_2C0], rdx
0x18010996f  mov     [rbp+2C0h+var_278], rdx
0x180109973  mov     [rbp+2C0h+var_2DC], edx
0x180109976  mov     [rbp+2C0h+var_280], rdx
0x18010997a  mov     [rbp+2C0h+var_2E0], edx
0x18010997d  mov     esi, edx
0x18010997f  mov     [rbp+2C0h+var_2C8], rdx
0x180109983  lea     eax, [r9-2]
0x180109987  test    eax, 0FFFFFFFDh
0x18010998c  jz      short loc_1801099A9
0x18010998e  mov     rcx, [rcx]
0x180109991  mov     rax, [rcx]
0x180109994  mov     rax, [rax+38h]
0x180109998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010999d  mov     [rbp+2C0h+var_330], eax
0x1801099a0  mov     r9d, [rsp+3C0h+var_348]
0x1801099a5  xor     edx, edx
0x1801099a7  jmp     short loc_1801099B0
0x1801099a9  mov     [rbp+2C0h+var_330], 1
0x1801099b0  mov     r15d, edx
0x1801099b3  test    r9d, r9d
0x1801099b6  jz      short loc_1801099D4
0x1801099b8  sub     r9d, 1
0x1801099bc  jz      short loc_1801099D4
0x1801099be  sub     r9d, 1
0x1801099c2  jz      short loc_1801099D4
0x1801099c4  sub     r9d, 1
0x1801099c8  jz      short loc_1801099D4
0x1801099ca  cmp     r9d, 1
0x1801099ce  jnz     loc_180109DE8
0x1801099d4  test    r12d, r12d
0x1801099d7  jnz     loc_180109DE8
0x1801099dd  mov     r14, cs:?g_pVolumeProvider@@3PEAUIVolumeProvider@@EA; IVolumeProvider * g_pVolumeProvider
0x1801099e4  mov     rax, [r14]
0x1801099e7  mov     rsi, [rax+28h]
0x1801099eb  lea     rcx, [rbp+2C0h+var_2C8]
0x1801099ef  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1801099f4  mov     rdx, [rbp+2C0h+var_328]
0x1801099f8  mov     rdx, [rdx]
0x1801099fb  lea     r8, [rbp+2C0h+var_2C8]
0x1801099ff  mov     rdx, [rdx+30h]
0x180109a03  mov     rcx, r14
0x180109a06  mov     rax, rsi
0x180109a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a0e  mov     esi, eax
0x180109a10  xor     r14d, r14d
0x180109a13  test    eax, eax
0x180109a15  jns     short loc_180109A37
0x180109a17  mov     rcx, [rbp+2C8h]; this
0x180109a1e  mov     r9d, eax; char *
0x180109a21  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180109a28  mov     edx, 981h; void *
0x180109a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109a32  jmp     loc_18010A884
0x180109a37  mov     rcx, [rbp+2C0h+var_2C8]
0x180109a3b  mov     rax, [rcx]
0x180109a3e  mov     rax, [rax+0E0h]
0x180109a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a4a  mov     [rbp+2C0h+var_33D], al
0x180109a4d  mov     rcx, [rbp+2C0h+var_2C8]
0x180109a51  mov     rax, [rcx]
0x180109a54  mov     rax, [rax+0D0h]
0x180109a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a60  mov     [rbp+2C0h+var_33E], al
0x180109a63  mov     rcx, [rbp+2C0h+var_2C8]
0x180109a67  mov     rax, [rcx]
0x180109a6a  mov     rax, [rax+0D8h]
0x180109a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a76  mov     [rbp+2C0h+var_33F], al
0x180109a79  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x180109a80  mov     rax, [rcx]
0x180109a83  mov     rax, [rax+0C8h]
0x180109a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a8f  test    eax, eax
0x180109a91  jz      short loc_180109A9B
0x180109a93  cmp     [rbp+2C0h+var_330], r14d
0x180109a97  mov     al, 1
0x180109a99  jz      short loc_180109A9E
0x180109a9b  mov     al, r14b
0x180109a9e  mov     [rbp+2C0h+var_340], al
0x180109aa1  mov     edx, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109aa5  test    edx, 0FFFFFFFCh
0x180109aab  jnz     loc_180109DB1
0x180109ab1  cmp     edx, 2
0x180109ab4  jz      loc_180109DB1
0x180109aba  mov     rcx, [rbp+2C0h+var_328]
0x180109abe  mov     rcx, [rcx+8]; this
0x180109ac2  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x180109ac7  test    eax, eax
0x180109ac9  jnz     short loc_180109B0B
0x180109acb  mov     rax, [rbp+2C0h+var_328]
0x180109acf  mov     qword ptr [rbp+2C0h+var_300.Data1], r14
0x180109ad3  mov     [rbp+2C0h+var_2B8], r14
0x180109ad7  lea     r9, [rbp+2C0h+var_300]; struct IAudioProcessingObject **
0x180109adb  lea     r8, [rbp+2C0h+var_2B8]; struct ICompositeSystemEffect **
0x180109adf  mov     edx, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109ae3  mov     rcx, [rax+8]; this
0x180109ae7  call    ?GetGfx@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetGfx(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109aec  mov     rcx, qword ptr [rbp+2C0h+var_300.Data1]; struct IAudioProcessingObject *
0x180109af0  call    ?IsFixedFormatApo@@YA_NPEAUIAudioProcessingObject@@@Z; IsFixedFormatApo(IAudioProcessingObject *)
0x180109af5  movzx   r15d, al
0x180109af9  lea     rcx, [rbp+2C0h+var_300]
0x180109afd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109b02  mov     rdi, [rbp+2C0h+var_2B8]
0x180109b06  jmp     loc_180109D45
0x180109b0b  mov     rsi, r14
0x180109b0e  mov     [rbp+2C0h+var_2D0], r14
0x180109b12  mov     [rbp+2C0h+var_308], r14
0x180109b16  mov     rbx, qword ptr [rbp+2C0h+rclsid.Data1]
0x180109b1a  movups  xmm0, xmmword ptr [rbx]
0x180109b1d  movdqu  xmmword ptr [rbp+2C0h+var_300.Data1], xmm0
0x180109b22  mov     r8d, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109b27  lea     rdx, [rbp+2C0h+var_300]; struct _GUID
0x180109b2b  mov     rcx, [rbp+2C0h+var_328]
0x180109b2f  mov     rcx, [rcx+8]; this
0x180109b33  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x180109b38  test    al, al
0x180109b3a  jnz     loc_180109BC4
0x180109b40  mov     r8d, 10h; Size
0x180109b46  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x180109b4d  mov     rcx, [rbp+2C0h+Buf1]; Buf1
0x180109b54  call    memcmp_0
0x180109b59  test    eax, eax
0x180109b5b  jnz     short loc_180109B7C
0x180109b5d  xor     r8d, r8d
0x180109b60  mov     edx, [rsp+3C0h+var_348]
0x180109b64  mov     rcx, [rbp+2C0h+var_328]
0x180109b68  mov     rcx, [rcx+8]
0x180109b6c  call    ?CanBuildProcessingModesOnRawConnector@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@@Z; EffectPack::CanBuildProcessingModesOnRawConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration)
0x180109b71  test    eax, eax
0x180109b73  jz      short loc_180109B7C
0x180109b75  cmp     [rsp+3C0h+var_348], 1
0x180109b7a  jnz     short loc_180109BC4
0x180109b7c  mov     rax, [rbp+2C0h+var_328]
0x180109b80  mov     [rbp+2C0h+var_2D0], r14
0x180109b84  mov     [rbp+2C0h+var_2B8], r14
0x180109b88  movups  xmm0, xmmword ptr [rbx]
0x180109b8b  movdqu  xmmword ptr [rbp+2C0h+var_300.Data1], xmm0
0x180109b90  mov     [rsp+3C0h+pAuthInfo], r14; struct IAudioSystemEffects2 **
0x180109b95  lea     rcx, [rbp+2C0h+var_2D0]
0x180109b99  mov     qword ptr [rsp+3C0h+dwImpLevel], rcx; struct IAudioProcessingObject **
0x180109b9e  lea     rcx, [rbp+2C0h+var_2B8]
0x180109ba2  mov     [rsp+3C0h+ppv], rcx; struct ICompositeSystemEffect **
0x180109ba7  mov     r9d, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109bac  xor     r8d, r8d; int
0x180109baf  lea     rdx, [rbp+2C0h+var_300]; struct _GUID *
0x180109bb3  mov     rcx, [rax+8]; this
0x180109bb7  call    ?GetModeEffect@EffectPack@@QEAAJU_GUID@@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetModeEffect(_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109bbc  mov     rdi, [rbp+2C0h+var_2B8]
0x180109bc0  mov     rsi, [rbp+2C0h+var_2D0]
0x180109bc4  mov     rax, [rbp+2C0h+var_328]
0x180109bc8  mov     [rbp+2C0h+var_308], r14
0x180109bcc  mov     [rbp+2C0h+var_2C0], r14
0x180109bd0  mov     qword ptr [rsp+3C0h+dwImpLevel], r14; struct IAudioSystemEffects2 **
0x180109bd5  lea     rcx, [rbp+2C0h+var_308]
0x180109bd9  mov     [rsp+3C0h+ppv], rcx; int
0x180109bde  lea     r9, [rbp+2C0h+var_2C0]; struct ICompositeSystemEffect **
0x180109be2  mov     r8d, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109be7  xor     edx, edx; int
0x180109be9  mov     rcx, [rax+8]; this
0x180109bed  call    ?GetEndpointEffect@EffectPack@@QEAAJHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetEndpointEffect(int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109bf2  mov     r8d, 10h; Size
0x180109bf8  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x180109bff  mov     rcx, [rbp+2C0h+Buf1]; Buf1
0x180109c06  call    memcmp_0
0x180109c0b  test    eax, eax
0x180109c0d  jnz     loc_180109D0C
0x180109c13  cmp     [rsp+3C0h+var_348], r14d
0x180109c18  jnz     loc_180109D0C
0x180109c1e  mov     rax, [rbp+2C0h+var_328]
0x180109c22  mov     qword ptr [rbp+2C0h+var_300.Data1], r14
0x180109c26  mov     [rbp+2C0h+var_310], r14
0x180109c2a  lea     rcx, [rbp+2C0h+var_300]
0x180109c2e  mov     [rsp+3C0h+ppv], rcx; int
0x180109c33  lea     r9, [rbp+2C0h+var_310]; struct ICompositeSystemEffect **
0x180109c37  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109c3a  mov     rcx, [rax+8]; this
0x180109c3e  call    ?GetRawModePostMixEffect@EffectPack@@QEAAJHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetRawModePostMixEffect(int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109c43  mov     rbx, [rbp+2C0h+var_310]
0x180109c47  test    rbx, rbx
0x180109c4a  jz      loc_180109CF3
0x180109c50  cmp     [rbp+2C0h+var_2C0], r14
0x180109c54  jz      short loc_180109CA3
0x180109c56  mov     rcx, [rbp+2C8h]; this
0x180109c5d  mov     esi, 8000FFFFh
0x180109c62  mov     r9d, esi; char *
0x180109c65  lea     r8, aAvcoreAudiocor_62; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180109c6c  mov     edx, 9BBh; void *
0x180109c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c76  nop
0x180109c77  lea     rcx, [rbp+2C0h+var_310]
0x180109c7b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109c80  nop
0x180109c81  lea     rcx, [rbp+2C0h+var_300]
0x180109c85  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109c8a  nop
0x180109c8b  lea     rcx, [rbp+2C0h+var_308]
0x180109c8f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109c94  nop
0x180109c95  lea     rcx, [rbp+2C0h+var_2D0]
0x180109c99  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109c9e  jmp     loc_18010A884
0x180109ca3  mov     [rbp+2C0h+var_2C0], rbx
0x180109ca7  test    rbx, rbx
0x180109caa  jz      short loc_180109CBC
0x180109cac  mov     rax, [rbx]
0x180109caf  mov     rcx, rbx
0x180109cb2  mov     rax, [rax+8]
0x180109cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cbb  nop
0x180109cbc  mov     rcx, qword ptr [rbp+2C0h+var_300.Data1]
0x180109cc0  mov     r14, [rbp+2C0h+var_308]
0x180109cc4  mov     [rbp+2C0h+var_308], rcx
0x180109cc8  test    rcx, rcx
0x180109ccb  jz      short loc_180109CD9
0x180109ccd  mov     rax, [rcx]
0x180109cd0  mov     rax, [rax+8]
0x180109cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cd9  test    r14, r14
0x180109cdc  jz      short loc_180109CEE
0x180109cde  mov     rax, [r14]
0x180109ce1  mov     rcx, r14
0x180109ce4  mov     rax, [rax+10h]
0x180109ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109ced  nop
0x180109cee  xor     r14d, r14d
0x180109cf1  jmp     short loc_180109CF7
0x180109cf3  mov     rbx, [rbp+2C0h+var_2C0]
0x180109cf7  lea     rcx, [rbp+2C0h+var_310]
0x180109cfb  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109d00  nop
0x180109d01  lea     rcx, [rbp+2C0h+var_300]
0x180109d05  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109d0a  jmp     short loc_180109D10
0x180109d0c  mov     rbx, [rbp+2C0h+var_2C0]
0x180109d10  mov     rcx, rsi; struct IAudioProcessingObject *
0x180109d13  call    ?IsFixedFormatApo@@YA_NPEAUIAudioProcessingObject@@@Z; IsFixedFormatApo(IAudioProcessingObject *)
0x180109d18  test    al, al
0x180109d1a  jnz     short loc_180109D2C
0x180109d1c  mov     rcx, [rbp+2C0h+var_308]; struct IAudioProcessingObject *
0x180109d20  call    ?IsFixedFormatApo@@YA_NPEAUIAudioProcessingObject@@@Z; IsFixedFormatApo(IAudioProcessingObject *)
0x180109d25  test    al, al
0x180109d27  mov     r15d, r14d
0x180109d2a  jz      short loc_180109D32
0x180109d2c  mov     r15d, 1
0x180109d32  lea     rcx, [rbp+2C0h+var_308]
0x180109d36  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109d3b  nop
0x180109d3c  lea     rcx, [rbp+2C0h+var_2D0]
0x180109d40  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109d45  test    rdi, rdi
0x180109d48  jz      short loc_180109D7B
0x180109d4a  mov     rax, [rdi]
0x180109d4d  lea     rcx, [rbp+2C0h+var_278]
0x180109d51  mov     qword ptr [rbp+2C0h+var_300.Data1], rcx
0x180109d55  mov     qword ptr [rbp+2C0h+var_300.Data4], r14
0x180109d59  mov     byte ptr [rbp+2C0h+var_2F0], 1
0x180109d5d  lea     r8, [rbp+2C0h+var_300.Data4]
0x180109d61  lea     rdx, [rbp+2C0h+var_2DC]
0x180109d65  mov     rcx, rdi
0x180109d68  mov     rax, [rax+20h]
0x180109d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d71  nop
0x180109d72  lea     rcx, [rbp+2C0h+var_300]
0x180109d76  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180109d7b  test    rbx, rbx
  ... truncated ...
```
