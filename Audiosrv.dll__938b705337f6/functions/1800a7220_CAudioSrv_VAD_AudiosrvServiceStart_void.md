# CAudioSrv::VAD_AudiosrvServiceStart(void)

- ea: `0x1800a7220`
- end: `0x1800a78db`
- name: `?VAD_AudiosrvServiceStart@CAudioSrv@@AEAAJXZ`
- size: `1723`
- prototype: `__int64 __fastcall(CAudioSrv *__hidden this)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f0be0`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001d788`
- `0x180023690`
- `0x18002d0cc`
- `0x18006e444`
- `0x180072450`
- `0x1800a7220`
- `0x1800a78e4`
- `0x1800a7b48`
- `0x1800a7c0c`
- `0x1800a7cc0`
- `0x1800a7cd0`
- `0x1800a7d18`
- `0x1800a7d64`
- `0x1800b4ad0`
- `0x1800b6978`
- `0x1800bd784`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800df6fc`
- `0x1800e1808`
- `0x1800e5990`
- `0x1800eb290`
- `0x1800edc78`
- `0x1800ede3c`
- `0x1800edfbc`
- `0x1800eecac`
- `0x1800f1ed4`
- `0x1800f2a74`
- `0x1800f2c58`
- `0x1800f2c8c`
- `0x1800f2cc0`
- `0x180107074`
- `0x18010c9a4`
- `0x1801117ec`
- `0x180114ea4`
- `0x180127bb4`
- `0x18012ec2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800a7521`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800a7521`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800a7617`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800a7617`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7629`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a7629`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800a7800`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800a7800`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800a776e`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800a776e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a7340`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a74bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a7513`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a75b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a7340`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a74bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a7513`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a75b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a78a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a78a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a7690`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a7690`

## string_xrefs

