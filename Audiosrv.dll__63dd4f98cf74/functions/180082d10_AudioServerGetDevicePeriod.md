# AudioServerGetDevicePeriod

- ea: `0x180082d10`
- end: `0x1800830af`
- name: `AudioServerGetDevicePeriod`
- size: `927`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, __int64, _QWORD *, __int64 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x18001b520`
- `0x18001e92c`
- `0x180025eb4`
- `0x180038b64`
- `0x180039650`
- `0x180044bd8`
- `0x180050730`
- `0x180055ab4`
- `0x180082d10`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180082d74`
- `ntdll!EtwEventActivityIdControl` at `0x18008307b`
- `ntdll!EtwEventActivityIdControl` at `0x180082d74`
- `ntdll!EtwEventActivityIdControl` at `0x18008307b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008302e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008302e`

## string_xrefs

- `0x180082e4c`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180082e8e`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180082f7f`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c
__int64 __fastcall AudioServerGetDevicePeriod(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 *a6)
{
  IID v7; // xmm0
  void *v9; // r14
  struct _FILETIME v10; // rbx
  __int64 v11; // rax
  void *v12; // r14
  struct _FILETIME v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  int ConnectorFormatForProcessingMode; // ebx
  int EndpointCharacteristicsDescriptor; // eax
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v18; // edx
  __int64 v19; // rdx
  struct _GUID v20; // xmm6
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  void *v23; // rcx
  int SharedModeEnginePeriodicity; // eax
  void *v25; // rcx
  int v26; // eax
  BOOL pftDueTime; // [rsp+28h] [rbp-E0h]
  LPVOID pv; // [rsp+88h] [rbp-80h] BYREF
  int v30; // [rsp+90h] [rbp-78h]
  EffectPack *v31[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-60h]
  struct _GUID v33; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-38h] BYREF
  LPVOID *p_pv; // [rsp+D8h] [rbp-30h] BYREF
  struct tWAVEFORMATEX *v37; // [rsp+E0h] [rbp-28h] BYREF
  char v38; // [rsp+E8h] [rbp-20h]
  IID v39; // [rsp+F0h] [rbp-18h]
  _QWORD v40[2]; // [rsp+100h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v7 = *(IID *)a3;
  v40[0] = *(_QWORD *)a3;
  v40[1] = *(_QWORD *)(a3 + 8);
  v39 = v7;
  EtwEventActivityIdControl(4, v40);
  v35 = 0;
  v34 = 0;
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
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v35, v11);
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
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v34, v14);
  }
  v15 = ValidateVadServerSettings((IID *)a3);
  ConnectorFormatForProcessingMode = v15;
  if ( v15 >= 0 )
  {
    v32 = 0;
    *(_OWORD *)v31 = 0;
    EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                          a2,
                                          0,
                                          (struct EndpointCharacteristicsDescriptor *)v31);
    ConnectorFormatForProcessingMode = EndpointCharacteristicsDescriptor;
    if ( EndpointCharacteristicsDescriptor < 0 )
    {
      v19 = 4018;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
        (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
        pftDueTime);
LABEL_15:
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v31);
      goto LABEL_31;
    }
    if ( a5 )
    {
      v33 = 0;
      pftDueTime = (*(__int64 (__fastcall **)(EffectPack *))(*(_QWORD *)v31[0] + 56LL))(v31[0]) == 1;
      EndpointCharacteristicsDescriptor = DeriveAudioProcessingModeConfiguration(
                                            *(unsigned int *)(a3 + 48),
                                            *(unsigned int *)(a3 + 56),
                                            *(unsigned int *)(a3 + 128),
                                            v31);
      ConnectorFormatForProcessingMode = EndpointCharacteristicsDescriptor;
      if ( EndpointCharacteristicsDescriptor < 0 )
      {
        v19 = 4042;
        goto LABEL_14;
      }
      v20 = v33;
      p_pv = &pv;
      pv = 0;
      v37 = 0;
      v38 = 1;
      ConnectorFormatForProcessingMode = EffectPack::GetConnectorFormatForProcessingMode(
                                           v31[1],
                                           eHostProcessConnector,
                                           &v33,
                                           &v37);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( ConnectorFormatForProcessingMode < 0 )
      {
        v21 = (unsigned int)ConnectorFormatForProcessingMode;
        v22 = 4046;
        goto LABEL_21;
      }
      pftDueTime = 0;
      v30 = 0;
      v33 = v20;
      SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(v31[1], 0, pv, &v33);
      ConnectorFormatForProcessingMode = SharedModeEnginePeriodicity;
      if ( SharedModeEnginePeriodicity < 0 )
      {
        v21 = (unsigned int)SharedModeEnginePeriodicity;
        v22 = 4050;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
          (const char *)v21,
          pftDueTime);
        v23 = pv;
        pv = 0;
        if ( v23 )
          CoTaskMemFree(v23);
        goto LABEL_15;
      }
      v25 = pv;
      v26 = *((_DWORD *)pv + 1);
      pv = 0;
      *a5 = (unsigned int)(int)((double)v30 * 10000000.0 / (double)v26 + 0.5);
      if ( v25 )
        CoTaskMemFree(v25);
    }
    if ( !a6
      || (EndpointCharacteristicsDescriptor = EffectPack::GetMinProcessingPeriodForExclusiveMode(v31[1], v18, a6),
          ConnectorFormatForProcessingMode = EndpointCharacteristicsDescriptor,
          EndpointCharacteristicsDescriptor >= 0) )
    {
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v31);
      ConnectorFormatForProcessingMode = 0;
      goto LABEL_31;
    }
    v19 = 4058;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFAF,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
    (const char *)(unsigned int)v15,
    pftDueTime);
