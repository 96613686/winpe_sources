# CAudioSrv::VAD_AudiosrvServiceStart(void)

- ea: `0x1800f222c`
- end: `0x1800f29fa`
- name: `?VAD_AudiosrvServiceStart@CAudioSrv@@AEAAJXZ`
- size: `1998`
- prototype: `__int64 __fastcall(CAudioSrv *__hidden this)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f03f0`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x18001b520`
- `0x18001d8d8`
- `0x1800237e0`
- `0x18002d22c`
- `0x180071f50`
- `0x1800993e0`
- `0x1800a6894`
- `0x1800a695c`
- `0x1800ad0e4`
- `0x1800afad8`
- `0x1800b2de0`
- `0x1800b4c88`
- `0x1800bbc34`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800ce774`
- `0x1800dd70c`
- `0x1800ded84`
- `0x1800e0190`
- `0x1800e108c`
- `0x1800e5210`
- `0x1800eab10`
- `0x1800ed638`
- `0x1800ed7b8`
- `0x1800eda8c`
- `0x1800edb48`
- `0x1800f16e4`
- `0x1800f222c`
- `0x1800f2d04`
- `0x1800f2ee8`
- `0x1800f2f1c`
- `0x1800f2f50`
- `0x180106854`
- `0x18010cc54`
- `0x180111a9c`
- `0x180115124`
- `0x180127e04`
- `0x18012ee7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800f25cd`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800f25cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f26eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f26eb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f26fd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f26fd`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800f28d7`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800f28d7`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800f284e`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800f284e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f23a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f2567`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f25bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f2684`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f23a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f2567`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f25bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f2684`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f29a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f29a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f2764`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f2764`

## string_xrefs

