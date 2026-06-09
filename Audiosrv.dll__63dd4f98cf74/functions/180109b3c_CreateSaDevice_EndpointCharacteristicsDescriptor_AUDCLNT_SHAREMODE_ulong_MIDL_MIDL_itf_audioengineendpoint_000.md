# CreateSaDevice(EndpointCharacteristicsDescriptor *,_AUDCLNT_SHAREMODE,ulong,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,_GUID,__int64,__int64,tWAVEFORMATEX const *,tWAVEFORMATEX const *,_GUID,_GUID const *,_GUID const *,std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>> const &,IAudioDeviceGraph * *)

- ea: `0x180109b3c`
- end: `0x18010ab45`
- name: `?CreateSaDevice@@YAJPEAUEndpointCharacteristicsDescriptor@@W4_AUDCLNT_SHAREMODE@@KW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@3_J4PEBUtWAVEFORMATEX@@53PEBU4@6AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUIAudioDeviceGraph@@@Z`
- size: `4105`
- prototype: `__int64 __fastcall(CEndpointCharacteristics **, int, int, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, IID *Buf1, _OWORD *, __int64, __int64, struct tWAVEFORMATEX *, __int64, _OWORD *, IID *, _OWORD *, __int64, IUnknown **)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010db68`

## callees

- `0x180001d90`
- `0x180003724`
- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x18001b520`
- `0x18001c3ec`
- `0x18001c70c`
- `0x18001e9a0`
- `0x180020238`
- `0x1800202b0`
- `0x1800206e8`
- `0x180020d2c`
- `0x180020eb8`
- `0x1800210c4`
- `0x180022f70`
- `0x180023100`
- `0x18002c4c0`
- `0x180039510`
- `0x180039f10`
- `0x1800424ec`
- `0x180062238`
- `0x180068748`
- `0x18006ac54`
- `0x18007204c`
- `0x180072e10`
- `0x1800a4da0`
- `0x1800b3c74`
- `0x1800b571c`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x1800ce774`
- `0x1801086b4`
- `0x18010876c`
- `0x1801088d0`
- `0x180108a24`
- `0x180109b3c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010a115`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010a19b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010a1d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010a115`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010a19b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010a1d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010a067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010a067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a07c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010aadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a07c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010a988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010aadb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18010a2c6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18010a2c6`

## string_xrefs

