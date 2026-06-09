# AudioServerGetDevicePeriod

- ea: `0x180083210`
- end: `0x1800835af`
- name: `AudioServerGetDevicePeriod`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001e7dc`
- `0x180025d64`
- `0x180038a04`
- `0x1800394f0`
- `0x180045068`
- `0x180050bc0`
- `0x180055f44`
- `0x180083210`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180083274`
- `ntdll!EtwEventActivityIdControl` at `0x18008357b`
- `ntdll!EtwEventActivityIdControl` at `0x180083274`
- `ntdll!EtwEventActivityIdControl` at `0x18008357b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008349c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008352e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008349c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008352e`

## string_xrefs

- `0x18008334c`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x18008338e`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x18008347f`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c
__int64 __fastcall AudioServerGetDevicePeriod(
        __int64 a1,
        const unsigned __int16 *a2,
        __int128 *a3,
        __int64 a4,
        _QWORD *a5,
        __int64 *a6)
{
  __int128 v7; // xmm0
  struct _TP_TIMER **v9; // r14
  struct _TP_TIMER *v10; // rbx
  unsigned int v11; // edi
  struct AudioSrvTelemetryProvider *v12; // rax
  struct _TP_TIMER **v13; // rax
  struct _TP_TIMER **v14; // r14
  struct _TP_TIMER *v15; // rbx
  unsigned int v16; // edi
  struct AudioSrvTelemetryProvider *v17; // rax
  struct _TP_TIMER **v18; // rax
  int v19; // eax
  int ConnectorFormatForProcessingMode; // ebx
  int EndpointCharacteristicsDescriptor; // eax
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v22; // edx
  __int64 v23; // rdx
  struct _GUID v24; // xmm6
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  void *v27; // rcx
  int SharedModeEnginePeriodicity; // eax
  void *v29; // rcx
  int v30; // eax
  BOOL pftDueTime; // [rsp+28h] [rbp-E0h]
  LPVOID pv; // [rsp+88h] [rbp-80h] BYREF
  int v34; // [rsp+90h] [rbp-78h]
  EffectPack *v35[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-60h]
  struct _GUID v37; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-38h] BYREF
  LPVOID *p_pv; // [rsp+D8h] [rbp-30h] BYREF
  struct tWAVEFORMATEX *v41; // [rsp+E0h] [rbp-28h] BYREF
  char v42; // [rsp+E8h] [rbp-20h]
  __int128 v43; // [rsp+F0h] [rbp-18h]
  _QWORD v44[2]; // [rsp+100h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v7 = *a3;
  v44[0] = *(_QWORD *)a3;
  v44[1] = *((_QWORD *)a3 + 1);
  v43 = v7;
  EtwEventActivityIdControl(4, v44);
  v39 = 0;
  v38 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v9 = (struct _TP_TIMER **)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
    {
      v10 = (struct _TP_TIMER *)g_AudioHealthMonitor;
      v11 = g_AudioSrvWatchDogTimerInMs;
      v12 = AudioSrvTelemetryProvider::Instance();
      v13 = CWatchdogTimer<1>::CWatchdogTimer<1>(
              v9,
              *((struct _TP_TIMER **)v12 + 1),
              v11,
              (struct _TP_TIMER *)L"AudioServerGetDevicePeriod",
              v10);
    }
    else
    {
      v13 = 0;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v39, v13);
  }
  else
  {
    v14 = (struct _TP_TIMER **)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v14 )
    {
      v15 = (struct _TP_TIMER *)g_AudioHealthMonitor;
      v16 = g_AudioSrvWatchDogTimerInMs;
      v17 = AudioSrvTelemetryProvider::Instance();
      v18 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(
              v14,
              *((struct _TP_TIMER **)v17 + 1),
              v16,
              (struct _TP_TIMER *)L"AudioServerGetDevicePeriod",
              v15);
    }
    else
    {
      v18 = 0;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v38, v18);
  }
  v19 = ValidateVadServerSettings((struct VadServerSettings *)a3);
  ConnectorFormatForProcessingMode = v19;
  if ( v19 >= 0 )
  {
    v36 = 0;
    *(_OWORD *)v35 = 0;
    EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                          a2,
                                          0,
                                          (struct EndpointCharacteristicsDescriptor *)v35);
    ConnectorFormatForProcessingMode = EndpointCharacteristicsDescriptor;
    if ( EndpointCharacteristicsDescriptor < 0 )
    {
      v23 = 4018;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
        (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
        pftDueTime);
LABEL_15:
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v35);
      goto LABEL_31;
    }
    if ( a5 )
    {
      v37 = 0;
      pftDueTime = (*(__int64 (__fastcall **)(EffectPack *))(*(_QWORD *)v35[0] + 56LL))(v35[0]) == 1;
      EndpointCharacteristicsDescriptor = DeriveAudioProcessingModeConfiguration(
                                            *((unsigned int *)a3 + 12),
                                            *((unsigned int *)a3 + 14),
                                            *((unsigned int *)a3 + 32),
                                            v35);
      ConnectorFormatForProcessingMode = EndpointCharacteristicsDescriptor;
      if ( EndpointCharacteristicsDescriptor < 0 )
      {
        v23 = 4042;
        goto LABEL_14;
      }
      v24 = v37;
      p_pv = &pv;
      pv = 0;
      v41 = 0;
      v42 = 1;
      ConnectorFormatForProcessingMode = EffectPack::GetConnectorFormatForProcessingMode(
                                           v35[1],
                                           eHostProcessConnector,
                                           &v37,
                                           &v41);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( ConnectorFormatForProcessingMode < 0 )
      {
        v25 = (unsigned int)ConnectorFormatForProcessingMode;
        v26 = 4046;
        goto LABEL_21;
      }
      pftDueTime = 0;
      v34 = 0;
      v37 = v24;
      SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(v35[1], 0, pv, &v37);
      ConnectorFormatForProcessingMode = SharedModeEnginePeriodicity;
      if ( SharedModeEnginePeriodicity < 0 )
      {
        v25 = (unsigned int)SharedModeEnginePeriodicity;
        v26 = 4050;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
          (const char *)v25,
          pftDueTime);
        v27 = pv;
        pv = 0;
        if ( v27 )
          CoTaskMemFree(v27);
        goto LABEL_15;
      }
      v29 = pv;
      v30 = *((_DWORD *)pv + 1);
      pv = 0;
      *a5 = (unsigned int)(int)((double)v34 * 10000000.0 / (double)v30 + 0.5);
      if ( v29 )
        CoTaskMemFree(v29);
    }
    if ( !a6
      || (EndpointCharacteristicsDescriptor = EffectPack::GetMinProcessingPeriodForExclusiveMode(v35[1], v22, a6),
          ConnectorFormatForProcessingMode = EndpointCharacteristicsDescriptor,
          EndpointCharacteristicsDescriptor >= 0) )
    {
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v35);
      ConnectorFormatForProcessingMode = 0;
      goto LABEL_31;
    }
    v23 = 4058;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFAF,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
    (const char *)(unsigned int)v19,
    pftDueTime);