- `0x1800f232a`: `avcore\audiocore\server\audiosrv\dll\audiosrv.cpp`
- `0x1800f247e`: `avcore\audiocore\server\audiosrv\dll\audiosrv.cpp`
- `0x1800f244b`: `avcore\audiocore\server\audiosrv\dll\customaudioresourcemanagerprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAudioSrv::VAD_AudiosrvServiceStart(CAudioSrv *this)
{
  wil::details *v2; // rax
  CPolicyConfig *v3; // rbx
  CPolicyConfig *v4; // rdi
  __int64 v5; // rdx
  signed int LastError; // ebx
  wil::details::in1diag3 *v7; // rcx
  PVOID *v9; // rsi
  unsigned int v10; // eax
  CAudioHealthMonitor *v11; // rax
  CAudioHealthMonitor *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rcx
  std::_Ref_count_base *v22; // rdx
  std::_Ref_count_base *v23; // rcx
  AudioSessionManagerProvider *v24; // rcx
  _QWORD *v25; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  const char *v29; // r9
  int wnf_subscription; // eax
  wil::details *v31; // rcx
  struct wil::details::wnf_subscription_state_base *v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rdx
  RPC_STATUS v35; // eax
  int v36; // eax
  Windows::Internal::ServiceModuleBase *v37; // rax
  int v38; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  wil::details *v42; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR *v45; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v47; // [rsp+70h] [rbp-90h]
  DWORD v48; // [rsp+78h] [rbp-88h] BYREF
  int v49[2]; // [rsp+80h] [rbp-80h] BYREF
  PVOID v50; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v51[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v52[15]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t String[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
  }
  v2 = (wil::details *)operator new[](0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v42 = v2;
  v4 = 0;
  if ( v2 )
  {
    memset_0(v2, 0, 0x58u);
    v4 = CPolicyConfig::CPolicyConfig(v3);
    v42 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<CAudioRenderEndpointChangeDelegator>::~MakeAllocator<CAudioRenderEndpointChangeDelegator>(&v42);
  *(_QWORD *)v49 = 0;
  v42 = g_PolicyConfig;
  g_PolicyConfig = v4;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v49);
  if ( !g_PolicyConfig )
  {
    v5 = 2140;
LABEL_9:
    LastError = -2147024882;
LABEL_10:
    v7 = retaddr;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      v7,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)(unsigned int)LastError,
      pdwType);
    return (unsigned int)LastError;
  }
  v9 = (PVOID *)((char *)this + 560);
  wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset((char *)this + 560);
  LastError = Microsoft::WRL::Details::MakeAndInitialize<EffectPackConfigurationManager,EffectPackConfigurationManager,>((char *)this + 560);
  if ( LastError < 0 )
  {
    v5 = 2142;
    goto LABEL_10;
  }
  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
         L"AudioHealthMonitorLimit",
         0x18u,
         0,
         &pvData,
         &pcbData) )
  {
    v10 = 5;
    pvData = 5;
  }
  else
  {
    v10 = pvData;
  }
  if ( v10 )
  {
    v11 = (CAudioHealthMonitor *)operator new[](0x60u, (const struct std::nothrow_t *)&std::nothrow);
    p_SecurityDescriptor = (PSECURITY_DESCRIPTOR *)v11;
    v12 = v11 ? CAudioHealthMonitor::CAudioHealthMonitor(v11, pvData) : 0LL;
    g_AudioHealthMonitor = (struct _FILETIME)v12;
    if ( !v12 )
    {
      v5 = 2159;
      goto LABEL_9;
    }
  }
  LastError = Microsoft::WRL::Details::MakeAndInitialize<CVolumeProvider,IVolumeProvider,>();
  v7 = retaddr;
  if ( LastError < 0 )
  {
    v5 = 2164;
    goto LABEL_11;
  }
  if ( !g_pVolumeProvider )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, (void *)0x875, v13, v14);
  wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy>::reset(retaddr);
  v15 = Microsoft::WRL::Details::MakeAndInitialize<CCustomAudioEndpointResourceManagerCache,IEndpointResourceManagerProvider,>(&g_CustomEndpointResourceManagerProvider);
  LastError = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\customaudioresourcemanagerprovider.cpp",
      (const char *)(unsigned int)v15,
      pdwType);
    v5 = 2168;
    goto LABEL_10;
  }
  wil::com_ptr_t<CAudioPumpDspResourceTracker,wil::err_returncode_policy>::reset();
  v16 = Microsoft::WRL::Details::MakeAndInitialize<CAudioPumpDspResourceTracker,CAudioPumpDspResourceTracker,>(&s_DspResourceTracker);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x87B,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)(unsigned int)v16,
      pdwType);
  v45 = 0;
  wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset(&v45);
  wil::com_query_to<IPolicyConfigInternal,Microsoft::WRL::ComPtr<CPolicyConfig> &>(v17, &v45);
  *(_QWORD *)v49 = *((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  v42 = (wil::details *)g_CustomEndpointResourceManagerProvider;
  v50 = *v9;
  p_SecurityDescriptor = v45;
  v18 = Microsoft::WRL::Details::MakeAndInitialize<CEndpointCharacteristicsCache,IEndpointCharacteristicsCache,IPolicyConfigInternal * &,EffectPackConfigurationManager * &,IEndpointResourceManagerProvider * &,_tlgProvider_t const * &>(
          v49[0],
          (unsigned int)&p_SecurityDescriptor,
          (unsigned int)&v50,
          (unsigned int)&v42,
          (__int64)v49);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2178;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)(unsigned int)v18,
      pdwTypea);
LABEL_82:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
    return (unsigned int)LastError;
  }
  v18 = EffectPackConfigurationManager::ScheduleScanForInstalledEffectPacks(*v9);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2182;
    goto LABEL_35;
  }
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"AudioSrvWatchDogTimerInMs",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    g_AudioSrvWatchDogTimerInMs = pvData;
  memset_0(String, 0, sizeof(String));
  v48 = 64;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"RenderStreamVolumeTaperPower",
          2u,
          0,
          String,
          &v48)
    && _wtof(String) != 0.0 )
  {
    v20 = (__int64 *)std::make_shared<CVolumeUnit,>(&p_SecurityDescriptor);
    v21 = *v20;
    v22 = (std::_Ref_count_base *)v20[1];
    *v20 = 0;
    v20[1] = 0;
    g_RenderStreamTaperTranslator = v21;
    v23 = qword_1801D66F0;
    qword_1801D66F0 = v22;
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    if ( v47 )
      std::_Ref_count_base::_Decref(v47);
    CVolumeUnit::SetDBRange(g_RenderStreamTaperTranslator);
  }
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"UnrestrictedPerProcessLoopback",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    g_UnrestrictedPerProcessLoopback = pvData;
  v18 = InitializeDeviceGraphManager();
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2209;
    goto LABEL_35;
  }
  v18 = Microsoft::WRL::Details::MakeAndInitialize<CAudioResourceManager,IAudioResourceManager,>();
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2211;
    goto LABEL_35;
  }
  v18 = AudioSessionManagerProvider::Initialize(v24);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2216;
    goto LABEL_35;
  }
  v25 = g_pEndpointCharacteristicsCache;
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)CEndpointCharacteristicsCache::PopulateEndpointCharacteristicsCache,
                     g_pEndpointCharacteristicsCache,
                     0);
  v25[12] = ThreadpoolWork;
  if ( ThreadpoolWork )
    SubmitThreadpoolWork(ThreadpoolWork);
  p_SecurityDescriptor = (PSECURITY_DESCRIPTOR *)g_PolicyManager;
  v18 = Microsoft::WRL::Details::MakeAndInitialize<Sarm::CSpatialAudioResourceManager,ISpatialAudioResourceManager,IAudioPolicyManager * &>(
          v27,
          &p_SecurityDescriptor);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2219;
    goto LABEL_35;
  }
  wil::com_ptr_t<IMulticastSessionManager,wil::err_returncode_policy>::reset();
  v18 = InitializeMulticastSessionManager(&g_MulticastSessionManager);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = 2221;
    goto LABEL_35;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-405489"
           "3335-185714091-3362601943-3526593181-1159816984-2199008581-497492991)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x8B0,
                  (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
                  v29);
    goto LABEL_82;
  }
  if ( !SecurityDescriptor )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, (void *)0x8B1, v28, v29);
  p_SecurityDescriptor = &SecurityDescriptor;
  LOBYTE(v47) = 1;
  v52[0] = off_180173FD8;
  v52[1] = this;
  v52[13] = v52;
  v42 = 0;
  wnf_subscription = wil::details::make_wnf_subscription_state<enum _PO_STANDBY_AUDIO_POLICY>(retaddr, v51, v28, &v42);
  v31 = 0;
  if ( wnf_subscription >= 0 )
    v31 = v42;
  v42 = v31;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 568,
    &v42);
  if ( v42 )
    wil::details::delete_wnf_subscription_state(v42, v32);
  wistd::function<void (enum Microsoft::Bluetooth::Audio::Internal::BluetoothLEAudioSupportedState const &)>::~function<void (enum Microsoft::Bluetooth::Audio::Internal::BluetoothLEAudioSupportedState const &)>(v51);
  if ( !*((_QWORD *)this + 71) )
  {
    LastError = -2147024882;
    v33 = 2147942414LL;
    v34 = 2241;
LABEL_81:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)v33,
      pdwTypea);
    LocalFree(SecurityDescriptor);
    goto LABEL_82;
  }
  if ( ServerEndpointIsStarted(L"AudioClientRpc") )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
    }
  }
  else
  {
    v35 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"AudioClientRpc", SecurityDescriptor);
    LastError = v35 != 0 ? v35 | 0x80010000 : 0;
    if ( LastError < 0 )
    {
      v33 = (unsigned int)LastError;
      v34 = 2252;
      goto LABEL_81;
    }
  }
  pdwTypea = 1234;
  v36 = RpcServerRegisterIf3(qword_18017C6B0, 0, 0, 33);
  LastError = v36 != 0 ? v36 | 0x80010000 : 0;
  if ( LastError < 0 )
  {
    v33 = (unsigned int)LastError;
    v34 = 2259;
    goto LABEL_81;
  }
  *((_DWORD *)this + 25) = 1;
  v37 = (Windows::Internal::ServiceModuleBase *)Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
  if ( !*((_QWORD *)v37 + 6) )
  {
    byte_1801D6748 = 1;
    byte_1801D6738 = 0;
    qword_1801D6730 = (__int64)&off_180173FC8;
    *((_QWORD *)v37 + 6) = &qword_1801D6730;
  }
  v38 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(v37);
  LastError = v38;
  if ( v38 < 0 )
  {
    v33 = (unsigned int)v38;
    v34 = 2263;
    goto LABEL_81;
  }
  *((_DWORD *)this + 26) = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids);
  }
  LocalFree(SecurityDescriptor);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
  return 0;
}

```