- `0x180109c81`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x180109ec5`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a09b`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a134`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a21f`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a25c`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a4fd`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a7a1`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010aa4f`: `avcore\audiocore\server\audiosrv\dll\devicegraphmanagement.cpp`
- `0x18010a0ca`: `SaDevice_CoCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
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
  __int64 v40; // rdx
  HRESULT ContainerProperty; // ebx
  __int64 v42; // rdx
  void *v43; // rcx
  __int64 v44; // rdx
  void *v45; // rcx
  __int64 v46; // rcx
  int v47; // edi
  IID *p_rclsid; // rax
  int v49; // ecx
  __int64 v50; // rdx
  _OWORD *v51; // rbx
  int v52; // edi
  __int64 v53; // rdx
  __int64 v54; // rdx
  int v55; // edi
  _DWORD *v56; // r8
  int v57; // r8d
  int v58; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v59; // edx
  int DeviceFormatAndSpatialSettings; // ebx
  struct ICompositeSystemEffect *v61; // rcx
  bool v62; // al
  _DWORD *v63; // r8
  int v64; // r8d
  int v65; // r9d
  void *v66; // rcx
  bool v67; // al
  __int64 AudioPumpDspResourceTokenFromTokenList; // rax
  __int64 v69; // rbx
  struct AudioSrvTelemetryProvider *v70; // rax
  int v71; // eax
  IUnknown *v72; // rax
  void *v73; // rcx
  struct IAudioSystemEffects2 **ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  struct IAudioSystemEffects2 **dwImpLevel; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v80; // [rsp+78h] [rbp-88h] BYREF
  char v81; // [rsp+80h] [rbp-80h] BYREF
  char v82; // [rsp+81h] [rbp-7Fh] BYREF
  char v83; // [rsp+82h] [rbp-7Eh] BYREF
  char v84; // [rsp+83h] [rbp-7Dh] BYREF
  LPVOID v85; // [rsp+88h] [rbp-78h] BYREF
  int v86; // [rsp+90h] [rbp-70h] BYREF
  CEndpointCharacteristics **v87; // [rsp+98h] [rbp-68h] BYREF
  IUnknown *pProxy; // [rsp+A0h] [rbp-60h] BYREF
  char v89; // [rsp+A8h] [rbp-58h] BYREF
  char v90; // [rsp+A9h] [rbp-57h] BYREF
  char v91; // [rsp+AAh] [rbp-56h] BYREF
  char v92[5]; // [rsp+ABh] [rbp-55h] BYREF
  struct ICompositeSystemEffect *v93; // [rsp+B0h] [rbp-50h] BYREF
  struct IAudioProcessingObject *v94; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v95; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v96; // [rsp+D0h] [rbp-30h]
  int v97; // [rsp+E0h] [rbp-20h] BYREF
  int v98; // [rsp+E4h] [rbp-1Ch] BYREF
  int v99; // [rsp+E8h] [rbp-18h] BYREF
  struct IAudioProcessingObject *v100; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v101; // [rsp+F8h] [rbp-8h] BYREF
  struct ICompositeSystemEffect *v102; // [rsp+100h] [rbp+0h] BYREF
  struct ICompositeSystemEffect *v103; // [rsp+108h] [rbp+8h] BYREF
  IID rclsid; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v105; // [rsp+120h] [rbp+20h]
  struct tWAVEFORMATEX *v106; // [rsp+130h] [rbp+30h] BYREF
  __int64 v107; // [rsp+138h] [rbp+38h] BYREF
  __int64 v108; // [rsp+140h] [rbp+40h] BYREF
  __int64 v109; // [rsp+148h] [rbp+48h] BYREF
  CEndpointCharacteristics ***v110; // [rsp+150h] [rbp+50h] BYREF
  struct SpatialAudioSettings *v111; // [rsp+158h] [rbp+58h] BYREF
  void *p_pv; // [rsp+160h] [rbp+60h]
  IID *v113; // [rsp+168h] [rbp+68h]
  __int64 *v114; // [rsp+170h] [rbp+70h]
  char *v115; // [rsp+178h] [rbp+78h]
  _QWORD v116[2]; // [rsp+180h] [rbp+80h] BYREF
  IUnknown **v117; // [rsp+190h] [rbp+90h]
  LARGE_INTEGER PerformanceCount; // [rsp+1A0h] [rbp+A0h] BYREF
  LARGE_INTEGER v119; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v99 = a3;
  v87 = a1;
  v80 = a4;
  v16 = a6;
  *(_QWORD *)&rclsid.Data1 = a6;
  v106 = a9;
  v17 = a12;
  v116[0] = a14;
  v117 = a15;
  v84 = 0;
  v83 = 0;
  v82 = 0;
  v81 = 0;
  v18 = 0;
  v103 = 0;
  v19 = 0;
  v102 = 0;
  v109 = 0;
  v98 = 0;
  v108 = 0;
  v97 = 0;
  v20 = 0;
  v101 = 0;
  if ( ((a4 - 2) & 0xFFFFFFFD) != 0 )
  {
    v86 = (*(__int64 (__fastcall **)(CEndpointCharacteristics *))(*(_QWORD *)*a1 + 56LL))(*a1);
    a4 = v80;
  }
  else
  {
    v86 = 1;
  }
  v21 = 0;
  if ( (a4 == eHostProcessConnector || (v22 = a4 - 1) == 0 || (v23 = v22 - 1) == 0 || (unsigned int)(v23 - 1) <= 1)
    && !a2 )
  {
    v24 = g_pVolumeProvider;
    v25 = *(__int64 (__fastcall **)(struct IVolumeProvider *, _QWORD, __int64 *))(*(_QWORD *)g_pVolumeProvider + 40LL);
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v101, 0);
    v26 = v25(v24, *((_QWORD *)*v87 + 6), &v101);
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
    v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v101 + 224LL))(v101);
    v83 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v101 + 208LL))(v101);
    v82 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v101 + 216LL))(v101);
    if ( !(*(unsigned int (__fastcall **)(struct IAudioPolicyManager *))(*(_QWORD *)g_PolicyManager + 200LL))(g_PolicyManager)
      || (v28 = 1, v86) )
    {
      v28 = 0;
    }
    v81 = v28;
    if ( (v80 & 0xFFFFFFFC) == 0 && v80 != eLoopbackConnector )
    {
      if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v87[1], v80) )
      {
        v29 = 0;
        v100 = 0;
        v94 = 0;
        v30 = *(struct _GUID **)&rclsid.Data1;
        v95 = *(struct _GUID *)*(_QWORD *)&rclsid.Data1;
        if ( !EffectPack::CanProcessingModeBeParameterized(v87[1], &v95, v80)
          && (memcmp_0(Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u)
           || !(unsigned int)EffectPack::CanBuildProcessingModesOnRawConnector(v87[1], (unsigned int)v80, 0)
           || v80 == eOffloadConnector) )
        {
          v100 = 0;
          v103 = 0;
          v95 = *v30;
          EffectPack::GetModeEffect(v87[1], &v95, 0, v80, &v103, &v100, 0);
          v18 = v103;
          v29 = v100;
        }
        v94 = 0;
        v102 = 0;
        EffectPack::GetEndpointEffect(v87[1], 0, v80, &v102, &v94, 0);
        if ( memcmp_0(Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u) || v80 )
        {
          v19 = v102;
        }
        else
        {
          *(_QWORD *)&v95.Data1 = 0;
          v93 = 0;
          EffectPack::GetRawModePostMixEffect(
            v87[1],
            v31,
            eHostProcessConnector,
            &v93,
            (struct IAudioProcessingObject **)&v95,
            dwImpLevel);
          v19 = v93;
          if ( v93 )
          {
            if ( v102 )
            {
              v27 = -2147418113;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9BB,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
                (const char *)0x8000FFFFLL,
                (int)ppv);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v93);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v95);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v94);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v100);
              goto LABEL_144;
            }
            v102 = v93;
            (*(void (__fastcall **)(struct ICompositeSystemEffect *))(*(_QWORD *)v93 + 8LL))(v93);
            v32 = v94;
            v94 = *(struct IAudioProcessingObject **)&v95.Data1;
            if ( *(_QWORD *)&v95.Data1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v95.Data1 + 8LL))(*(_QWORD *)&v95.Data1);
            if ( v32 )
              ((void (__fastcall *)(struct IAudioProcessingObject *))v32->lpVtbl->Release)(v32);
          }
          else
          {
            v19 = v102;
          }
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v93);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v95);
        }
        if ( IsFixedFormatApo(v29) || (v21 = 0, IsFixedFormatApo(v94)) )
          v21 = 1;
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v94);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v100);
      }
      else
      {
        *(_QWORD *)&v95.Data1 = 0;
        v103 = 0;
        EffectPack::GetGfx(v87[1], v80, &v103, (struct IAudioProcessingObject **)&v95, ppv);
        v21 = IsFixedFormatApo(*(struct IAudioProcessingObject **)&v95.Data1);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v95);
        v18 = v103;
      }
      if ( v18 )
      {
        v33 = *(_QWORD *)v18;
        *(_QWORD *)&v95.Data1 = &v109;
        *(_QWORD *)v95.Data4 = 0;
        LOBYTE(v96) = 1;
        (*(void (__fastcall **)(struct ICompositeSystemEffect *, int *, unsigned __int8 *))(v33 + 32))(
          v18,
          &v98,
          v95.Data4);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v95);
      }
      if ( v19 )
      {
        v34 = *(_QWORD *)v19;
        *(_QWORD *)&v95.Data1 = &v108;
        *(_QWORD *)v95.Data4 = 0;
        LOBYTE(v96) = 1;
        (*(void (__fastcall **)(struct ICompositeSystemEffect *, int *, unsigned __int8 *))(v34 + 32))(
          v19,
          &v97,
          v95.Data4);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v95);
      }
    }
    if ( v84 || (v35 = 0, v83) )
      v35 = 1;
    v20 = v98 + v97 + v35 + (v81 != 0) + (v82 != 0);
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
    v45 = pv;
    pv = 0;
    goto LABEL_71;
  }
  memset_0(v38, 0, v37);
  v85 = 0;
  v39 = AudioSrvTelemetryProvider::Instance();
  CPerfTracker::CPerfTracker(&PerformanceCount, *((const struct _tlgProvider_t **)v39 + 1), "SaDevice_CoCreate", 0);
  if ( a2 == 1 )
  {
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v85, v40);
    ContainerProperty = CoCreateInstance(
                          &GUID_75269c13_41e1_4d0e_b8a0_9f8f22e246c9,
                          0,
                          0x17u,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v85);
    if ( ContainerProperty < 0 )
    {
      v42 = 2542;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
        (const char *)(unsigned int)ContainerProperty,
        ppva);
      CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
LABEL_56:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v85);
      v43 = pv;
      pv = 0;
LABEL_57:
      if ( v43 )
        CoTaskMemFree(v43);
      v27 = ContainerProperty;
      goto LABEL_144;
    }
  }
  else if ( v80 == eOffloadConnector )
  {
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v85, v40);
    ContainerProperty = CoCreateInstance(
                          &GUID_c994009c_34d3_4c9d_90ae_8dd53f521058,
                          0,
                          0x17u,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v85);
    if ( ContainerProperty < 0 )
    {
      v42 = 2548;
      goto LABEL_55;
    }
  }
  else
  {
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v85, v40);
    ContainerProperty = CoCreateInstance(
                          &GUID_89115307_8248_448f_ada0_f3f3718a9b2a,
                          0,
                          0x17u,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v85);
    if ( ContainerProperty < 0 )
    {
      v42 = 2552;
      goto LABEL_55;
    }
  }
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  pProxy = 0;
  ContainerProperty = (**(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))v85)(
                        v85,
                        &GUID_359f1fc4_4a4b_42d0_b75d_a021af7de2ee,
                        &pProxy);
  if ( ContainerProperty < 0 )
  {
    v44 = 2559;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
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
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v85);
    goto LABEL_70;
  }
  ContainerProperty = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 3u, 0, 0x40u);
  if ( ContainerProperty < 0 )
  {
    v44 = 2566;
    goto LABEL_67;
  }
  *((_QWORD *)pv + 1) = v106;
  *(_DWORD *)pv = v106->cbSize + 18;
  v46 = a10;
  if ( a10 )
  {
    *((_QWORD *)pv + 3) = a10;
    *((_DWORD *)pv + 4) = *(unsigned __int16 *)(v46 + 16) + 18;
  }
  else
  {
    *((_QWORD *)pv + 3) = 0;
    *((_DWORD *)pv + 4) = 0;
  }
  v47 = v86;
  *((_DWORD *)pv + 18) = v86;
  *((_QWORD *)pv + 7) = *((_QWORD *)*v87 + 6);
  *((_QWORD *)pv + 4) = a7;
  *((_QWORD *)pv + 5) = a8;
  *((_DWORD *)pv + 24) = 0;
  *((_DWORD *)pv + 20) = 0;
  *((_DWORD *)pv + 19) = v99;
  *((_DWORD *)pv + 25) = v80;
  *((_DWORD *)pv + 22) = -1;
  *((_DWORD *)pv + 23) = 0;
  *((_DWORD *)pv + 21) = -1;
  if ( ((v80 - 2) & 0xFFFFFFFD) != 0 && (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v87[1], v80) )
  {
    rclsid = *Buf1;
    p_rclsid = EffectPack::TranslateDeviceConnectorModeToStreamingConnectorMode(v87[1], &v95, v80, &rclsid);
  }
  else
  {
    rclsid = GUID_00000000_0000_0000_0000_000000000000;
    p_rclsid = &rclsid;
  }
  *(IID *)((char *)pv + 104) = *p_rclsid;
  *(_OWORD *)((char *)pv + 120) = *v16;
  *((_DWORD *)pv + 34) = CEndpointCharacteristics::HasHardwareAudioEngine(*v87);
  *((_DWORD *)pv + 12) = *((_DWORD *)*v87 + 58);
  if ( !(unsigned int)CEndpointCharacteristics::AreEnhancementsEnabled(*v87) || (v49 = 0, a2 == 1) )
    v49 = 1;
  *((_DWORD *)pv + 35) = v49;
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
        v50 = 2614;
LABEL_89:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v50,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
          (const char *)(unsigned int)ContainerProperty,
          ppva);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v85);
        v43 = pv;
        pv = 0;
        goto LABEL_57;
      }
    }
  }
  v51 = a13;
  if ( a13 && memcmp_0(a13, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    *(_OWORD *)((char *)pv + 180) = *v51;
  v110 = (CEndpointCharacteristics ***)&v80;
  v111 = (struct SpatialAudioSettings *)&v82;
  p_pv = &pv;
  v113 = (IID *)&v84;
  v114 = (__int64 *)&v83;
  v115 = &v81;
  *(_QWORD *)&v95.Data1 = &v98;
  *(_QWORD *)v95.Data4 = &pv;
  v96 = &v109;
  *(_QWORD *)&rclsid.Data1 = &v97;
  *(_QWORD *)rclsid.Data4 = &pv;
  v105 = &v108;
  if ( (v80 & 0xFFFFFFFC) == 0 && v80 != eLoopbackConnector )
  {
    if ( (unsigned int)EffectPack::EndpointConnectorSupportsProcessingModes(v87[1], v80) )
    {
      ContainerProperty = lambda_4d47e4b1195443ce5ef14f7026d1d081_::operator()(&v95, 0);
      if ( ContainerProperty < 0 )
      {
        v50 = 2681;
        goto LABEL_89;
      }
      v52 = ValidateUncompressedWaveFormatEx(v106);
      if ( !v52 )
      {
        ContainerProperty = lambda_3f48f908354d0a377503ef9be61a0c4e_::operator()(&rclsid, 0);
        if ( ContainerProperty < 0 )
        {
          v50 = 2686;
          goto LABEL_89;
        }
      }
      lambda_c327f0ba139a0c7bdef6b59ff99923d9_::operator()(&v110);
      if ( v52 == 1 )
      {
        LOBYTE(v53) = 1;
        ContainerProperty = lambda_3f48f908354d0a377503ef9be61a0c4e_::operator()(&rclsid, v53);
        if ( ContainerProperty < 0 )
        {
          v50 = 2695;
          goto LABEL_89;
        }
      }
    }
    else
    {
      v55 = ValidateUncompressedWaveFormatEx(v106);
      if ( v55 == 1 )
        lambda_c327f0ba139a0c7bdef6b59ff99923d9_::operator()(&v110);
      LOBYTE(v54) = v55 == 1;
      ContainerProperty = lambda_4d47e4b1195443ce5ef14f7026d1d081_::operator()(&v95, v54);
      if ( ContainerProperty < 0 )
      {
        v50 = 2721;
        goto LABEL_89;
      }
      if ( !v55 )
        lambda_c327f0ba139a0c7bdef6b59ff99923d9_::operator()(&v110);
    }
    v47 = v86;
  }
  if ( *((_DWORD *)pv + 24) > v20 )
  {
    v56 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v56 > 2u && (unsigned __int8)tlgKeywordOn(v56, 0x400000000400LL) )
    {
      v99 = *((_DWORD *)pv + 24);
      v86 = v97;
      LODWORD(v93) = v98;
      v89 = v81;
      v90 = v82;
      v91 = v83;
      v92[0] = v84;
      LODWORD(v100) = a2;
      LODWORD(v94) = v80;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v57,
        (unsigned int)&unk_1801A5B40,
        v57,
        v58,
        (__int64)&v94,
        (__int64)&v100,
        (__int64)v92,
        (__int64)&v91,
        (__int64)&v90,
        (__int64)&v89,
        (__int64)&v93,
        (__int64)&v86,
        (__int64)&v99);
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
  v110 = &v87;
  v111 = (struct SpatialAudioSettings *)&v80;
  p_pv = &v106;
  v113 = Buf1;
  v114 = &a7;
  *(GUID *)((char *)pv + 196) = GUID_00000000_0000_0000_0000_000000000000;
  if ( !v47 )
  {
    v59 = v80;
    if ( ((v80 - 2) & 0xFFFFFFFD) != 0 )
    {
      if ( g_DisableSpatialOnLowLatency )
      {
        if ( (unsigned __int8)lambda_9bf885da0abb1dc890da24065742d1f0_::operator()(&v110) )
          goto LABEL_136;
        v59 = v80;
      }
      *(_QWORD *)&v95.Data1 = 0;
      v93 = 0;
      v110 = (CEndpointCharacteristics ***)&v93;
      v111 = 0;
      LOBYTE(p_pv) = 1;
      *(_QWORD *)&rclsid.Data1 = &v95;
      *(_QWORD *)rclsid.Data4 = 0;
      LOBYTE(v105) = 1;
      DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                         v87[1],
                                         v59,
                                         0,
                                         (struct tWAVEFORMATEX **)rclsid.Data4,
                                         &v111,
                                         0,
                                         0);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&rclsid);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v110);
      if ( DeviceFormatAndSpatialSettings < 0 )
      {
        v63 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *v63 > 3u && (unsigned __int8)tlgKeywordOn(v63, 1024) )
        {
          LODWORD(v94) = a2;
          LODWORD(v100) = v80;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v64,
            (unsigned int)byte_1801A5AE5,
            v64,
            v65,
            (__int64)&v100,
            (__int64)&v94);
        }
      }
      else
      {
        v61 = v93;
        if ( !*(_DWORD *)v93 )
          goto LABEL_132;
        v62 = IsCompressedSpatialFormat(v106);
        v61 = v93;
        if ( !v62
          && (*(_OWORD *)((char *)v93 + 12) == DOLBY_ATMOS_MAT_SPATIAL_ENCODER
           || *(_OWORD *)((char *)v93 + 12) == DTSX_HDMI_SPATIAL_ENCODER) )
        {
          goto LABEL_132;
        }
        *(_OWORD *)((char *)pv + 196) = *(_OWORD *)((char *)v93 + 12);
      }
      v61 = v93;
LABEL_132:
      v93 = 0;
      if ( v61 )
        CoTaskMemFree(v61);
      v66 = *(void **)&v95.Data1;
      *(_QWORD *)&v95.Data1 = 0;
      if ( v66 )
        CoTaskMemFree(v66);
    }
  }
LABEL_136:
  v67 = CEndpointCharacteristics::DisablePumpBackupTimer(*v87);
  *((_DWORD *)pv + 53) = v67;
  v107 = 0;
  if ( v101 )
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v101)(v101, &GUID_2f732065_eff0_4c7c_8fc1_363851b1f1d7, &v107);
  else
    v107 = 0;
  AudioPumpDspResourceTokenFromTokenList = TryGetAudioPumpDspResourceTokenFromTokenList(v116, v116[0]);
  v69 = *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8);
  *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8) = 0;
  *(_QWORD *)&rclsid.Data1 = v69;
  AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair((AudioPumpDspResourceTokenPair *)v116);
  v70 = AudioSrvTelemetryProvider::Instance();
  CPerfTracker::CPerfTracker(&v119, *((const struct _tlgProvider_t **)v70 + 1), "SaDevice_Initialize", 0);
  ppvb = v99;
  v71 = ((__int64 (__fastcall *)(IUnknown *, LPVOID, __int64, __int64))pProxy->lpVtbl[1].QueryInterface)(
          pProxy,
          pv,
          v69,
          v107);
  v27 = v71;
  if ( v71 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB05,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\devicegraphmanagement.cpp",
      (const char *)(unsigned int)v71,
      ppvb);
    CPerfTracker::~CPerfTracker((CPerfTracker *)&v119);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&rclsid);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v107);
LABEL_116:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v85);
    v45 = pv;
    pv = 0;
LABEL_71:
    if ( v45 )
      CoTaskMemFree(v45);
    goto LABEL_144;
  }
  CPerfTracker::~CPerfTracker((CPerfTracker *)&v119);
  v72 = pProxy;
  pProxy = 0;
  *v117 = v72;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&rclsid);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v107);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pProxy);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v85);
  v73 = pv;
  pv = 0;
  if ( v73 )
    CoTaskMemFree(v73);
  v27 = 0;
LABEL_144:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v101);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v108, 0);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v109, 0);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v102);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v103);
  return v27;
}

```