- `0x1800a72c5`: `avcore\audiocore\server\audiosrv\dll\audiosrv.cpp`
- `0x1800a747b`: `avcore\audiocore\server\audiosrv\dll\audiosrv.cpp`
- `0x1800a76a1`: `avcore\audiocore\server\audiosrv\dll\audiosrv.cpp`
- `0x1800a783b`: `avcore\audiocore\server\audiosrv\dll\audiosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAudioSrv::VAD_AudiosrvServiceStart(CAudioSrv *this)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rdx
  signed int LastError; // ebx
  wil::details::in1diag3 *v6; // rcx
  PVOID *v8; // rdi
  unsigned int v9; // eax
  wil::details *v10; // rax
  CAudioHealthMonitor *v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  AudioSessionManagerProvider *v19; // rcx
  _QWORD *v20; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v22; // rcx
  unsigned int v23; // r8d
  const char *v24; // r9
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 wnf_subscription; // rax
  struct wil::details::wnf_subscription_state_base *v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rdx
  RPC_STATUS v31; // eax
  int v32; // eax
  Windows::Internal::ServiceModuleBase *lambda_b07e40d598d2e6cc64bbba968f53c163; // rax
  int v34; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  wil::details *v40; // [rsp+50h] [rbp-B0h] BYREF
  wil::details *v41; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v42; // [rsp+60h] [rbp-A0h]
  DWORD v43; // [rsp+68h] [rbp-98h] BYREF
  int v44[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID v45; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  char v47; // [rsp+88h] [rbp-78h]
  _BYTE v48[128]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t String[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
  }
  v2 = Microsoft::WRL::Details::Make<CPolicyConfig,>(v44);
  Microsoft::WRL::ComPtr<CPolicyConfig>::operator=(v3, v2);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(v44);
  if ( !g_PolicyConfig )
  {
    v4 = 2135;
LABEL_7:
    LastError = -2147024882;
LABEL_8:
    v6 = retaddr;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      v6,
      (void *)v4,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)(unsigned int)LastError,
      pdwType);
    return (unsigned int)LastError;
  }
  v8 = (PVOID *)((char *)this + 560);
  wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset((char *)this + 560);
  LastError = Microsoft::WRL::Details::MakeAndInitialize<EffectPackConfigurationManager,EffectPackConfigurationManager,>((char *)this + 560);
  if ( LastError < 0 )
  {
    v4 = 2137;
    goto LABEL_8;
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
    v9 = 5;
    pvData = 5;
  }
  else
  {
    v9 = pvData;
  }
  if ( v9 )
  {
    v10 = (wil::details *)operator new[](0x60u, (const struct std::nothrow_t *)&std::nothrow);
    v41 = v10;
    v11 = v10 ? CAudioHealthMonitor::CAudioHealthMonitor(v10, pvData) : 0LL;
    g_AudioHealthMonitor = (struct _FILETIME)v11;
    if ( !v11 )
    {
      v4 = 2154;
      goto LABEL_7;
    }
  }
  LastError = Microsoft::WRL::Details::MakeAndInitialize<CVolumeProvider,IVolumeProvider,>();
  v6 = retaddr;
  if ( LastError < 0 )
  {
    v4 = 2159;
    goto LABEL_9;
  }
  if ( !g_pVolumeProvider )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, (void *)0x870, v12, v13);
  wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy>::reset(retaddr);
  LastError = InitializeCustomEndpointResourceManagerProvider(&g_CustomEndpointResourceManagerProvider);
  if ( LastError < 0 )
  {
    v4 = 2163;
    goto LABEL_8;
  }
  v40 = 0;
  wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset(&v40);
  wil::com_query_to<IPolicyConfigInternal,Microsoft::WRL::ComPtr<CPolicyConfig> &>(v14, &v40);
  *(_QWORD *)v44 = *((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  p_SecurityDescriptor = (PSECURITY_DESCRIPTOR *)g_CustomEndpointResourceManagerProvider;
  v45 = *v8;
  v41 = v40;
  v15 = Microsoft::WRL::Details::MakeAndInitialize<CEndpointCharacteristicsCache,IEndpointCharacteristicsCache,IPolicyConfigInternal * &,EffectPackConfigurationManager * &,IEndpointResourceManagerProvider * &,_tlgProvider_t const * &>(
          v44[0],
          (unsigned int)&v41,
          (unsigned int)&v45,
          (unsigned int)&p_SecurityDescriptor,
          (__int64)v44);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2170;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)(unsigned int)v15,
      pdwTypea);
LABEL_74:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
    return (unsigned int)LastError;
  }
  v15 = EffectPackConfigurationManager::ScheduleScanForInstalledEffectPacks(*v8);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2174;
    goto LABEL_32;
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
  v43 = 64;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"RenderStreamVolumeTaperPower",
          2u,
          0,
          String,
          &v43)
    && _wtof(String) != 0.0 )
  {
    v17 = std::make_shared<CVolumeUnit,>(&v41);
    std::shared_ptr<CVolumeUnit>::operator=(v18, v17);
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
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
  v15 = InitializeDeviceGraphManager();
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2201;
    goto LABEL_32;
  }
  v15 = Microsoft::WRL::Details::MakeAndInitialize<CAudioResourceManager,IAudioResourceManager,>();
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2203;
    goto LABEL_32;
  }
  v15 = AudioSessionManagerProvider::Initialize(v19);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2208;
    goto LABEL_32;
  }
  v20 = g_pEndpointCharacteristicsCache;
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)CEndpointCharacteristicsCache::PopulateEndpointCharacteristicsCache,
                     g_pEndpointCharacteristicsCache,
                     0);
  v20[12] = ThreadpoolWork;
  if ( ThreadpoolWork )
    SubmitThreadpoolWork(ThreadpoolWork);
  v41 = g_PolicyManager;
  v15 = Microsoft::WRL::Details::MakeAndInitialize<Sarm::CSpatialAudioResourceManager,ISpatialAudioResourceManager,IAudioPolicyManager * &>(
          v22,
          &v41);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2211;
    goto LABEL_32;
  }
  wil::com_ptr_t<IMulticastSessionManager,wil::err_returncode_policy>::reset();
  v15 = InitializeMulticastSessionManager(&g_MulticastSessionManager);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 2213;
    goto LABEL_32;
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
                  (void *)0x8A8,
                  (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
                  v24);
    goto LABEL_74;
  }
  if ( !SecurityDescriptor )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, (void *)0x8A9, v23, v24);
  p_SecurityDescriptor = &SecurityDescriptor;
  v47 = 1;
  v25 = (_QWORD *)lambda_94e5a5c3bcbe6dc5ed82e5c580ce3bfb_::_lambda_94e5a5c3bcbe6dc5ed82e5c580ce3bfb_(&v45, this);
  wistd::function_void___cdecl_enum__PO_STANDBY_AUDIO_POLICY_const____::function_void___cdecl_enum__PO_STANDBY_AUDIO_POLICY_const______lambda_cc54e5dd528306179db4038c2fc6bf4d__void_(
    v48,
    *v25);
  wnf_subscription = wil::make_wnf_subscription_nothrow<enum _PO_STANDBY_AUDIO_POLICY>(&v41, v26, v48);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 568,
    wnf_subscription);
  if ( v41 )
    wil::details::delete_wnf_subscription_state(v41, v28);
  wistd::function<void (enum Microsoft::Bluetooth::Audio::Internal::BluetoothLEAudioSupportedState const &)>::~function<void (enum Microsoft::Bluetooth::Audio::Internal::BluetoothLEAudioSupportedState const &)>(v48);
  if ( !*((_QWORD *)this + 71) )
  {
    LastError = -2147024882;
    v29 = 2147942414LL;
    v30 = 2233;
LABEL_73:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosrv.cpp",
      (const char *)v29,
      pdwTypea);
    LocalFree(SecurityDescriptor);
    goto LABEL_74;
  }
  if ( ServerEndpointIsStarted(L"AudioClientRpc") )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
    }
  }
  else
  {
    v31 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"AudioClientRpc", SecurityDescriptor);
    LastError = v31 != 0 ? v31 | 0x80010000 : 0;
    if ( LastError < 0 )
    {
      v29 = (unsigned int)LastError;
      v30 = 2244;
      goto LABEL_73;
    }
  }
  pdwTypea = 1234;
  v32 = RpcServerRegisterIf3(&unk_18017B670, 0, 0, 33);
  LastError = v32 != 0 ? v32 | 0x80010000 : 0;
  if ( LastError < 0 )
  {
    v29 = (unsigned int)LastError;
    v30 = 2251;
    goto LABEL_73;
  }
  *((_DWORD *)this + 25) = 1;
  lambda_b07e40d598d2e6cc64bbba968f53c163 = (Windows::Internal::ServiceModuleBase *)Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::Create__lambda_b07e40d598d2e6cc64bbba968f53c163___();
  v34 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(lambda_b07e40d598d2e6cc64bbba968f53c163);
  LastError = v34;
  if ( v34 < 0 )
  {
    v29 = (unsigned int)v34;
    v30 = 2255;
    goto LABEL_73;
  }
  *((_DWORD *)this + 26) = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids);
  }
  LocalFree(SecurityDescriptor);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
  return 0;
}

```