## disassembly

```asm
0x1800f222c  mov     rax, rsp
0x1800f222f  push    rbp
0x1800f2230  push    rbx
0x1800f2231  push    rsi
0x1800f2232  push    rdi
0x1800f2233  push    r12
0x1800f2235  push    r13
0x1800f2237  push    r14
0x1800f2239  push    r15
0x1800f223b  lea     rbp, [rsp-78h]
0x1800f2240  sub     rsp, 178h
0x1800f2247  movaps  xmmword ptr [rax-58h], xmm6
0x1800f224b  mov     rax, cs:__security_cookie
0x1800f2252  xor     rax, rsp
0x1800f2255  mov     [rbp+0B0h+var_60], rax
0x1800f2259  mov     r14, rcx
0x1800f225c  lea     rax, WPP_GLOBAL_Control
0x1800f2263  mov     r12d, 4
0x1800f2269  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f2270  cmp     rcx, rax
0x1800f2273  jz      short loc_1800F2296
0x1800f2275  test    [rcx+1Ch], r12b
0x1800f2279  jz      short loc_1800F2296
0x1800f227b  cmp     [rcx+19h], r12b
0x1800f227f  jb      short loc_1800F2296
0x1800f2281  lea     edx, [r12+26h]
0x1800f2286  lea     r8, WPP_287faa574dbc3bf006e0241a41e44d35_Traceguids
0x1800f228d  mov     rcx, [rcx+10h]
0x1800f2291  call    WPP_SF_
0x1800f2296  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f229d  mov     esi, 58h ; 'X'
0x1800f22a2  mov     ecx, esi; unsigned __int64
0x1800f22a4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f22a9  mov     rbx, rax
0x1800f22ac  mov     [rsp+1B0h+var_168], rax
0x1800f22b1  xor     r15d, r15d
0x1800f22b4  mov     edi, r15d
0x1800f22b7  test    rax, rax
0x1800f22ba  jz      short loc_1800F22D9
0x1800f22bc  mov     r8d, esi; Size
0x1800f22bf  xor     edx, edx; Val
0x1800f22c1  mov     rcx, rax; void *
0x1800f22c4  call    memset_0
0x1800f22c9  mov     rcx, rbx; this
0x1800f22cc  call    ??0CPolicyConfig@@QEAA@XZ; CPolicyConfig::CPolicyConfig(void)
0x1800f22d1  mov     rdi, rax
0x1800f22d4  mov     [rsp+1B0h+var_168], r15
0x1800f22d9  lea     rcx, [rsp+1B0h+var_168]
0x1800f22de  call    ??1?$MakeAllocator@VCAudioRenderEndpointChangeDelegator@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioRenderEndpointChangeDelegator>::~MakeAllocator<CAudioRenderEndpointChangeDelegator>(void)
0x1800f22e3  mov     qword ptr [rbp+0B0h+var_130], r15
0x1800f22e7  mov     rcx, cs:?g_PolicyConfig@@3V?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CPolicyConfig> g_PolicyConfig
0x1800f22ee  mov     [rsp+1B0h+var_168], rcx
0x1800f22f3  mov     cs:?g_PolicyConfig@@3V?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@A, rdi; Microsoft::WRL::ComPtr<CPolicyConfig> g_PolicyConfig
0x1800f22fa  lea     rcx, [rsp+1B0h+var_168]
0x1800f22ff  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f2304  lea     rcx, [rbp+0B0h+var_130]
0x1800f2308  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800f230d  cmp     cs:?g_PolicyConfig@@3V?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@A, r15; Microsoft::WRL::ComPtr<CPolicyConfig> g_PolicyConfig
0x1800f2314  jnz     short loc_1800F233D
0x1800f2316  mov     edx, 85Ch; void *
0x1800f231b  mov     ebx, 8007000Eh
0x1800f2320  mov     rcx, [rbp+0B8h]; this
0x1800f2327  mov     r9d, ebx; char *
0x1800f232a  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f2331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2336  mov     eax, ebx
0x1800f2338  jmp     loc_1800F29BC
0x1800f233d  lea     rsi, [r14+230h]
0x1800f2344  mov     rcx, rsi
0x1800f2347  call    ?reset@?$com_ptr_t@VEffectPackConfigurationManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset(void)
0x1800f234c  mov     rcx, rsi
0x1800f234f  call    ??$MakeAndInitialize@VEffectPackConfigurationManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVEffectPackConfigurationManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<EffectPackConfigurationManager,EffectPackConfigurationManager,>(EffectPackConfigurationManager * *)
0x1800f2354  mov     ebx, eax
0x1800f2356  test    eax, eax
0x1800f2358  jns     short loc_1800F2361
0x1800f235a  mov     edx, 85Eh
0x1800f235f  jmp     short loc_1800F2320
0x1800f2361  mov     [rsp+1B0h+var_170], r15d
0x1800f2366  mov     [rsp+1B0h+var_160], r12d
0x1800f236b  lea     rax, [rsp+1B0h+var_160]
0x1800f2370  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800f2375  lea     rax, [rsp+1B0h+var_170]
0x1800f237a  mov     [rsp+1B0h+pvData], rax; pvData
0x1800f237f  mov     [rsp+1B0h+pdwType], r15; int
0x1800f2384  mov     r9d, 18h; dwFlags
0x1800f238a  lea     r8, aAudiohealthmon; "AudioHealthMonitorLimit"
0x1800f2391  lea     r13, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800f2398  mov     rdx, r13; lpSubKey
0x1800f239b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f23a2  call    cs:__imp_RegGetValueW
0x1800f23a8  test    eax, eax
0x1800f23aa  jz      short loc_1800F23B7
0x1800f23ac  mov     eax, 5
0x1800f23b1  mov     [rsp+1B0h+var_170], eax
0x1800f23b5  jmp     short loc_1800F23BB
0x1800f23b7  mov     eax, [rsp+1B0h+var_170]
0x1800f23bb  test    eax, eax
0x1800f23bd  jz      short loc_1800F2401
0x1800f23bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f23c6  mov     ecx, 60h ; '`'; unsigned __int64
0x1800f23cb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800f23d0  mov     [rsp+1B0h+var_148], rax
0x1800f23d5  test    rax, rax
0x1800f23d8  jz      short loc_1800F23E8
0x1800f23da  mov     edx, [rsp+1B0h+var_170]; unsigned int
0x1800f23de  mov     rcx, rax; this
0x1800f23e1  call    ??0CAudioHealthMonitor@@QEAA@K@Z; CAudioHealthMonitor::CAudioHealthMonitor(ulong)
0x1800f23e6  jmp     short loc_1800F23EB
0x1800f23e8  mov     rax, r15
0x1800f23eb  mov     qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime, rax; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1800f23f2  test    rax, rax
0x1800f23f5  jnz     short loc_1800F2401
0x1800f23f7  mov     edx, 86Fh
0x1800f23fc  jmp     loc_1800F231B
0x1800f2401  call    ??$MakeAndInitialize@VCVolumeProvider@@UIVolumeProvider@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIVolumeProvider@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CVolumeProvider,IVolumeProvider,>(IVolumeProvider * *)
0x1800f2406  mov     ebx, eax
0x1800f2408  mov     rcx, [rbp+0B8h]; this
0x1800f240f  test    eax, eax
0x1800f2411  jns     short loc_1800F241D
0x1800f2413  mov     edx, 874h
0x1800f2418  jmp     loc_1800F2327
0x1800f241d  cmp     cs:?g_pVolumeProvider@@3PEAUIVolumeProvider@@EA, r15; IVolumeProvider * g_pVolumeProvider
0x1800f2424  jz      loc_1800F29EF
0x1800f242a  call    ?reset@?$com_ptr_t@UIEndpointResourceManagerProvider@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy>::reset(void)
0x1800f242f  lea     rcx, ?g_CustomEndpointResourceManagerProvider@@3V?$com_ptr_t@UIEndpointResourceManagerProvider@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy> g_CustomEndpointResourceManagerProvider
0x1800f2436  call    ??$MakeAndInitialize@VCCustomAudioEndpointResourceManagerCache@@UIEndpointResourceManagerProvider@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIEndpointResourceManagerProvider@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCustomAudioEndpointResourceManagerCache,IEndpointResourceManagerProvider,>(IEndpointResourceManagerProvider * *)
0x1800f243b  mov     ebx, eax
0x1800f243d  test    eax, eax
0x1800f243f  jns     short loc_1800F2466
0x1800f2441  mov     rcx, [rbp+0B8h]; this
0x1800f2448  mov     r9d, eax; char *
0x1800f244b  lea     r8, aAvcoreAudiocor_76; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f2452  mov     edx, 10Fh; void *
0x1800f2457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f245c  mov     edx, 878h
0x1800f2461  jmp     loc_1800F2320
0x1800f2466  call    ?reset@?$com_ptr_t@VCAudioPumpDspResourceTracker@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CAudioPumpDspResourceTracker,wil::err_returncode_policy>::reset(void)
0x1800f246b  lea     rcx, ?s_DspResourceTracker@@3V?$com_ptr_t@VCAudioPumpDspResourceTracker@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CAudioPumpDspResourceTracker,wil::err_returncode_policy> s_DspResourceTracker
0x1800f2472  call    ??$MakeAndInitialize@VCAudioPumpDspResourceTracker@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCAudioPumpDspResourceTracker@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioPumpDspResourceTracker,CAudioPumpDspResourceTracker,>(CAudioPumpDspResourceTracker * *)
0x1800f2477  mov     rcx, [rbp+0B8h]; this
0x1800f247e  lea     rdi, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800f2485  test    eax, eax
0x1800f2487  jns     short loc_1800F2499
0x1800f2489  mov     r9d, eax; char *
0x1800f248c  mov     r8, rdi; unsigned int
0x1800f248f  mov     edx, 87Bh; void *
0x1800f2494  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f2499  mov     [rsp+1B0h+var_150], r15
0x1800f249e  lea     rcx, [rsp+1B0h+var_150]
0x1800f24a3  call    ?reset@?$com_ptr_t@VEffectPackConfigurationManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset(void)
0x1800f24a8  lea     rdx, [rsp+1B0h+var_150]
0x1800f24ad  call    ??$com_query_to@UIPolicyConfigInternal@@AEAV?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@@wil@@YAXAEAV?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@PEAPEAUIPolicyConfigInternal@@@Z; wil::com_query_to<IPolicyConfigInternal,Microsoft::WRL::ComPtr<CPolicyConfig> &>(Microsoft::WRL::ComPtr<CPolicyConfig> &,IPolicyConfigInternal * *)
0x1800f24b2  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800f24b7  mov     rcx, [rax+8]
0x1800f24bb  mov     qword ptr [rbp+0B0h+var_130], rcx
0x1800f24bf  mov     rax, cs:?g_CustomEndpointResourceManagerProvider@@3V?$com_ptr_t@UIEndpointResourceManagerProvider@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy> g_CustomEndpointResourceManagerProvider
0x1800f24c6  mov     [rsp+1B0h+var_168], rax
0x1800f24cb  mov     rax, [rsi]
0x1800f24ce  mov     [rbp+0B0h+var_128], rax
0x1800f24d2  mov     rax, [rsp+1B0h+var_150]
0x1800f24d7  mov     [rsp+1B0h+var_148], rax
0x1800f24dc  lea     rax, [rbp+0B0h+var_130]
0x1800f24e0  mov     [rsp+1B0h+pdwType], rax; int
0x1800f24e5  lea     r9, [rsp+1B0h+var_168]
0x1800f24ea  lea     r8, [rbp+0B0h+var_128]
0x1800f24ee  lea     rdx, [rsp+1B0h+var_148]
0x1800f24f3  call    ??$MakeAndInitialize@VCEndpointCharacteristicsCache@@UIEndpointCharacteristicsCache@@AEAPEAUIPolicyConfigInternal@@AEAPEAVEffectPackConfigurationManager@@AEAPEAUIEndpointResourceManagerProvider@@AEAPEBU_tlgProvider_t@@@Details@WRL@Microsoft@@YAJPEAPEAUIEndpointCharacteristicsCache@@AEAPEAUIPolicyConfigInternal@@AEAPEAVEffectPackConfigurationManager@@AEAPEAUIEndpointResourceManagerProvider@@AEAPEBU_tlgProvider_t@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CEndpointCharacteristicsCache,IEndpointCharacteristicsCache,IPolicyConfigInternal * &,EffectPackConfigurationManager * &,IEndpointResourceManagerProvider * &,_tlgProvider_t const * &>(IEndpointCharacteristicsCache * *,IPolicyConfigInternal * &,EffectPackConfigurationManager * &,IEndpointResourceManagerProvider * &,_tlgProvider_t const * &)
0x1800f24f8  mov     ebx, eax
0x1800f24fa  test    eax, eax
0x1800f24fc  jns     short loc_1800F2505
0x1800f24fe  mov     edx, 882h
0x1800f2503  jmp     short loc_1800F2518
0x1800f2505  mov     rcx, [rsi]; pv
0x1800f2508  call    ?ScheduleScanForInstalledEffectPacks@EffectPackConfigurationManager@@QEAAJXZ; EffectPackConfigurationManager::ScheduleScanForInstalledEffectPacks(void)
0x1800f250d  mov     ebx, eax
0x1800f250f  test    eax, eax
0x1800f2511  jns     short loc_1800F252F
0x1800f2513  mov     edx, 886h; void *
0x1800f2518  mov     rcx, [rbp+0B8h]; this
0x1800f251f  mov     r9d, eax; char *
0x1800f2522  mov     r8, rdi; unsigned int
0x1800f2525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f252a  jmp     loc_1800F295C
0x1800f252f  mov     [rsp+1B0h+var_160], r12d
0x1800f2534  lea     rax, [rsp+1B0h+var_160]
0x1800f2539  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800f253e  lea     rax, [rsp+1B0h+var_170]
0x1800f2543  mov     [rsp+1B0h+pvData], rax; pvData
0x1800f2548  mov     [rsp+1B0h+pdwType], r15; pdwType
0x1800f254d  mov     r9d, 18h; dwFlags
0x1800f2553  lea     r8, aAudiosrvwatchd; "AudioSrvWatchDogTimerInMs"
0x1800f255a  mov     rdx, r13; lpSubKey
0x1800f255d  mov     rsi, 0FFFFFFFF80000002h
0x1800f2564  mov     rcx, rsi; hkey
0x1800f2567  call    cs:__imp_RegGetValueW
0x1800f256d  test    eax, eax
0x1800f256f  jnz     short loc_1800F257B
0x1800f2571  mov     eax, [rsp+1B0h+var_170]
0x1800f2575  mov     cs:?g_AudioSrvWatchDogTimerInMs@@3KA, eax; ulong g_AudioSrvWatchDogTimerInMs
0x1800f257b  mov     ebx, 40h ; '@'
0x1800f2580  mov     r8d, ebx; Size
0x1800f2583  xor     edx, edx; Val
0x1800f2585  lea     rcx, [rbp+0B0h+String]; void *
0x1800f2589  call    memset_0
0x1800f258e  mov     [rsp+1B0h+var_138], ebx
0x1800f2592  lea     rax, [rsp+1B0h+var_138]
0x1800f2597  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800f259c  lea     rax, [rbp+0B0h+String]
0x1800f25a0  mov     [rsp+1B0h+pvData], rax; pvData
0x1800f25a5  mov     [rsp+1B0h+pdwType], r15; pdwType
0x1800f25aa  lea     r9d, [rbx-3Eh]; dwFlags
0x1800f25ae  lea     r8, aRenderstreamvo; "RenderStreamVolumeTaperPower"
0x1800f25b5  mov     rdx, r13; lpSubKey
0x1800f25b8  mov     rcx, rsi; hkey
0x1800f25bb  call    cs:__imp_RegGetValueW
0x1800f25c1  test    eax, eax
0x1800f25c3  jnz     loc_1800F2653
0x1800f25c9  lea     rcx, [rbp+0B0h+String]; String
0x1800f25cd  call    cs:__imp__wtof
0x1800f25d3  movaps  xmm6, xmm0
0x1800f25d6  ucomisd xmm0, cs:__real@0000000000000000
0x1800f25de  jp      short loc_1800F25E2
0x1800f25e0  jz      short loc_1800F2653
0x1800f25e2  lea     rcx, [rsp+1B0h+var_148]
0x1800f25e7  call    ??$make_shared@VCVolumeUnit@@$$V@std@@YA?AV?$shared_ptr@VCVolumeUnit@@@0@XZ; std::make_shared<CVolumeUnit,>(void)
0x1800f25ec  mov     rcx, [rax]
0x1800f25ef  mov     rdx, [rax+8]
0x1800f25f3  mov     [rax], r15
0x1800f25f6  mov     [rax+8], r15
0x1800f25fa  mov     cs:?g_RenderStreamTaperTranslator@@3V?$shared_ptr@VCVolumeUnit@@@std@@A, rcx; std::shared_ptr<CVolumeUnit> g_RenderStreamTaperTranslator
0x1800f2601  mov     rcx, cs:qword_1801D66F0; this
0x1800f2608  mov     cs:qword_1801D66F0, rdx
0x1800f260f  test    rcx, rcx
0x1800f2612  jz      short loc_1800F2619
0x1800f2614  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f2619  mov     rcx, [rsp+1B0h+var_140]; this
0x1800f261e  test    rcx, rcx
0x1800f2621  jz      short loc_1800F2628
0x1800f2623  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f2628  movsd   [rsp+1B0h+pvData], xmm6
0x1800f262e  movss   xmm0, cs:__real@3fc00000
0x1800f2636  movss   dword ptr [rsp+1B0h+pdwType], xmm0
0x1800f263c  xorps   xmm3, xmm3
0x1800f263f  movss   xmm2, cs:__real@c2c00000
0x1800f2647  mov     rcx, cs:?g_RenderStreamTaperTranslator@@3V?$shared_ptr@VCVolumeUnit@@@std@@A; std::shared_ptr<CVolumeUnit> g_RenderStreamTaperTranslator
0x1800f264e  call    ?SetDBRange@CVolumeUnit@@QEAAXW4TAPERTYPE@@MMMN@Z; CVolumeUnit::SetDBRange(TAPERTYPE,float,float,float,double)
0x1800f2653  mov     [rsp+1B0h+var_160], r12d
0x1800f2658  lea     rax, [rsp+1B0h+var_160]
0x1800f265d  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800f2662  lea     rax, [rsp+1B0h+var_170]
0x1800f2667  mov     [rsp+1B0h+pvData], rax; pvData
0x1800f266c  mov     [rsp+1B0h+pdwType], r15; pdwType
0x1800f2671  mov     r9d, 18h; dwFlags
0x1800f2677  lea     r8, aUnrestrictedpe; "UnrestrictedPerProcessLoopback"
0x1800f267e  mov     rdx, r13; lpSubKey
0x1800f2681  mov     rcx, rsi; hkey
0x1800f2684  call    cs:__imp_RegGetValueW
0x1800f268a  test    eax, eax
0x1800f268c  jnz     short loc_1800F2698
0x1800f268e  mov     eax, [rsp+1B0h+var_170]
0x1800f2692  mov     cs:?g_UnrestrictedPerProcessLoopback@@3HA, eax; int g_UnrestrictedPerProcessLoopback
0x1800f2698  call    ?InitializeDeviceGraphManager@@YAJXZ; InitializeDeviceGraphManager(void)
0x1800f269d  mov     ebx, eax
0x1800f269f  test    eax, eax
0x1800f26a1  jns     short loc_1800F26AD
0x1800f26a3  mov     edx, 8A1h
0x1800f26a8  jmp     loc_1800F2518
0x1800f26ad  call    ??$MakeAndInitialize@VCAudioResourceManager@@UIAudioResourceManager@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAudioResourceManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioResourceManager,IAudioResourceManager,>(IAudioResourceManager * *)
0x1800f26b2  mov     ebx, eax
0x1800f26b4  test    eax, eax
0x1800f26b6  jns     short loc_1800F26C2
0x1800f26b8  mov     edx, 8A3h
0x1800f26bd  jmp     loc_1800F2518
0x1800f26c2  call    ?Initialize@AudioSessionManagerProvider@@YAJXZ; AudioSessionManagerProvider::Initialize(void)
0x1800f26c7  mov     ebx, eax
0x1800f26c9  test    eax, eax
0x1800f26cb  jns     short loc_1800F26D7
0x1800f26cd  mov     edx, 8A8h
0x1800f26d2  jmp     loc_1800F2518
0x1800f26d7  mov     rbx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x1800f26de  xor     r8d, r8d; pcbe
0x1800f26e1  mov     rdx, rbx; pv
0x1800f26e4  lea     rcx, ?PopulateEndpointCharacteristicsCache@CEndpointCharacteristicsCache@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f26eb  call    cs:__imp_CreateThreadpoolWork
0x1800f26f1  mov     [rbx+60h], rax
0x1800f26f5  test    rax, rax
0x1800f26f8  jz      short loc_1800F2703
0x1800f26fa  mov     rcx, rax; pwk
0x1800f26fd  call    cs:__imp_SubmitThreadpoolWork
0x1800f2703  mov     rax, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x1800f270a  mov     [rsp+1B0h+var_148], rax
0x1800f270f  lea     rdx, [rsp+1B0h+var_148]
0x1800f2714  call    ??$MakeAndInitialize@VCSpatialAudioResourceManager@Sarm@@UISpatialAudioResourceManager@@AEAPEAUIAudioPolicyManager@@@Details@WRL@Microsoft@@YAJPEAPEAUISpatialAudioResourceManager@@AEAPEAUIAudioPolicyManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Sarm::CSpatialAudioResourceManager,ISpatialAudioResourceManager,IAudioPolicyManager * &>(ISpatialAudioResourceManager * *,IAudioPolicyManager * &)
0x1800f2719  mov     ebx, eax
0x1800f271b  test    eax, eax
0x1800f271d  jns     short loc_1800F2729
0x1800f271f  mov     edx, 8ABh
0x1800f2724  jmp     loc_1800F2518
0x1800f2729  call    ?reset@?$com_ptr_t@UIMulticastSessionManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMulticastSessionManager,wil::err_returncode_policy>::reset(void)
0x1800f272e  lea     rcx, ?g_MulticastSessionManager@@3V?$com_ptr_t@UIMulticastSessionManager@@Uerr_returncode_policy@wil@@@wil@@A; struct IMulticastSessionManager **
  ... truncated ...
```