## disassembly

```asm
0x180109b3c  mov     [rsp-8+arg_8], rbx
0x180109b41  push    rbp
0x180109b42  push    rsi
0x180109b43  push    rdi
0x180109b44  push    r12
0x180109b46  push    r13
0x180109b48  push    r14
0x180109b4a  push    r15
0x180109b4c  lea     rbp, [rsp-290h]
0x180109b54  sub     rsp, 390h
0x180109b5b  mov     rax, cs:__security_cookie
0x180109b62  xor     rax, rsp
0x180109b65  mov     [rbp+2C0h+var_40], rax
0x180109b6c  mov     [rbp+2C0h+var_2D8], r8d
0x180109b70  mov     r12d, edx
0x180109b73  mov     [rbp+2C0h+var_328], rcx
0x180109b77  mov     [rsp+3C0h+var_348], r9d
0x180109b7c  mov     r14, [rbp+2C0h+arg_28]
0x180109b83  mov     qword ptr [rbp+2C0h+rclsid.Data1], r14
0x180109b87  mov     rax, [rbp+2C0h+arg_40]
0x180109b8e  mov     [rbp+2C0h+var_290], rax
0x180109b92  mov     r13, [rbp+2C0h+arg_58]
0x180109b99  mov     rax, [rbp+2C0h+arg_68]
0x180109ba0  mov     [rbp+2C0h+var_240], rax
0x180109ba7  mov     rax, [rbp+2C0h+arg_70]
0x180109bae  mov     [rbp+2C0h+var_230], rax
0x180109bb5  xor     edx, edx
0x180109bb7  mov     [rbp+2C0h+var_33D], dl
0x180109bba  mov     [rbp+2C0h+var_33E], dl
0x180109bbd  mov     [rbp+2C0h+var_33F], dl
0x180109bc0  mov     [rbp+2C0h+var_340], dl
0x180109bc3  mov     edi, edx
0x180109bc5  mov     [rbp+2C0h+var_2B8], rdx
0x180109bc9  mov     ebx, edx
0x180109bcb  mov     [rbp+2C0h+var_2C0], rdx
0x180109bcf  mov     [rbp+2C0h+var_278], rdx
0x180109bd3  mov     [rbp+2C0h+var_2DC], edx
0x180109bd6  mov     [rbp+2C0h+var_280], rdx
0x180109bda  mov     [rbp+2C0h+var_2E0], edx
0x180109bdd  mov     esi, edx
0x180109bdf  mov     [rbp+2C0h+var_2C8], rdx
0x180109be3  lea     eax, [r9-2]
0x180109be7  test    eax, 0FFFFFFFDh
0x180109bec  jz      short loc_180109C09
0x180109bee  mov     rcx, [rcx]
0x180109bf1  mov     rax, [rcx]
0x180109bf4  mov     rax, [rax+38h]
0x180109bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109bfd  mov     [rbp+2C0h+var_330], eax
0x180109c00  mov     r9d, [rsp+3C0h+var_348]
0x180109c05  xor     edx, edx
0x180109c07  jmp     short loc_180109C10
0x180109c09  mov     [rbp+2C0h+var_330], 1
0x180109c10  mov     r15d, edx
0x180109c13  test    r9d, r9d
0x180109c16  jz      short loc_180109C34
0x180109c18  sub     r9d, 1
0x180109c1c  jz      short loc_180109C34
0x180109c1e  sub     r9d, 1
0x180109c22  jz      short loc_180109C34
0x180109c24  sub     r9d, 1
0x180109c28  jz      short loc_180109C34
0x180109c2a  cmp     r9d, 1
0x180109c2e  jnz     loc_18010A048
0x180109c34  test    r12d, r12d
0x180109c37  jnz     loc_18010A048
0x180109c3d  mov     r14, cs:?g_pVolumeProvider@@3PEAUIVolumeProvider@@EA; IVolumeProvider * g_pVolumeProvider
0x180109c44  mov     rax, [r14]
0x180109c47  mov     rsi, [rax+28h]
0x180109c4b  lea     rcx, [rbp+2C0h+var_2C8]
0x180109c4f  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180109c54  mov     rdx, [rbp+2C0h+var_328]
0x180109c58  mov     rdx, [rdx]
0x180109c5b  lea     r8, [rbp+2C0h+var_2C8]
0x180109c5f  mov     rdx, [rdx+30h]
0x180109c63  mov     rcx, r14
0x180109c66  mov     rax, rsi
0x180109c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c6e  mov     esi, eax
0x180109c70  xor     r14d, r14d
0x180109c73  test    eax, eax
0x180109c75  jns     short loc_180109C97
0x180109c77  mov     rcx, [rbp+2C8h]; this
0x180109c7e  mov     r9d, eax; char *
0x180109c81  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180109c88  mov     edx, 981h; void *
0x180109c8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c92  jmp     loc_18010AAE4
0x180109c97  mov     rcx, [rbp+2C0h+var_2C8]
0x180109c9b  mov     rax, [rcx]
0x180109c9e  mov     rax, [rax+0E0h]
0x180109ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109caa  mov     [rbp+2C0h+var_33D], al
0x180109cad  mov     rcx, [rbp+2C0h+var_2C8]
0x180109cb1  mov     rax, [rcx]
0x180109cb4  mov     rax, [rax+0D0h]
0x180109cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cc0  mov     [rbp+2C0h+var_33E], al
0x180109cc3  mov     rcx, [rbp+2C0h+var_2C8]
0x180109cc7  mov     rax, [rcx]
0x180109cca  mov     rax, [rax+0D8h]
0x180109cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cd6  mov     [rbp+2C0h+var_33F], al
0x180109cd9  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x180109ce0  mov     rax, [rcx]
0x180109ce3  mov     rax, [rax+0C8h]
0x180109cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cef  test    eax, eax
0x180109cf1  jz      short loc_180109CFB
0x180109cf3  cmp     [rbp+2C0h+var_330], r14d
0x180109cf7  mov     al, 1
0x180109cf9  jz      short loc_180109CFE
0x180109cfb  mov     al, r14b
0x180109cfe  mov     [rbp+2C0h+var_340], al
0x180109d01  mov     edx, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109d05  test    edx, 0FFFFFFFCh
0x180109d0b  jnz     loc_18010A011
0x180109d11  cmp     edx, 2
0x180109d14  jz      loc_18010A011
0x180109d1a  mov     rcx, [rbp+2C0h+var_328]
0x180109d1e  mov     rcx, [rcx+8]; this
0x180109d22  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x180109d27  test    eax, eax
0x180109d29  jnz     short loc_180109D6B
0x180109d2b  mov     rax, [rbp+2C0h+var_328]
0x180109d2f  mov     qword ptr [rbp+2C0h+var_300.Data1], r14
0x180109d33  mov     [rbp+2C0h+var_2B8], r14
0x180109d37  lea     r9, [rbp+2C0h+var_300]; struct IAudioProcessingObject **
0x180109d3b  lea     r8, [rbp+2C0h+var_2B8]; struct ICompositeSystemEffect **
0x180109d3f  mov     edx, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109d43  mov     rcx, [rax+8]; this
0x180109d47  call    ?GetGfx@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetGfx(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109d4c  mov     rcx, qword ptr [rbp+2C0h+var_300.Data1]; struct IAudioProcessingObject *
0x180109d50  call    ?IsFixedFormatApo@@YA_NPEAUIAudioProcessingObject@@@Z; IsFixedFormatApo(IAudioProcessingObject *)
0x180109d55  movzx   r15d, al
0x180109d59  lea     rcx, [rbp+2C0h+var_300]
0x180109d5d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109d62  mov     rdi, [rbp+2C0h+var_2B8]
0x180109d66  jmp     loc_180109FA5
0x180109d6b  mov     rsi, r14
0x180109d6e  mov     [rbp+2C0h+var_2D0], r14
0x180109d72  mov     [rbp+2C0h+var_308], r14
0x180109d76  mov     rbx, qword ptr [rbp+2C0h+rclsid.Data1]
0x180109d7a  movups  xmm0, xmmword ptr [rbx]
0x180109d7d  movdqu  xmmword ptr [rbp+2C0h+var_300.Data1], xmm0
0x180109d82  mov     r8d, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109d87  lea     rdx, [rbp+2C0h+var_300]; struct _GUID
0x180109d8b  mov     rcx, [rbp+2C0h+var_328]
0x180109d8f  mov     rcx, [rcx+8]; this
0x180109d93  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x180109d98  test    al, al
0x180109d9a  jnz     loc_180109E24
0x180109da0  mov     r8d, 10h; Size
0x180109da6  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x180109dad  mov     rcx, [rbp+2C0h+Buf1]; Buf1
0x180109db4  call    memcmp_0
0x180109db9  test    eax, eax
0x180109dbb  jnz     short loc_180109DDC
0x180109dbd  xor     r8d, r8d
0x180109dc0  mov     edx, [rsp+3C0h+var_348]
0x180109dc4  mov     rcx, [rbp+2C0h+var_328]
0x180109dc8  mov     rcx, [rcx+8]
0x180109dcc  call    ?CanBuildProcessingModesOnRawConnector@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@@Z; EffectPack::CanBuildProcessingModesOnRawConnector(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration)
0x180109dd1  test    eax, eax
0x180109dd3  jz      short loc_180109DDC
0x180109dd5  cmp     [rsp+3C0h+var_348], 1
0x180109dda  jnz     short loc_180109E24
0x180109ddc  mov     rax, [rbp+2C0h+var_328]
0x180109de0  mov     [rbp+2C0h+var_2D0], r14
0x180109de4  mov     [rbp+2C0h+var_2B8], r14
0x180109de8  movups  xmm0, xmmword ptr [rbx]
0x180109deb  movdqu  xmmword ptr [rbp+2C0h+var_300.Data1], xmm0
0x180109df0  mov     [rsp+3C0h+pAuthInfo], r14; struct IAudioSystemEffects2 **
0x180109df5  lea     rcx, [rbp+2C0h+var_2D0]
0x180109df9  mov     qword ptr [rsp+3C0h+dwImpLevel], rcx; struct IAudioProcessingObject **
0x180109dfe  lea     rcx, [rbp+2C0h+var_2B8]
0x180109e02  mov     [rsp+3C0h+ppv], rcx; struct ICompositeSystemEffect **
0x180109e07  mov     r9d, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109e0c  xor     r8d, r8d; int
0x180109e0f  lea     rdx, [rbp+2C0h+var_300]; struct _GUID *
0x180109e13  mov     rcx, [rax+8]; this
0x180109e17  call    ?GetModeEffect@EffectPack@@QEAAJU_GUID@@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetModeEffect(_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109e1c  mov     rdi, [rbp+2C0h+var_2B8]
0x180109e20  mov     rsi, [rbp+2C0h+var_2D0]
0x180109e24  mov     rax, [rbp+2C0h+var_328]
0x180109e28  mov     [rbp+2C0h+var_308], r14
0x180109e2c  mov     [rbp+2C0h+var_2C0], r14
0x180109e30  mov     qword ptr [rsp+3C0h+dwImpLevel], r14; struct IAudioSystemEffects2 **
0x180109e35  lea     rcx, [rbp+2C0h+var_308]
0x180109e39  mov     [rsp+3C0h+ppv], rcx; int
0x180109e3e  lea     r9, [rbp+2C0h+var_2C0]; struct ICompositeSystemEffect **
0x180109e42  mov     r8d, [rsp+3C0h+var_348]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109e47  xor     edx, edx; int
0x180109e49  mov     rcx, [rax+8]; this
0x180109e4d  call    ?GetEndpointEffect@EffectPack@@QEAAJHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetEndpointEffect(int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109e52  mov     r8d, 10h; Size
0x180109e58  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x180109e5f  mov     rcx, [rbp+2C0h+Buf1]; Buf1
0x180109e66  call    memcmp_0
0x180109e6b  test    eax, eax
0x180109e6d  jnz     loc_180109F6C
0x180109e73  cmp     [rsp+3C0h+var_348], r14d
0x180109e78  jnz     loc_180109F6C
0x180109e7e  mov     rax, [rbp+2C0h+var_328]
0x180109e82  mov     qword ptr [rbp+2C0h+var_300.Data1], r14
0x180109e86  mov     [rbp+2C0h+var_310], r14
0x180109e8a  lea     rcx, [rbp+2C0h+var_300]
0x180109e8e  mov     [rsp+3C0h+ppv], rcx; int
0x180109e93  lea     r9, [rbp+2C0h+var_310]; struct ICompositeSystemEffect **
0x180109e97  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180109e9a  mov     rcx, [rax+8]; this
0x180109e9e  call    ?GetRawModePostMixEffect@EffectPack@@QEAAJHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetRawModePostMixEffect(int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x180109ea3  mov     rbx, [rbp+2C0h+var_310]
0x180109ea7  test    rbx, rbx
0x180109eaa  jz      loc_180109F53
0x180109eb0  cmp     [rbp+2C0h+var_2C0], r14
0x180109eb4  jz      short loc_180109F03
0x180109eb6  mov     rcx, [rbp+2C8h]; this
0x180109ebd  mov     esi, 8000FFFFh
0x180109ec2  mov     r9d, esi; char *
0x180109ec5  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180109ecc  mov     edx, 9BBh; void *
0x180109ed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ed6  nop
0x180109ed7  lea     rcx, [rbp+2C0h+var_310]
0x180109edb  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109ee0  nop
0x180109ee1  lea     rcx, [rbp+2C0h+var_300]
0x180109ee5  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109eea  nop
0x180109eeb  lea     rcx, [rbp+2C0h+var_308]
0x180109eef  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109ef4  nop
0x180109ef5  lea     rcx, [rbp+2C0h+var_2D0]
0x180109ef9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109efe  jmp     loc_18010AAE4
0x180109f03  mov     [rbp+2C0h+var_2C0], rbx
0x180109f07  test    rbx, rbx
0x180109f0a  jz      short loc_180109F1C
0x180109f0c  mov     rax, [rbx]
0x180109f0f  mov     rcx, rbx
0x180109f12  mov     rax, [rax+8]
0x180109f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f1b  nop
0x180109f1c  mov     rcx, qword ptr [rbp+2C0h+var_300.Data1]
0x180109f20  mov     r14, [rbp+2C0h+var_308]
0x180109f24  mov     [rbp+2C0h+var_308], rcx
0x180109f28  test    rcx, rcx
0x180109f2b  jz      short loc_180109F39
0x180109f2d  mov     rax, [rcx]
0x180109f30  mov     rax, [rax+8]
0x180109f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f39  test    r14, r14
0x180109f3c  jz      short loc_180109F4E
0x180109f3e  mov     rax, [r14]
0x180109f41  mov     rcx, r14
0x180109f44  mov     rax, [rax+10h]
0x180109f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f4d  nop
0x180109f4e  xor     r14d, r14d
0x180109f51  jmp     short loc_180109F57
0x180109f53  mov     rbx, [rbp+2C0h+var_2C0]
0x180109f57  lea     rcx, [rbp+2C0h+var_310]
0x180109f5b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109f60  nop
0x180109f61  lea     rcx, [rbp+2C0h+var_300]
0x180109f65  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109f6a  jmp     short loc_180109F70
0x180109f6c  mov     rbx, [rbp+2C0h+var_2C0]
0x180109f70  mov     rcx, rsi; struct IAudioProcessingObject *
0x180109f73  call    ?IsFixedFormatApo@@YA_NPEAUIAudioProcessingObject@@@Z; IsFixedFormatApo(IAudioProcessingObject *)
0x180109f78  test    al, al
0x180109f7a  jnz     short loc_180109F8C
0x180109f7c  mov     rcx, [rbp+2C0h+var_308]; struct IAudioProcessingObject *
0x180109f80  call    ?IsFixedFormatApo@@YA_NPEAUIAudioProcessingObject@@@Z; IsFixedFormatApo(IAudioProcessingObject *)
0x180109f85  test    al, al
0x180109f87  mov     r15d, r14d
0x180109f8a  jz      short loc_180109F92
0x180109f8c  mov     r15d, 1
0x180109f92  lea     rcx, [rbp+2C0h+var_308]
0x180109f96  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109f9b  nop
0x180109f9c  lea     rcx, [rbp+2C0h+var_2D0]
0x180109fa0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180109fa5  test    rdi, rdi
0x180109fa8  jz      short loc_180109FDB
0x180109faa  mov     rax, [rdi]
0x180109fad  lea     rcx, [rbp+2C0h+var_278]
0x180109fb1  mov     qword ptr [rbp+2C0h+var_300.Data1], rcx
0x180109fb5  mov     qword ptr [rbp+2C0h+var_300.Data4], r14
0x180109fb9  mov     byte ptr [rbp+2C0h+var_2F0], 1
0x180109fbd  lea     r8, [rbp+2C0h+var_300.Data4]
0x180109fc1  lea     rdx, [rbp+2C0h+var_2DC]
0x180109fc5  mov     rcx, rdi
0x180109fc8  mov     rax, [rax+20h]
0x180109fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109fd1  nop
0x180109fd2  lea     rcx, [rbp+2C0h+var_300]
0x180109fd6  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180109fdb  test    rbx, rbx
  ... truncated ...
```