LABEL_31:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v38);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v39);
  EtwEventActivityIdControl(4, v44);
  return (unsigned int)ConnectorFormatForProcessingMode;
}

```

## disassembly

```asm
0x180083210  mov     rax, rsp
0x180083213  mov     [rax+8], rbx
0x180083217  push    rbp
0x180083218  push    rsi
0x180083219  push    rdi
0x18008321a  push    r12
0x18008321c  push    r13
0x18008321e  push    r14
0x180083220  push    r15
0x180083222  lea     rbp, [rax-58h]
0x180083226  sub     rsp, 120h
0x18008322d  movaps  xmmword ptr [rax-48h], xmm6
0x180083231  mov     rax, cs:__security_cookie
0x180083238  xor     rax, rsp
0x18008323b  mov     [rbp+50h+var_48], rax
0x18008323f  mov     rax, [r8]
0x180083242  mov     r13, rdx
0x180083245  movups  xmm0, xmmword ptr [r8]
0x180083249  mov     r12, [rbp+50h+arg_20]
0x180083250  lea     rdx, [rbp+50h+var_58]
0x180083254  mov     r15, [rbp+50h+arg_28]
0x18008325b  mov     ecx, 4
0x180083260  mov     [rbp+50h+var_58], rax
0x180083264  mov     rsi, r8
0x180083267  mov     rax, [r8+8]
0x18008326b  mov     [rbp+50h+var_50], rax
0x18008326f  movdqu  [rbp+50h+var_68], xmm0
0x180083274  call    cs:__imp_EtwEventActivityIdControl
0x18008327a  xor     edi, edi
0x18008327c  mov     [rbp+50h+var_88], rdi
0x180083280  mov     [rbp+50h+var_90], rdi
0x180083284  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x18008328b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180083290  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180083297  lea     ecx, [rdi+38h]; unsigned __int64
0x18008329a  test    al, al
0x18008329c  jz      short loc_1800832ED
0x18008329e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800832a3  mov     r14, rax
0x1800832a6  test    rax, rax
0x1800832a9  jz      short loc_1800832DC
0x1800832ab  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1800832b2  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x1800832b8  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800832bd  lea     r9, aAudioserverget_5; "AudioServerGetDevicePeriod"
0x1800832c4  mov     qword ptr [rsp+150h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x1800832c9  mov     r8d, edi
0x1800832cc  mov     rcx, r14; pv
0x1800832cf  mov     rdx, [rax+8]
0x1800832d3  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x1800832d8  xor     edi, edi
0x1800832da  jmp     short loc_1800832DF
0x1800832dc  mov     rax, rdi
0x1800832df  mov     rdx, rax
0x1800832e2  lea     rcx, [rbp+50h+var_88]
0x1800832e6  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x1800832eb  jmp     short loc_18008333A
0x1800832ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800832f2  mov     r14, rax
0x1800832f5  test    rax, rax
0x1800832f8  jz      short loc_18008332B
0x1800832fa  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180083301  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180083307  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18008330c  lea     r9, aAudioserverget_5; "AudioServerGetDevicePeriod"
0x180083313  mov     qword ptr [rsp+150h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x180083318  mov     r8d, edi
0x18008331b  mov     rcx, r14; pv
0x18008331e  mov     rdx, [rax+8]
0x180083322  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180083327  xor     edi, edi
0x180083329  jmp     short loc_18008332E
0x18008332b  mov     rax, rdi
0x18008332e  mov     rdx, rax
0x180083331  lea     rcx, [rbp+50h+var_90]
0x180083335  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x18008333a  mov     rcx, rsi; struct VadServerSettings *
0x18008333d  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x180083342  mov     ebx, eax
0x180083344  test    eax, eax
0x180083346  jns     short loc_180083365
0x180083348  mov     rcx, [rbp+58h]; this
0x18008334c  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083353  mov     r9d, eax; char *
0x180083356  mov     edx, 0FAFh; void *
0x18008335b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083360  jmp     loc_180083560
0x180083365  xorps   xmm0, xmm0
0x180083368  mov     [rbp+50h+var_B0], rdi
0x18008336c  lea     r8, [rbp+50h+var_C0]; struct EndpointCharacteristicsDescriptor *
0x180083370  xor     edx, edx; int
0x180083372  mov     rcx, r13; unsigned __int16 *
0x180083375  movdqu  xmmword ptr [rbp+50h+var_C0], xmm0
0x18008337a  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x18008337f  mov     ebx, eax
0x180083381  test    eax, eax
0x180083383  jns     short loc_1800833AB
0x180083385  mov     edx, 0FB2h; void *
0x18008338a  mov     rcx, [rbp+58h]; this
0x18008338e  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083395  mov     r9d, eax; char *
0x180083398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008339d  lea     rcx, [rbp+50h+var_C0]; this
0x1800833a1  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800833a6  jmp     loc_180083560
0x1800833ab  test    r12, r12
0x1800833ae  jz      loc_180083534
0x1800833b4  mov     rcx, [rbp+50h+var_C0]
0x1800833b8  xorps   xmm0, xmm0
0x1800833bb  movups  xmmword ptr [rbp+50h+var_A0.Data1], xmm0
0x1800833bf  mov     rax, [rcx]
0x1800833c2  mov     rax, [rax+38h]
0x1800833c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833cb  mov     r8d, [rsi+80h]
0x1800833d2  lea     r9, [rbp+50h+var_C0]
0x1800833d6  mov     ecx, [rsi+30h]
0x1800833d9  mov     edx, edi
0x1800833db  mov     [rsp+150h+var_D8], rdi
0x1800833e0  cmp     eax, 1
0x1800833e3  mov     [rsp+150h+var_E0], rdi
0x1800833e8  lea     rax, [rbp+50h+var_A0]
0x1800833ec  mov     [rsp+150h+var_E8], rdi
0x1800833f1  setz    dl
0x1800833f4  mov     [rsp+150h+var_F0], rdi
0x1800833f9  mov     [rsp+150h+var_F8], rax
0x1800833fe  mov     [rsp+150h+var_100], rdi
0x180083403  mov     dword ptr [rsp+150h+var_108], edi
0x180083407  mov     [rsp+150h+var_110], edi
0x18008340b  mov     [rsp+150h+var_118], rdi
0x180083410  mov     dword ptr [rsp+150h+var_120], edi
0x180083414  mov     dword ptr [rsp+150h+var_128], edi
0x180083418  mov     [rsp+150h+pftDueTime.dwLowDateTime], edx; int
0x18008341c  mov     edx, [rsi+38h]
0x18008341f  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x180083424  mov     ebx, eax
0x180083426  test    eax, eax
0x180083428  jns     short loc_180083434
0x18008342a  mov     edx, 0FCAh
0x18008342f  jmp     loc_18008338A
0x180083434  movaps  xmm6, xmmword ptr [rbp+50h+var_A0.Data1]
0x180083438  lea     rax, [rbp+50h+pv]
0x18008343c  mov     rcx, [rbp+50h+var_C0+8]; this
0x180083440  lea     r9, [rbp+50h+var_78]; struct tWAVEFORMATEX **
0x180083444  lea     r8, [rbp+50h+var_A0]; struct _GUID
0x180083448  mov     [rbp+50h+var_80], rax
0x18008344c  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008344e  movdqa  xmmword ptr [rbp+50h+var_A0.Data1], xmm6
0x180083453  mov     [rbp+50h+pv], rdi
0x180083457  mov     [rbp+50h+var_78], rdi
0x18008345b  mov     [rbp+50h+var_70], 1
0x18008345f  call    ?GetConnectorFormatForProcessingMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetConnectorFormatForProcessingMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x180083464  lea     rcx, [rbp+50h+var_80]
0x180083468  mov     ebx, eax
0x18008346a  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008346f  test    ebx, ebx
0x180083471  jns     short loc_1800834A7
0x180083473  mov     r9d, ebx; char *
0x180083476  mov     edx, 0FCEh; void *
0x18008347b  mov     rcx, [rbp+58h]; this
0x18008347f  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008348b  mov     rcx, [rbp+50h+pv]; pv
0x18008348f  mov     [rbp+50h+pv], rdi
0x180083493  test    rcx, rcx
0x180083496  jz      loc_18008339D
0x18008349c  call    cs:__imp_CoTaskMemFree
0x1800834a2  jmp     loc_18008339D
0x1800834a7  mov     r8, [rbp+50h+pv]
0x1800834ab  lea     rax, [rbp+50h+var_C8]
0x1800834af  mov     rcx, [rbp+50h+var_C0+8]
0x1800834b3  lea     r9, [rbp+50h+var_A0]
0x1800834b7  mov     qword ptr [rsp+150h+var_110], rdi
0x1800834bc  xor     edx, edx
0x1800834be  mov     [rsp+150h+var_118], rdi
0x1800834c3  mov     [rsp+150h+var_120], rdi
0x1800834c8  mov     [rsp+150h+var_128], rax
0x1800834cd  mov     [rsp+150h+pftDueTime.dwLowDateTime], edi
0x1800834d1  mov     [rbp+50h+var_C8], edi
0x1800834d4  movdqa  xmmword ptr [rbp+50h+var_A0.Data1], xmm6
0x1800834d9  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x1800834de  mov     ebx, eax
0x1800834e0  test    eax, eax
0x1800834e2  jns     short loc_1800834EE
0x1800834e4  mov     r9d, eax
0x1800834e7  mov     edx, 0FD2h
0x1800834ec  jmp     short loc_18008347B
0x1800834ee  mov     rcx, [rbp+50h+pv]; pv
0x1800834f2  xorps   xmm1, xmm1
0x1800834f5  mov     eax, [rbp+50h+var_C8]
0x1800834f8  xorps   xmm0, xmm0
0x1800834fb  cvtsi2sd xmm1, rax
0x180083500  mov     eax, [rcx+4]
0x180083503  mov     [rbp+50h+pv], rdi
0x180083507  cvtsi2sd xmm0, rax
0x18008350c  mulsd   xmm1, cs:__real@416312d000000000
0x180083514  divsd   xmm1, xmm0
0x180083518  addsd   xmm1, cs:__real@3fe0000000000000
0x180083520  cvttsd2si rax, xmm1
0x180083525  mov     [r12], rax
0x180083529  test    rcx, rcx
0x18008352c  jz      short loc_180083534
0x18008352e  call    cs:__imp_CoTaskMemFree
0x180083534  test    r15, r15
0x180083537  jz      short loc_180083555
0x180083539  mov     rcx, [rbp+50h+var_C0+8]; this
0x18008353d  mov     r8, r15; __int64 *
0x180083540  call    ?GetMinProcessingPeriodForExclusiveMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEA_J@Z; EffectPack::GetMinProcessingPeriodForExclusiveMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,__int64 *)
0x180083545  mov     ebx, eax
0x180083547  test    eax, eax
0x180083549  jns     short loc_180083555
0x18008354b  mov     edx, 0FDAh
0x180083550  jmp     loc_18008338A
0x180083555  lea     rcx, [rbp+50h+var_C0]; this
0x180083559  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18008355e  mov     ebx, edi
0x180083560  lea     rcx, [rbp+50h+var_90]
0x180083564  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180083569  lea     rcx, [rbp+50h+var_88]
0x18008356d  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180083572  lea     rdx, [rbp+50h+var_58]
0x180083576  mov     ecx, 4
0x18008357b  call    cs:__imp_EtwEventActivityIdControl
0x180083581  mov     eax, ebx
0x180083583  mov     rcx, [rbp+50h+var_48]
0x180083587  xor     rcx, rsp; StackCookie
0x18008358a  call    __security_check_cookie
0x18008358f  lea     r11, [rsp+150h+var_30]
0x180083597  mov     rbx, [r11+40h]
0x18008359b  movaps  xmm6, xmmword ptr [r11-10h]
0x1800835a0  mov     rsp, r11
0x1800835a3  pop     r15
0x1800835a5  pop     r14
0x1800835a7  pop     r13
0x1800835a9  pop     r12
0x1800835ab  pop     rdi
0x1800835ac  pop     rsi
0x1800835ad  pop     rbp
0x1800835ae  retn
```