## disassembly

```asm
0x1800a7220  mov     rax, rsp
0x1800a7223  push    rbp
0x1800a7224  push    rbx
0x1800a7225  push    rsi
0x1800a7226  push    rdi
0x1800a7227  push    r12
0x1800a7229  push    r13
0x1800a722b  push    r14
0x1800a722d  push    r15
0x1800a722f  lea     rbp, [rsp-78h]
0x1800a7234  sub     rsp, 178h
0x1800a723b  movaps  xmmword ptr [rax-58h], xmm6
0x1800a723f  mov     rax, cs:__security_cookie
0x1800a7246  xor     rax, rsp
0x1800a7249  mov     [rbp+0B0h+var_60], rax
0x1800a724d  mov     rsi, rcx
0x1800a7250  lea     rax, WPP_GLOBAL_Control
0x1800a7257  mov     r15d, 4
0x1800a725d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7264  cmp     rcx, rax
0x1800a7267  jz      short loc_1800A7289
0x1800a7269  test    [rcx+1Ch], r15b
0x1800a726d  jz      short loc_1800A7289
0x1800a726f  cmp     [rcx+19h], r15b
0x1800a7273  jb      short loc_1800A7289
0x1800a7275  lea     edx, [r15+26h]
0x1800a7279  lea     r8, WPP_126de3733680384bb8fabd64a7dcaca6_Traceguids
0x1800a7280  mov     rcx, [rcx+10h]
0x1800a7284  call    WPP_SF_
0x1800a7289  lea     rcx, [rsp+1B0h+var_140]
0x1800a728e  call    ??$Make@VCPolicyConfig@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPolicyConfig@@@12@XZ; Microsoft::WRL::Details::Make<CPolicyConfig,>(void)
0x1800a7293  mov     rdx, rax
0x1800a7296  call    ??4?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<CPolicyConfig>::operator=(Microsoft::WRL::ComPtr<CPolicyConfig> &&)
0x1800a729b  lea     rcx, [rsp+1B0h+var_140]
0x1800a72a0  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800a72a5  xor     r14d, r14d
0x1800a72a8  cmp     cs:?g_PolicyConfig@@3V?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@A, r14; Microsoft::WRL::ComPtr<CPolicyConfig> g_PolicyConfig
0x1800a72af  jnz     short loc_1800A72D8
0x1800a72b1  mov     edx, 857h; void *
0x1800a72b6  mov     ebx, 8007000Eh
0x1800a72bb  mov     rcx, [rbp+0B8h]; this
0x1800a72c2  mov     r9d, ebx; char *
0x1800a72c5  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a72cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a72d1  mov     eax, ebx
0x1800a72d3  jmp     loc_1800A78B3
0x1800a72d8  lea     rdi, [rsi+230h]
0x1800a72df  mov     rcx, rdi
0x1800a72e2  call    ?reset@?$com_ptr_t@VEffectPackConfigurationManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset(void)
0x1800a72e7  mov     rcx, rdi
0x1800a72ea  call    ??$MakeAndInitialize@VEffectPackConfigurationManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVEffectPackConfigurationManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<EffectPackConfigurationManager,EffectPackConfigurationManager,>(EffectPackConfigurationManager * *)
0x1800a72ef  mov     ebx, eax
0x1800a72f1  test    eax, eax
0x1800a72f3  jns     short loc_1800A72FC
0x1800a72f5  mov     edx, 859h
0x1800a72fa  jmp     short loc_1800A72BB
0x1800a72fc  mov     [rsp+1B0h+var_170], r14d
0x1800a7301  mov     [rsp+1B0h+var_16C], r15d
0x1800a7306  lea     rax, [rsp+1B0h+var_16C]
0x1800a730b  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800a7310  lea     rax, [rsp+1B0h+var_170]
0x1800a7315  mov     [rsp+1B0h+pvData], rax; pvData
0x1800a731a  mov     [rsp+1B0h+pdwType], r14; pdwType
0x1800a731f  mov     r9d, 18h; dwFlags
0x1800a7325  lea     r8, aAudiohealthmon; "AudioHealthMonitorLimit"
0x1800a732c  lea     r12, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a7333  mov     rdx, r12; lpSubKey
0x1800a7336  mov     r13, 0FFFFFFFF80000002h
0x1800a733d  mov     rcx, r13; hkey
0x1800a7340  call    cs:__imp_RegGetValueW
0x1800a7346  test    eax, eax
0x1800a7348  jz      short loc_1800A7355
0x1800a734a  mov     eax, 5
0x1800a734f  mov     [rsp+1B0h+var_170], eax
0x1800a7353  jmp     short loc_1800A7359
0x1800a7355  mov     eax, [rsp+1B0h+var_170]
0x1800a7359  test    eax, eax
0x1800a735b  jz      short loc_1800A739F
0x1800a735d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a7364  mov     ecx, 60h ; '`'; unsigned __int64
0x1800a7369  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a736e  mov     [rsp+1B0h+var_158], rax
0x1800a7373  test    rax, rax
0x1800a7376  jz      short loc_1800A7386
0x1800a7378  mov     edx, [rsp+1B0h+var_170]; unsigned int
0x1800a737c  mov     rcx, rax; this
0x1800a737f  call    ??0CAudioHealthMonitor@@QEAA@K@Z; CAudioHealthMonitor::CAudioHealthMonitor(ulong)
0x1800a7384  jmp     short loc_1800A7389
0x1800a7386  mov     rax, r14
0x1800a7389  mov     qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime, rax; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1800a7390  test    rax, rax
0x1800a7393  jnz     short loc_1800A739F
0x1800a7395  mov     edx, 86Ah
0x1800a739a  jmp     loc_1800A72B6
0x1800a739f  call    ??$MakeAndInitialize@VCVolumeProvider@@UIVolumeProvider@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIVolumeProvider@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CVolumeProvider,IVolumeProvider,>(IVolumeProvider * *)
0x1800a73a4  mov     ebx, eax
0x1800a73a6  mov     rcx, [rbp+0B8h]; this
0x1800a73ad  test    eax, eax
0x1800a73af  jns     short loc_1800A73BB
0x1800a73b1  mov     edx, 86Fh
0x1800a73b6  jmp     loc_1800A72C2
0x1800a73bb  cmp     cs:?g_pVolumeProvider@@3PEAUIVolumeProvider@@EA, r14; IVolumeProvider * g_pVolumeProvider
0x1800a73c2  jnz     short loc_1800A73CF
0x1800a73c4  mov     edx, 870h; void *
0x1800a73c9  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800a73cf  call    ?reset@?$com_ptr_t@UIEndpointResourceManagerProvider@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy>::reset(void)
0x1800a73d4  lea     rcx, ?g_CustomEndpointResourceManagerProvider@@3V?$com_ptr_t@UIEndpointResourceManagerProvider@@Uerr_returncode_policy@wil@@@wil@@A; struct IEndpointResourceManagerProvider **
0x1800a73db  call    ?InitializeCustomEndpointResourceManagerProvider@@YAJPEAPEAUIEndpointResourceManagerProvider@@@Z; InitializeCustomEndpointResourceManagerProvider(IEndpointResourceManagerProvider * *)
0x1800a73e0  mov     ebx, eax
0x1800a73e2  test    eax, eax
0x1800a73e4  jns     short loc_1800A73F0
0x1800a73e6  mov     edx, 873h
0x1800a73eb  jmp     loc_1800A72BB
0x1800a73f0  mov     [rsp+1B0h+var_160], r14
0x1800a73f5  lea     rcx, [rsp+1B0h+var_160]
0x1800a73fa  call    ?reset@?$com_ptr_t@VEffectPackConfigurationManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<EffectPackConfigurationManager,wil::err_returncode_policy>::reset(void)
0x1800a73ff  lea     rdx, [rsp+1B0h+var_160]
0x1800a7404  call    ??$com_query_to@UIPolicyConfigInternal@@AEAV?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@@wil@@YAXAEAV?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@PEAPEAUIPolicyConfigInternal@@@Z; wil::com_query_to<IPolicyConfigInternal,Microsoft::WRL::ComPtr<CPolicyConfig> &>(Microsoft::WRL::ComPtr<CPolicyConfig> &,IPolicyConfigInternal * *)
0x1800a7409  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800a740e  mov     rcx, [rax+8]
0x1800a7412  mov     qword ptr [rsp+1B0h+var_140], rcx
0x1800a7417  mov     rax, cs:?g_CustomEndpointResourceManagerProvider@@3V?$com_ptr_t@UIEndpointResourceManagerProvider@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IEndpointResourceManagerProvider,wil::err_returncode_policy> g_CustomEndpointResourceManagerProvider
0x1800a741e  mov     [rbp+0B0h+var_130], rax
0x1800a7422  mov     rax, [rdi]
0x1800a7425  mov     [rsp+1B0h+var_138], rax
0x1800a742a  mov     rax, [rsp+1B0h+var_160]
0x1800a742f  mov     [rsp+1B0h+var_158], rax
0x1800a7434  lea     rax, [rsp+1B0h+var_140]
0x1800a7439  mov     [rsp+1B0h+pdwType], rax; int
0x1800a743e  lea     r9, [rbp+0B0h+var_130]
0x1800a7442  lea     r8, [rsp+1B0h+var_138]
0x1800a7447  lea     rdx, [rsp+1B0h+var_158]
0x1800a744c  call    ??$MakeAndInitialize@VCEndpointCharacteristicsCache@@UIEndpointCharacteristicsCache@@AEAPEAUIPolicyConfigInternal@@AEAPEAVEffectPackConfigurationManager@@AEAPEAUIEndpointResourceManagerProvider@@AEAPEBU_tlgProvider_t@@@Details@WRL@Microsoft@@YAJPEAPEAUIEndpointCharacteristicsCache@@AEAPEAUIPolicyConfigInternal@@AEAPEAVEffectPackConfigurationManager@@AEAPEAUIEndpointResourceManagerProvider@@AEAPEBU_tlgProvider_t@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CEndpointCharacteristicsCache,IEndpointCharacteristicsCache,IPolicyConfigInternal * &,EffectPackConfigurationManager * &,IEndpointResourceManagerProvider * &,_tlgProvider_t const * &>(IEndpointCharacteristicsCache * *,IPolicyConfigInternal * &,EffectPackConfigurationManager * &,IEndpointResourceManagerProvider * &,_tlgProvider_t const * &)
0x1800a7451  mov     ebx, eax
0x1800a7453  test    eax, eax
0x1800a7455  jns     short loc_1800A745E
0x1800a7457  mov     edx, 87Ah
0x1800a745c  jmp     short loc_1800A7471
0x1800a745e  mov     rcx, [rdi]; pv
0x1800a7461  call    ?ScheduleScanForInstalledEffectPacks@EffectPackConfigurationManager@@QEAAJXZ; EffectPackConfigurationManager::ScheduleScanForInstalledEffectPacks(void)
0x1800a7466  mov     ebx, eax
0x1800a7468  test    eax, eax
0x1800a746a  jns     short loc_1800A748C
0x1800a746c  mov     edx, 87Eh; void *
0x1800a7471  mov     rcx, [rbp+0B8h]; this
0x1800a7478  mov     r9d, eax; char *
0x1800a747b  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a7482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7487  jmp     loc_1800A785B
0x1800a748c  mov     [rsp+1B0h+var_16C], r15d
0x1800a7491  lea     rax, [rsp+1B0h+var_16C]
0x1800a7496  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800a749b  lea     rax, [rsp+1B0h+var_170]
0x1800a74a0  mov     [rsp+1B0h+pvData], rax; pvData
0x1800a74a5  mov     [rsp+1B0h+pdwType], r14; pdwType
0x1800a74aa  mov     edi, 18h
0x1800a74af  mov     r9d, edi; dwFlags
0x1800a74b2  lea     r8, aAudiosrvwatchd; "AudioSrvWatchDogTimerInMs"
0x1800a74b9  mov     rdx, r12; lpSubKey
0x1800a74bc  mov     rcx, r13; hkey
0x1800a74bf  call    cs:__imp_RegGetValueW
0x1800a74c5  test    eax, eax
0x1800a74c7  jnz     short loc_1800A74D3
0x1800a74c9  mov     eax, [rsp+1B0h+var_170]
0x1800a74cd  mov     cs:?g_AudioSrvWatchDogTimerInMs@@3KA, eax; ulong g_AudioSrvWatchDogTimerInMs
0x1800a74d3  mov     ebx, 40h ; '@'
0x1800a74d8  mov     r8d, ebx; Size
0x1800a74db  xor     edx, edx; Val
0x1800a74dd  lea     rcx, [rbp+0B0h+String]; void *
0x1800a74e1  call    memset_0
0x1800a74e6  mov     [rsp+1B0h+var_148], ebx
0x1800a74ea  lea     rax, [rsp+1B0h+var_148]
0x1800a74ef  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800a74f4  lea     rax, [rbp+0B0h+String]
0x1800a74f8  mov     [rsp+1B0h+pvData], rax; pvData
0x1800a74fd  mov     [rsp+1B0h+pdwType], r14; pdwType
0x1800a7502  lea     r9d, [rbx-3Eh]; dwFlags
0x1800a7506  lea     r8, aRenderstreamvo; "RenderStreamVolumeTaperPower"
0x1800a750d  mov     rdx, r12; lpSubKey
0x1800a7510  mov     rcx, r13; hkey
0x1800a7513  call    cs:__imp_RegGetValueW
0x1800a7519  test    eax, eax
0x1800a751b  jnz     short loc_1800A7582
0x1800a751d  lea     rcx, [rbp+0B0h+String]; String
0x1800a7521  call    cs:__imp__wtof
0x1800a7527  movaps  xmm6, xmm0
0x1800a752a  ucomisd xmm0, cs:__real@0000000000000000
0x1800a7532  jp      short loc_1800A7536
0x1800a7534  jz      short loc_1800A7582
0x1800a7536  lea     rcx, [rsp+1B0h+var_158]
0x1800a753b  call    ??$make_shared@VCVolumeUnit@@$$V@std@@YA?AV?$shared_ptr@VCVolumeUnit@@@0@XZ; std::make_shared<CVolumeUnit,>(void)
0x1800a7540  mov     rdx, rax
0x1800a7543  call    ??4?$shared_ptr@VCVolumeUnit@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CVolumeUnit>::operator=(std::shared_ptr<CVolumeUnit> &&)
0x1800a7548  mov     rcx, [rsp+1B0h+var_150]; this
0x1800a754d  test    rcx, rcx
0x1800a7550  jz      short loc_1800A7557
0x1800a7552  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a7557  movsd   [rsp+1B0h+pvData], xmm6
0x1800a755d  movss   xmm0, cs:__real@3fc00000
0x1800a7565  movss   dword ptr [rsp+1B0h+pdwType], xmm0
0x1800a756b  xorps   xmm3, xmm3
0x1800a756e  movss   xmm2, cs:__real@c2c00000
0x1800a7576  mov     rcx, cs:?g_RenderStreamTaperTranslator@@3V?$shared_ptr@VCVolumeUnit@@@std@@A; std::shared_ptr<CVolumeUnit> g_RenderStreamTaperTranslator
0x1800a757d  call    ?SetDBRange@CVolumeUnit@@QEAAXW4TAPERTYPE@@MMMN@Z; CVolumeUnit::SetDBRange(TAPERTYPE,float,float,float,double)
0x1800a7582  mov     [rsp+1B0h+var_16C], r15d
0x1800a7587  lea     rax, [rsp+1B0h+var_16C]
0x1800a758c  mov     [rsp+1B0h+pcbData], rax; pcbData
0x1800a7591  lea     rax, [rsp+1B0h+var_170]
0x1800a7596  mov     [rsp+1B0h+pvData], rax; pvData
0x1800a759b  mov     [rsp+1B0h+pdwType], r14; pdwType
0x1800a75a0  mov     r9d, edi; dwFlags
0x1800a75a3  lea     r8, aUnrestrictedpe; "UnrestrictedPerProcessLoopback"
0x1800a75aa  mov     rdx, r12; lpSubKey
0x1800a75ad  mov     rcx, r13; hkey
0x1800a75b0  call    cs:__imp_RegGetValueW
0x1800a75b6  test    eax, eax
0x1800a75b8  jnz     short loc_1800A75C4
0x1800a75ba  mov     eax, [rsp+1B0h+var_170]
0x1800a75be  mov     cs:?g_UnrestrictedPerProcessLoopback@@3HA, eax; int g_UnrestrictedPerProcessLoopback
0x1800a75c4  call    ?InitializeDeviceGraphManager@@YAJXZ; InitializeDeviceGraphManager(void)
0x1800a75c9  mov     ebx, eax
0x1800a75cb  test    eax, eax
0x1800a75cd  jns     short loc_1800A75D9
0x1800a75cf  mov     edx, 899h
0x1800a75d4  jmp     loc_1800A7471
0x1800a75d9  call    ??$MakeAndInitialize@VCAudioResourceManager@@UIAudioResourceManager@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAudioResourceManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioResourceManager,IAudioResourceManager,>(IAudioResourceManager * *)
0x1800a75de  mov     ebx, eax
0x1800a75e0  test    eax, eax
0x1800a75e2  jns     short loc_1800A75EE
0x1800a75e4  mov     edx, 89Bh
0x1800a75e9  jmp     loc_1800A7471
0x1800a75ee  call    ?Initialize@AudioSessionManagerProvider@@YAJXZ; AudioSessionManagerProvider::Initialize(void)
0x1800a75f3  mov     ebx, eax
0x1800a75f5  test    eax, eax
0x1800a75f7  jns     short loc_1800A7603
0x1800a75f9  mov     edx, 8A0h
0x1800a75fe  jmp     loc_1800A7471
0x1800a7603  mov     rbx, cs:?g_pEndpointCharacteristicsCache@@3PEAUIEndpointCharacteristicsCache@@EA; IEndpointCharacteristicsCache * g_pEndpointCharacteristicsCache
0x1800a760a  xor     r8d, r8d; pcbe
0x1800a760d  mov     rdx, rbx; pv
0x1800a7610  lea     rcx, ?PopulateEndpointCharacteristicsCache@CEndpointCharacteristicsCache@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800a7617  call    cs:__imp_CreateThreadpoolWork
0x1800a761d  mov     [rbx+60h], rax
0x1800a7621  test    rax, rax
0x1800a7624  jz      short loc_1800A762F
0x1800a7626  mov     rcx, rax; pwk
0x1800a7629  call    cs:__imp_SubmitThreadpoolWork
0x1800a762f  mov     rax, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x1800a7636  mov     [rsp+1B0h+var_158], rax
0x1800a763b  lea     rdx, [rsp+1B0h+var_158]
0x1800a7640  call    ??$MakeAndInitialize@VCSpatialAudioResourceManager@Sarm@@UISpatialAudioResourceManager@@AEAPEAUIAudioPolicyManager@@@Details@WRL@Microsoft@@YAJPEAPEAUISpatialAudioResourceManager@@AEAPEAUIAudioPolicyManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Sarm::CSpatialAudioResourceManager,ISpatialAudioResourceManager,IAudioPolicyManager * &>(ISpatialAudioResourceManager * *,IAudioPolicyManager * &)
0x1800a7645  mov     ebx, eax
0x1800a7647  test    eax, eax
0x1800a7649  jns     short loc_1800A7655
0x1800a764b  mov     edx, 8A3h
0x1800a7650  jmp     loc_1800A7471
0x1800a7655  call    ?reset@?$com_ptr_t@UIMulticastSessionManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMulticastSessionManager,wil::err_returncode_policy>::reset(void)
0x1800a765a  lea     rcx, ?g_MulticastSessionManager@@3V?$com_ptr_t@UIMulticastSessionManager@@Uerr_returncode_policy@wil@@@wil@@A; struct IMulticastSessionManager **
0x1800a7661  call    ?InitializeMulticastSessionManager@@YAJPEAPEAUIMulticastSessionManager@@@Z; InitializeMulticastSessionManager(IMulticastSessionManager * *)
0x1800a7666  mov     ebx, eax
0x1800a7668  test    eax, eax
0x1800a766a  jns     short loc_1800A7676
0x1800a766c  mov     edx, 8A5h
0x1800a7671  jmp     loc_1800A7471
0x1800a7676  mov     [rsp+1B0h+SecurityDescriptor], r14
0x1800a767b  xor     r9d, r9d; SecurityDescriptorSize
0x1800a767e  lea     r8, [rsp+1B0h+SecurityDescriptor]; SecurityDescriptor
0x1800a7683  lea     edi, [r9+1]
0x1800a7687  mov     edx, edi; StringSDRevision
0x1800a7689  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800a7690  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a7696  mov     rcx, [rbp+0B8h]; this
0x1800a769d  test    eax, eax
0x1800a769f  jnz     short loc_1800A76B9
0x1800a76a1  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a76a8  mov     edx, 8A8h; void *
0x1800a76ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a76b2  mov     ebx, eax
0x1800a76b4  jmp     loc_1800A785B
0x1800a76b9  cmp     [rsp+1B0h+SecurityDescriptor], r14
0x1800a76be  jnz     short loc_1800A76CB
0x1800a76c0  mov     edx, 8A9h; void *
0x1800a76c5  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800a76cb  lea     rax, [rsp+1B0h+SecurityDescriptor]
0x1800a76d0  mov     [rbp+0B0h+var_130], rax
0x1800a76d4  mov     [rbp+0B0h+var_128], dil
0x1800a76d8  mov     rdx, rsi
0x1800a76db  lea     rcx, [rsp+1B0h+var_138]
0x1800a76e0  call    _lambda_94e5a5c3bcbe6dc5ed82e5c580ce3bfb____lambda_94e5a5c3bcbe6dc5ed82e5c580ce3bfb_
0x1800a76e5  mov     rdx, [rax]
0x1800a76e8  lea     rcx, [rbp+0B0h+var_120]
0x1800a76ec  call    wistd__function_void___cdecl_enum__PO_STANDBY_AUDIO_POLICY_const______function_void___cdecl_enum__PO_STANDBY_AUDIO_POLICY_const______lambda_cc54e5dd528306179db4038c2fc6bf4d__void_
0x1800a76f1  lea     r8, [rbp+0B0h+var_120]
0x1800a76f5  lea     rcx, [rsp+1B0h+var_158]
0x1800a76fa  call    ??$make_wnf_subscription_nothrow@W4_PO_STANDBY_AUDIO_POLICY@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBW4_PO_STANDBY_AUDIO_POLICY@@@Z@wistd@@K@Z; wil::make_wnf_subscription_nothrow<_PO_STANDBY_AUDIO_POLICY>(_WNF_STATE_NAME const &,wistd::function<void (_PO_STANDBY_AUDIO_POLICY const &)> &&,ulong)
0x1800a76ff  lea     rbx, [rsi+238h]
0x1800a7706  mov     rdx, rax
0x1800a7709  mov     rcx, rbx
0x1800a770c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x1800a7711  mov     rcx, [rsp+1B0h+var_158]; this
  ... truncated ...
```