LABEL_31:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v34);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v35);
  EtwEventActivityIdControl(4, v40);
  return (unsigned int)ConnectorFormatForProcessingMode;
}

```

## disassembly

```asm
0x180082d10  mov     rax, rsp
0x180082d13  mov     [rax+8], rbx
0x180082d17  push    rbp
0x180082d18  push    rsi
0x180082d19  push    rdi
0x180082d1a  push    r12
0x180082d1c  push    r13
0x180082d1e  push    r14
0x180082d20  push    r15
0x180082d22  lea     rbp, [rax-58h]
0x180082d26  sub     rsp, 120h
0x180082d2d  movaps  xmmword ptr [rax-48h], xmm6
0x180082d31  mov     rax, cs:__security_cookie
0x180082d38  xor     rax, rsp
0x180082d3b  mov     [rbp+50h+var_48], rax
0x180082d3f  mov     rax, [r8]
0x180082d42  mov     r13, rdx
0x180082d45  movups  xmm0, xmmword ptr [r8]
0x180082d49  mov     r12, [rbp+50h+arg_20]
0x180082d50  lea     rdx, [rbp+50h+var_58]
0x180082d54  mov     r15, [rbp+50h+arg_28]
0x180082d5b  mov     ecx, 4
0x180082d60  mov     [rbp+50h+var_58], rax
0x180082d64  mov     rsi, r8
0x180082d67  mov     rax, [r8+8]
0x180082d6b  mov     [rbp+50h+var_50], rax
0x180082d6f  movdqu  [rbp+50h+var_68], xmm0
0x180082d74  call    cs:__imp_EtwEventActivityIdControl
0x180082d7a  xor     edi, edi
0x180082d7c  mov     [rbp+50h+var_88], rdi
0x180082d80  mov     [rbp+50h+var_90], rdi
0x180082d84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180082d8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180082d90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180082d97  lea     ecx, [rdi+38h]; unsigned __int64
0x180082d9a  test    al, al
0x180082d9c  jz      short loc_180082DED
0x180082d9e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180082da3  mov     r14, rax
0x180082da6  test    rax, rax
0x180082da9  jz      short loc_180082DDC
0x180082dab  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180082db2  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180082db8  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180082dbd  lea     r9, aAudioserverget_5; "AudioServerGetDevicePeriod"
0x180082dc4  mov     qword ptr [rsp+150h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x180082dc9  mov     r8d, edi
0x180082dcc  mov     rcx, r14; pv
0x180082dcf  mov     rdx, [rax+8]
0x180082dd3  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180082dd8  xor     edi, edi
0x180082dda  jmp     short loc_180082DDF
0x180082ddc  mov     rax, rdi
0x180082ddf  mov     rdx, rax
0x180082de2  lea     rcx, [rbp+50h+var_88]
0x180082de6  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180082deb  jmp     short loc_180082E3A
0x180082ded  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180082df2  mov     r14, rax
0x180082df5  test    rax, rax
0x180082df8  jz      short loc_180082E2B
0x180082dfa  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180082e01  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180082e07  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180082e0c  lea     r9, aAudioserverget_5; "AudioServerGetDevicePeriod"
0x180082e13  mov     qword ptr [rsp+150h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x180082e18  mov     r8d, edi
0x180082e1b  mov     rcx, r14; pv
0x180082e1e  mov     rdx, [rax+8]
0x180082e22  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180082e27  xor     edi, edi
0x180082e29  jmp     short loc_180082E2E
0x180082e2b  mov     rax, rdi
0x180082e2e  mov     rdx, rax
0x180082e31  lea     rcx, [rbp+50h+var_90]
0x180082e35  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180082e3a  mov     rcx, rsi; struct VadServerSettings *
0x180082e3d  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x180082e42  mov     ebx, eax
0x180082e44  test    eax, eax
0x180082e46  jns     short loc_180082E65
0x180082e48  mov     rcx, [rbp+58h]; this
0x180082e4c  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180082e53  mov     r9d, eax; char *
0x180082e56  mov     edx, 0FAFh; void *
0x180082e5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082e60  jmp     loc_180083060
0x180082e65  xorps   xmm0, xmm0
0x180082e68  mov     [rbp+50h+var_B0], rdi
0x180082e6c  lea     r8, [rbp+50h+var_C0]; struct EndpointCharacteristicsDescriptor *
0x180082e70  xor     edx, edx; int
0x180082e72  mov     rcx, r13; unsigned __int16 *
0x180082e75  movdqu  xmmword ptr [rbp+50h+var_C0], xmm0
0x180082e7a  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x180082e7f  mov     ebx, eax
0x180082e81  test    eax, eax
0x180082e83  jns     short loc_180082EAB
0x180082e85  mov     edx, 0FB2h; void *
0x180082e8a  mov     rcx, [rbp+58h]; this
0x180082e8e  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180082e95  mov     r9d, eax; char *
0x180082e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082e9d  lea     rcx, [rbp+50h+var_C0]; this
0x180082ea1  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x180082ea6  jmp     loc_180083060
0x180082eab  test    r12, r12
0x180082eae  jz      loc_180083034
0x180082eb4  mov     rcx, [rbp+50h+var_C0]
0x180082eb8  xorps   xmm0, xmm0
0x180082ebb  movups  xmmword ptr [rbp+50h+var_A0.Data1], xmm0
0x180082ebf  mov     rax, [rcx]
0x180082ec2  mov     rax, [rax+38h]
0x180082ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ecb  mov     r8d, [rsi+80h]
0x180082ed2  lea     r9, [rbp+50h+var_C0]
0x180082ed6  mov     ecx, [rsi+30h]
0x180082ed9  mov     edx, edi
0x180082edb  mov     [rsp+150h+var_D8], rdi
0x180082ee0  cmp     eax, 1
0x180082ee3  mov     [rsp+150h+var_E0], rdi
0x180082ee8  lea     rax, [rbp+50h+var_A0]
0x180082eec  mov     [rsp+150h+var_E8], rdi
0x180082ef1  setz    dl
0x180082ef4  mov     [rsp+150h+var_F0], rdi
0x180082ef9  mov     [rsp+150h+var_F8], rax
0x180082efe  mov     [rsp+150h+var_100], rdi
0x180082f03  mov     dword ptr [rsp+150h+var_108], edi
0x180082f07  mov     [rsp+150h+var_110], edi
0x180082f0b  mov     [rsp+150h+var_118], rdi
0x180082f10  mov     dword ptr [rsp+150h+var_120], edi
0x180082f14  mov     dword ptr [rsp+150h+var_128], edi
0x180082f18  mov     [rsp+150h+pftDueTime.dwLowDateTime], edx; int
0x180082f1c  mov     edx, [rsi+38h]
0x180082f1f  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x180082f24  mov     ebx, eax
0x180082f26  test    eax, eax
0x180082f28  jns     short loc_180082F34
0x180082f2a  mov     edx, 0FCAh
0x180082f2f  jmp     loc_180082E8A
0x180082f34  movaps  xmm6, xmmword ptr [rbp+50h+var_A0.Data1]
0x180082f38  lea     rax, [rbp+50h+pv]
0x180082f3c  mov     rcx, [rbp+50h+var_C0+8]; this
0x180082f40  lea     r9, [rbp+50h+var_78]; struct tWAVEFORMATEX **
0x180082f44  lea     r8, [rbp+50h+var_A0]; struct _GUID
0x180082f48  mov     [rbp+50h+var_80], rax
0x180082f4c  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180082f4e  movdqa  xmmword ptr [rbp+50h+var_A0.Data1], xmm6
0x180082f53  mov     [rbp+50h+pv], rdi
0x180082f57  mov     [rbp+50h+var_78], rdi
0x180082f5b  mov     [rbp+50h+var_70], 1
0x180082f5f  call    ?GetConnectorFormatForProcessingMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetConnectorFormatForProcessingMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x180082f64  lea     rcx, [rbp+50h+var_80]
0x180082f68  mov     ebx, eax
0x180082f6a  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180082f6f  test    ebx, ebx
0x180082f71  jns     short loc_180082FA7
0x180082f73  mov     r9d, ebx; char *
0x180082f76  mov     edx, 0FCEh; void *
0x180082f7b  mov     rcx, [rbp+58h]; this
0x180082f7f  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180082f86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082f8b  mov     rcx, [rbp+50h+pv]; pv
0x180082f8f  mov     [rbp+50h+pv], rdi
0x180082f93  test    rcx, rcx
0x180082f96  jz      loc_180082E9D
0x180082f9c  call    cs:__imp_CoTaskMemFree
0x180082fa2  jmp     loc_180082E9D
0x180082fa7  mov     r8, [rbp+50h+pv]
0x180082fab  lea     rax, [rbp+50h+var_C8]
0x180082faf  mov     rcx, [rbp+50h+var_C0+8]
0x180082fb3  lea     r9, [rbp+50h+var_A0]
0x180082fb7  mov     qword ptr [rsp+150h+var_110], rdi
0x180082fbc  xor     edx, edx
0x180082fbe  mov     [rsp+150h+var_118], rdi
0x180082fc3  mov     [rsp+150h+var_120], rdi
0x180082fc8  mov     [rsp+150h+var_128], rax
0x180082fcd  mov     [rsp+150h+pftDueTime.dwLowDateTime], edi
0x180082fd1  mov     [rbp+50h+var_C8], edi
0x180082fd4  movdqa  xmmword ptr [rbp+50h+var_A0.Data1], xmm6
0x180082fd9  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x180082fde  mov     ebx, eax
0x180082fe0  test    eax, eax
0x180082fe2  jns     short loc_180082FEE
0x180082fe4  mov     r9d, eax
0x180082fe7  mov     edx, 0FD2h
0x180082fec  jmp     short loc_180082F7B
0x180082fee  mov     rcx, [rbp+50h+pv]; pv
0x180082ff2  xorps   xmm1, xmm1
0x180082ff5  mov     eax, [rbp+50h+var_C8]
0x180082ff8  xorps   xmm0, xmm0
0x180082ffb  cvtsi2sd xmm1, rax
0x180083000  mov     eax, [rcx+4]
0x180083003  mov     [rbp+50h+pv], rdi
0x180083007  cvtsi2sd xmm0, rax
0x18008300c  mulsd   xmm1, cs:__real@416312d000000000
0x180083014  divsd   xmm1, xmm0
0x180083018  addsd   xmm1, cs:__real@3fe0000000000000
0x180083020  cvttsd2si rax, xmm1
0x180083025  mov     [r12], rax
0x180083029  test    rcx, rcx
0x18008302c  jz      short loc_180083034
0x18008302e  call    cs:__imp_CoTaskMemFree
0x180083034  test    r15, r15
0x180083037  jz      short loc_180083055
0x180083039  mov     rcx, [rbp+50h+var_C0+8]; this
0x18008303d  mov     r8, r15; __int64 *
0x180083040  call    ?GetMinProcessingPeriodForExclusiveMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEA_J@Z; EffectPack::GetMinProcessingPeriodForExclusiveMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,__int64 *)
0x180083045  mov     ebx, eax
0x180083047  test    eax, eax
0x180083049  jns     short loc_180083055
0x18008304b  mov     edx, 0FDAh
0x180083050  jmp     loc_180082E8A
0x180083055  lea     rcx, [rbp+50h+var_C0]; this
0x180083059  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18008305e  mov     ebx, edi
0x180083060  lea     rcx, [rbp+50h+var_90]
0x180083064  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180083069  lea     rcx, [rbp+50h+var_88]
0x18008306d  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180083072  lea     rdx, [rbp+50h+var_58]
0x180083076  mov     ecx, 4
0x18008307b  call    cs:__imp_EtwEventActivityIdControl
0x180083081  mov     eax, ebx
0x180083083  mov     rcx, [rbp+50h+var_48]
0x180083087  xor     rcx, rsp; StackCookie
0x18008308a  call    __security_check_cookie
0x18008308f  lea     r11, [rsp+150h+var_30]
0x180083097  mov     rbx, [r11+40h]
0x18008309b  movaps  xmm6, xmmword ptr [r11-10h]
0x1800830a0  mov     rsp, r11
0x1800830a3  pop     r15
0x1800830a5  pop     r14
0x1800830a7  pop     r13
0x1800830a9  pop     r12
0x1800830ab  pop     rdi
0x1800830ac  pop     rsi
0x1800830ad  pop     rbp
0x1800830ae  retn
```
