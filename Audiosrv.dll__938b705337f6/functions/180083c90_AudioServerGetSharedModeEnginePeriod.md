# AudioServerGetSharedModeEnginePeriod

- ea: `0x180083c90`
- end: `0x18008417a`
- name: `AudioServerGetSharedModeEnginePeriod`
- size: `1258`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001e7dc`
- `0x18001fa40`
- `0x180025d64`
- `0x180045068`
- `0x180050bc0`
- `0x180055f44`
- `0x180083c90`
- `0x1800842f0`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x180121e04`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180083d16`
- `ntdll!EtwEventActivityIdControl` at `0x18008414a`
- `ntdll!EtwEventActivityIdControl` at `0x180083d16`
- `ntdll!EtwEventActivityIdControl` at `0x18008414a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008408c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008410b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008408c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008410b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084127`

## string_xrefs

- `0x180083df6`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180083e58`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180083eb4`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180083fe2`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x18008406b`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c
__int64 __fastcall AudioServerGetSharedModeEnginePeriod(
        __int64 a1,
        struct tWAVEFORMATEX *a2,
        __int128 *a3,
        struct tWAVEFORMATEX *a4,
        int a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  __int128 v11; // xmm0
  unsigned int *v12; // rdi
  __int64 v15; // rax
  void *v16; // rax
  void *v17; // r14
  struct _FILETIME v18; // rbx
  void *v19; // rax
  void *v20; // r14
  struct _FILETIME v21; // rbx
  int v22; // eax
  int IsFormatSupported; // ebx
  void *v24; // rcx
  int EndpointCharacteristicsDescriptor; // eax
  __int64 v26; // rdx
  __int64 v27; // rax
  struct _GUID v28; // xmm6
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v29; // edx
  void *v30; // rcx
  unsigned int *v31; // r13
  unsigned int *v32; // r12
  unsigned int *v33; // r14
  __int64 v34; // rdx
  int SharedModeEnginePeriodicity; // eax
  void *v36; // rcx
  void *v37; // r9
  unsigned int nSamplesPerSec; // r8d
  unsigned int v39; // edx
  __int64 v40; // r9
  __int64 v41; // r9
  __int64 v42; // r9
  void *v43; // rcx
  int pftDueTime; // [rsp+20h] [rbp-E0h]
  BOOL pftDueTimea; // [rsp+20h] [rbp-E0h]
  int pftDueTimeb; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+30h] [rbp-D0h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v50; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v51; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v52; // [rsp+A0h] [rbp-60h] BYREF
  char v53; // [rsp+B0h] [rbp-50h]
  __int128 v54; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v57[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v58; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int *v59; // [rsp+100h] [rbp+0h]
  unsigned int *v60; // [rsp+108h] [rbp+8h]
  unsigned int *v61; // [rsp+110h] [rbp+10h]
  LPVOID *v62; // [rsp+118h] [rbp+18h] BYREF
  struct tWAVEFORMATEX *v63; // [rsp+120h] [rbp+20h] BYREF
  char v64; // [rsp+128h] [rbp+28h]
  __int128 v65; // [rsp+130h] [rbp+30h]
  _QWORD v66[2]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v11 = *a3;
  v12 = a6;
  v61 = a7;
  v59 = a9;
  v66[0] = *(_QWORD *)a3;
  v15 = *((_QWORD *)a3 + 1);
  v60 = a8;
  v66[1] = v15;
  *(_QWORD *)&v51.Data1 = a6;
  v65 = v11;
  EtwEventActivityIdControl(4, v66);
  v57[0] = 0;
  v56 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v16 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( v16 )
    {
      v18 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v16 = (void *)CWatchdogTimer<1>::CWatchdogTimer<1>(v17, v18);
      v12 = *(unsigned int **)&v51.Data1;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(v57, v16);
  }
  else
  {
    v19 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v20 = v19;
    if ( v19 )
    {
      v21 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v19 = (void *)CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v20, v21);
      v12 = *(unsigned int **)&v51.Data1;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v56, v19);
  }
  v22 = ValidateVadServerSettings((struct VadServerSettings *)a3);
  IsFormatSupported = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF8,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)v22,
      pftDueTime);
    goto LABEL_35;
  }
  pv = 0;
  *(_QWORD *)&v52.Data1 = &pv;
  *(_QWORD *)v52.Data4 = 0;
  v53 = 1;
  IsFormatSupported = AudioServerIsFormatSupported(a1, a2, 0, a3, a4, (struct tWAVEFORMATEX **)v52.Data4);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v52);
  if ( IsFormatSupported < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFFC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)IsFormatSupported,
      pftDueTimea);
LABEL_12:
    v24 = pv;
    pv = 0;
LABEL_13:
    if ( v24 )
      CoTaskMemFree(v24);
    goto LABEL_35;
  }
  v55 = 0;
  v54 = 0;
  EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                        &a2->wFormatTag,
                                        0,
                                        (struct EndpointCharacteristicsDescriptor *)&v54);
  IsFormatSupported = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    v26 = 4095;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
      pftDueTimea);
LABEL_18:
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)&v54);
    goto LABEL_12;
  }
  v51 = 0;
  v27 = *(_QWORD *)v54;
  v58 = 0;
  v52 = 0;
  pftDueTimea = (*(__int64 (__fastcall **)(_QWORD))(v27 + 56))(v54) == 1;
  EndpointCharacteristicsDescriptor = DeriveAudioProcessingModeConfiguration(
                                        *((unsigned int *)a3 + 12),
                                        *((unsigned int *)a3 + 14),
                                        *((unsigned int *)a3 + 32),
                                        &v54);
  IsFormatSupported = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    v26 = 4117;
    goto LABEL_17;
  }
  v28 = v51;
  v29 = *((_DWORD *)a3 + 13);
  v62 = &v50;
  v48 = *((_DWORD *)a3 + 17);
  v50 = 0;
  v63 = 0;
  v64 = 1;
  IsFormatSupported = DeriveConnectorFormatFromStreamFormat(
                        (EffectPack **)&v54,
                        v29,
                        (IAudioMediaType *)a4,
                        &v52,
                        &v58,
                        &v51,
                        v48,
                        &v63);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v62);
  if ( IsFormatSupported < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101F,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)IsFormatSupported,
      pftDueTimeb);
    v30 = v50;
    v50 = 0;
    if ( v30 )
      CoTaskMemFree(v30);
    goto LABEL_18;
  }
  v31 = v59;
  v32 = v60;
  v33 = v61;
  v34 = *((unsigned int *)a3 + 13);
  v52 = v28;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(*((_QWORD *)&v54 + 1), v34, v50, &v52);
  IsFormatSupported = SharedModeEnginePeriodicity;
  if ( SharedModeEnginePeriodicity < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1021,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)(unsigned int)SharedModeEnginePeriodicity,
      a5 != 0);
    v36 = v50;
    v50 = 0;
    if ( v36 )
      CoTaskMemFree(v36);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)&v54);
    v24 = pv;
    pv = 0;
    goto LABEL_13;
  }
  v37 = v50;
  nSamplesPerSec = a4->nSamplesPerSec;
  v39 = *((_DWORD *)v50 + 1);
  if ( nSamplesPerSec != v39 )
  {
    *v12 = TranslateFrameCountBetweenSamplingRates(*v12, v39, nSamplesPerSec);
    *v33 = TranslateFrameCountBetweenSamplingRates(*v33, *(_DWORD *)(v40 + 4), a4->nSamplesPerSec);
    *v32 = TranslateFrameCountBetweenSamplingRates(*v32, *(_DWORD *)(v41 + 4), a4->nSamplesPerSec);
    *v31 = TranslateFrameCountBetweenSamplingRates(*v31, *(_DWORD *)(v42 + 4), a4->nSamplesPerSec);
  }
  v50 = 0;
  if ( v37 )
    CoTaskMemFree(v37);
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)&v54);
  v43 = pv;
  pv = 0;
  if ( v43 )
    CoTaskMemFree(v43);
  IsFormatSupported = 0;
LABEL_35:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v56);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(v57);
  EtwEventActivityIdControl(4, v66);
  return (unsigned int)IsFormatSupported;
}

```

## disassembly

```asm
0x180083c90  mov     rax, rsp
0x180083c93  push    rbp
0x180083c94  push    rbx
0x180083c95  push    rsi
0x180083c96  push    rdi
0x180083c97  push    r12
0x180083c99  push    r13
0x180083c9b  push    r14
0x180083c9d  push    r15
0x180083c9f  lea     rbp, [rsp-78h]
0x180083ca4  sub     rsp, 178h
0x180083cab  movaps  xmmword ptr [rax-58h], xmm6
0x180083caf  mov     rax, cs:__security_cookie
0x180083cb6  xor     rax, rsp
0x180083cb9  mov     [rbp+0B0h+var_60], rax
0x180083cbd  mov     rax, [rbp+0B0h+arg_30]
0x180083cc4  mov     r13, rcx
0x180083cc7  mov     rcx, [rbp+0B0h+arg_38]
0x180083cce  mov     r12, rdx
0x180083cd1  movups  xmm0, xmmword ptr [r8]
0x180083cd5  mov     rdi, [rbp+0B0h+arg_28]
0x180083cdc  lea     rdx, [rbp+0B0h+var_70]
0x180083ce0  mov     [rbp+0B0h+var_A0], rax
0x180083ce4  mov     r15, r9
0x180083ce7  mov     rax, [rbp+0B0h+arg_40]
0x180083cee  mov     rsi, r8
0x180083cf1  mov     [rbp+0B0h+var_B0], rax
0x180083cf5  mov     rax, [r8]
0x180083cf8  mov     [rbp+0B0h+var_70], rax
0x180083cfc  mov     rax, [r8+8]
0x180083d00  mov     [rbp+0B0h+var_A8], rcx
0x180083d04  mov     ecx, 4
0x180083d09  mov     [rbp+0B0h+var_68], rax
0x180083d0d  mov     qword ptr [rbp+0B0h+var_120.Data1], rdi
0x180083d11  movdqu  [rbp+0B0h+var_80], xmm0
0x180083d16  call    cs:__imp_EtwEventActivityIdControl
0x180083d1c  mov     [rbp+0B0h+var_D0], 0
0x180083d24  mov     [rbp+0B0h+var_D8], 0
0x180083d2c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180083d33  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180083d38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180083d3f  mov     ecx, 38h ; '8'; unsigned __int64
0x180083d44  test    al, al
0x180083d46  jz      short loc_180083D94
0x180083d48  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180083d4d  mov     r14, rax
0x180083d50  test    rax, rax
0x180083d53  jz      short loc_180083D86
0x180083d55  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180083d5c  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180083d62  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180083d67  lea     r9, aAudioserverget_14; "AudioServerGetSharedModeEnginePeriod"
0x180083d6e  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x180083d73  mov     r8d, edi
0x180083d76  mov     rcx, r14; pv
0x180083d79  mov     rdx, [rax+8]
0x180083d7d  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180083d82  mov     rdi, qword ptr [rbp+0B0h+var_120.Data1]
0x180083d86  mov     rdx, rax
0x180083d89  lea     rcx, [rbp+0B0h+var_D0]
0x180083d8d  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180083d92  jmp     short loc_180083DDE
0x180083d94  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180083d99  mov     r14, rax
0x180083d9c  test    rax, rax
0x180083d9f  jz      short loc_180083DD2
0x180083da1  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180083da8  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180083dae  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180083db3  lea     r9, aAudioserverget_14; "AudioServerGetSharedModeEnginePeriod"
0x180083dba  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], rbx; int
0x180083dbf  mov     r8d, edi
0x180083dc2  mov     rcx, r14; pv
0x180083dc5  mov     rdx, [rax+8]
0x180083dc9  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180083dce  mov     rdi, qword ptr [rbp+0B0h+var_120.Data1]
0x180083dd2  mov     rdx, rax
0x180083dd5  lea     rcx, [rbp+0B0h+var_D8]
0x180083dd9  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180083dde  mov     rcx, rsi; struct VadServerSettings *
0x180083de1  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x180083de6  xor     r14d, r14d
0x180083de9  mov     ebx, eax
0x180083deb  test    eax, eax
0x180083ded  jns     short loc_180083E0F
0x180083def  mov     rcx, [rbp+0B8h]; this
0x180083df6  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083dfd  mov     r9d, eax; char *
0x180083e00  mov     edx, 0FF8h; void *
0x180083e05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083e0a  jmp     loc_18008412F
0x180083e0f  lea     rax, [rbp+0B0h+pv]
0x180083e13  mov     [rbp+0B0h+pv], r14
0x180083e17  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x180083e1b  mov     r9, rsi
0x180083e1e  lea     rax, [rbp+0B0h+var_110.Data4]
0x180083e22  mov     qword ptr [rbp+0B0h+var_110.Data4], r14
0x180083e26  mov     [rsp+1B0h+var_188], rax
0x180083e2b  xor     r8d, r8d
0x180083e2e  mov     rdx, r12
0x180083e31  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], r15; int
0x180083e36  mov     rcx, r13
0x180083e39  mov     [rbp+0B0h+var_100], 1
0x180083e3d  call    AudioServerIsFormatSupported
0x180083e42  lea     rcx, [rbp+0B0h+var_110]
0x180083e46  mov     ebx, eax
0x180083e48  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180083e4d  test    ebx, ebx
0x180083e4f  jns     short loc_180083E88
0x180083e51  mov     rcx, [rbp+0B8h]; this
0x180083e58  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083e5f  mov     r9d, ebx; char *
0x180083e62  mov     edx, 0FFCh; void *
0x180083e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083e6c  mov     rcx, [rbp+0B0h+pv]; pv
0x180083e70  mov     [rbp+0B0h+pv], r14
0x180083e74  test    rcx, rcx
0x180083e77  jz      loc_18008412F
0x180083e7d  call    cs:__imp_CoTaskMemFree
0x180083e83  jmp     loc_18008412F
0x180083e88  xorps   xmm0, xmm0
0x180083e8b  mov     [rbp+0B0h+var_E0], r14
0x180083e8f  lea     r8, [rbp+0B0h+var_F0]; struct EndpointCharacteristicsDescriptor *
0x180083e93  xor     edx, edx; int
0x180083e95  mov     rcx, r12; unsigned __int16 *
0x180083e98  movdqu  [rbp+0B0h+var_F0], xmm0
0x180083e9d  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x180083ea2  mov     ebx, eax
0x180083ea4  test    eax, eax
0x180083ea6  jns     short loc_180083ECE
0x180083ea8  mov     edx, 0FFFh; void *
0x180083ead  mov     rcx, [rbp+0B8h]; this
0x180083eb4  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083ebb  mov     r9d, eax; char *
0x180083ebe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083ec3  lea     rcx, [rbp+0B0h+var_F0]; this
0x180083ec7  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x180083ecc  jmp     short loc_180083E6C
0x180083ece  mov     rcx, qword ptr [rbp+0B0h+var_F0]
0x180083ed2  xorps   xmm0, xmm0
0x180083ed5  mov     ebx, [rsi+34h]
0x180083ed8  xorps   xmm1, xmm1
0x180083edb  movups  xmmword ptr [rbp+0B0h+var_120.Data1], xmm0
0x180083edf  mov     rax, [rcx]
0x180083ee2  movups  xmmword ptr [rbp+0B0h+var_C0.Data1], xmm1
0x180083ee6  movups  xmmword ptr [rbp+0B0h+var_110.Data1], xmm0
0x180083eea  mov     rax, [rax+38h]
0x180083eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ef3  mov     r8d, [rsi+80h]
0x180083efa  lea     r9, [rbp+0B0h+var_F0]
0x180083efe  mov     edx, [rsi+38h]
0x180083f01  cmp     eax, 1
0x180083f04  mov     [rsp+1B0h+var_138], r14
0x180083f09  lea     rax, [rbp+0B0h+var_110]
0x180083f0d  mov     [rsp+1B0h+var_140], r14
0x180083f12  mov     ecx, r14d
0x180083f15  mov     [rsp+1B0h+var_148], rax
0x180083f1a  setz    cl
0x180083f1d  lea     rax, [rbp+0B0h+var_C0]
0x180083f21  mov     [rsp+1B0h+var_150], rax
0x180083f26  lea     rax, [rbp+0B0h+var_120]
0x180083f2a  mov     [rsp+1B0h+var_158], rax
0x180083f2f  mov     [rsp+1B0h+var_160], r14
0x180083f34  mov     [rsp+1B0h+var_168], r14d
0x180083f39  mov     dword ptr [rsp+1B0h+var_170], r14d
0x180083f3e  mov     [rsp+1B0h+var_178], r14
0x180083f43  mov     [rsp+1B0h+var_180], ebx
0x180083f47  mov     dword ptr [rsp+1B0h+var_188], r14d
0x180083f4c  mov     [rsp+1B0h+pftDueTime.dwLowDateTime], ecx
0x180083f50  mov     ecx, [rsi+30h]
0x180083f53  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x180083f58  mov     ebx, eax
0x180083f5a  test    eax, eax
0x180083f5c  jns     short loc_180083F68
0x180083f5e  mov     edx, 1015h
0x180083f63  jmp     loc_180083EAD
0x180083f68  movaps  xmm6, xmmword ptr [rbp+0B0h+var_120.Data1]
0x180083f6c  lea     rax, [rbp+0B0h+var_128]
0x180083f70  movaps  xmm0, xmmword ptr [rbp+0B0h+var_C0.Data1]
0x180083f74  lea     r9, [rbp+0B0h+var_110]; struct _GUID
0x180083f78  movaps  xmm1, xmmword ptr [rbp+0B0h+var_110.Data1]
0x180083f7c  lea     rcx, [rbp+0B0h+var_F0]; struct EndpointCharacteristicsDescriptor *
0x180083f80  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180083f83  mov     r8, r15; Src
0x180083f86  mov     [rbp+0B0h+var_98], rax
0x180083f8a  lea     rax, [rbp+0B0h+var_90]
0x180083f8e  mov     [rsp+1B0h+var_178], rax; struct tWAVEFORMATEX **
0x180083f93  mov     eax, [rsi+44h]
0x180083f96  mov     [rsp+1B0h+var_180], eax; int
0x180083f9a  lea     rax, [rbp+0B0h+var_120]
0x180083f9e  mov     [rsp+1B0h+var_188], rax; struct _GUID *
0x180083fa3  lea     rax, [rbp+0B0h+var_C0]
0x180083fa7  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], rax; int
0x180083fac  mov     [rbp+0B0h+var_128], r14
0x180083fb0  mov     [rbp+0B0h+var_90], r14
0x180083fb4  mov     [rbp+0B0h+var_88], 1
0x180083fb8  movdqa  xmmword ptr [rbp+0B0h+var_120.Data1], xmm6
0x180083fbd  movdqa  xmmword ptr [rbp+0B0h+var_C0.Data1], xmm0
0x180083fc2  movdqa  xmmword ptr [rbp+0B0h+var_110.Data1], xmm1
0x180083fc7  call    ?DeriveConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@33HPEAPEAU3@@Z; DeriveConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,_GUID,_GUID,int,tWAVEFORMATEX * *)
0x180083fcc  lea     rcx, [rbp+0B0h+var_98]
0x180083fd0  mov     ebx, eax
0x180083fd2  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180083fd7  test    ebx, ebx
0x180083fd9  jns     short loc_180084012
0x180083fdb  mov     rcx, [rbp+0B8h]; this
0x180083fe2  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083fe9  mov     r9d, ebx; char *
0x180083fec  mov     edx, 101Fh; void *
0x180083ff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083ff6  mov     rcx, [rbp+0B0h+var_128]; pv
0x180083ffa  mov     [rbp+0B0h+var_128], r14
0x180083ffe  test    rcx, rcx
0x180084001  jz      loc_180083EC3
0x180084007  call    cs:__imp_CoTaskMemFree
0x18008400d  jmp     loc_180083EC3
0x180084012  cmp     [rbp+0B0h+arg_20], r14d
0x180084019  lea     r9, [rbp+0B0h+var_110]
0x18008401d  mov     r13, [rbp+0B0h+var_B0]
0x180084021  mov     eax, r14d
0x180084024  mov     r12, [rbp+0B0h+var_A8]
0x180084028  setnz   al
0x18008402b  mov     r14, [rbp+0B0h+var_A0]
0x18008402f  mov     r8, [rbp+0B0h+var_128]
0x180084033  mov     edx, [rsi+34h]
0x180084036  mov     rcx, qword ptr [rbp+0B0h+var_F0+8]
0x18008403a  mov     [rsp+1B0h+var_170], r13
0x18008403f  mov     [rsp+1B0h+var_178], r12
0x180084044  mov     qword ptr [rsp+1B0h+var_180], r14
0x180084049  mov     [rsp+1B0h+var_188], rdi
0x18008404e  mov     [rsp+1B0h+pftDueTime.dwLowDateTime], eax; int
0x180084052  movdqa  xmmword ptr [rbp+0B0h+var_110.Data1], xmm6
0x180084057  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x18008405c  xor     esi, esi
0x18008405e  mov     ebx, eax
0x180084060  test    eax, eax
0x180084062  jns     short loc_1800840A8
0x180084064  mov     rcx, [rbp+0B8h]; this
0x18008406b  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180084072  mov     r9d, eax; char *
0x180084075  mov     edx, 1021h; void *
0x18008407a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008407f  mov     rcx, [rbp+0B0h+var_128]; pv
0x180084083  mov     [rbp+0B0h+var_128], rsi
0x180084087  test    rcx, rcx
0x18008408a  jz      short loc_180084092
0x18008408c  call    cs:__imp_CoTaskMemFree
0x180084092  lea     rcx, [rbp+0B0h+var_F0]; this
0x180084096  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18008409b  mov     rcx, [rbp+0B0h+pv]
0x18008409f  mov     [rbp+0B0h+pv], rsi
0x1800840a3  jmp     loc_180083E74
0x1800840a8  mov     r9, [rbp+0B0h+var_128]
0x1800840ac  mov     r8d, [r15+4]; unsigned int
0x1800840b0  mov     edx, [r9+4]; unsigned int
0x1800840b4  cmp     r8d, edx
0x1800840b7  jz      short loc_1800840FF
0x1800840b9  mov     ecx, [rdi]; unsigned int
0x1800840bb  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x1800840c0  mov     [rdi], eax
0x1800840c2  mov     ecx, [r14]; unsigned int
0x1800840c5  mov     r8d, [r15+4]; unsigned int
0x1800840c9  mov     edx, [r9+4]; unsigned int
0x1800840cd  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x1800840d2  mov     [r14], eax
0x1800840d5  mov     ecx, [r12]; unsigned int
0x1800840d9  mov     r8d, [r15+4]; unsigned int
0x1800840dd  mov     edx, [r9+4]; unsigned int
0x1800840e1  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x1800840e6  mov     [r12], eax
0x1800840ea  mov     ecx, [r13+0]; unsigned int
0x1800840ee  mov     r8d, [r15+4]; unsigned int
0x1800840f2  mov     edx, [r9+4]; unsigned int
0x1800840f6  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x1800840fb  mov     [r13+0], eax
0x1800840ff  mov     [rbp+0B0h+var_128], rsi
0x180084103  test    r9, r9
0x180084106  jz      short loc_180084111
0x180084108  mov     rcx, r9; pv
0x18008410b  call    cs:__imp_CoTaskMemFree
0x180084111  lea     rcx, [rbp+0B0h+var_F0]; this
0x180084115  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x18008411a  mov     rcx, [rbp+0B0h+pv]; pv
0x18008411e  mov     [rbp+0B0h+pv], rsi
0x180084122  test    rcx, rcx
0x180084125  jz      short loc_18008412D
0x180084127  call    cs:__imp_CoTaskMemFree
0x18008412d  mov     ebx, esi
0x18008412f  lea     rcx, [rbp+0B0h+var_D8]
0x180084133  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180084138  lea     rcx, [rbp+0B0h+var_D0]
0x18008413c  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180084141  lea     rdx, [rbp+0B0h+var_70]
0x180084145  mov     ecx, 4
0x18008414a  call    cs:__imp_EtwEventActivityIdControl
0x180084150  mov     eax, ebx
0x180084152  mov     rcx, [rbp+0B0h+var_60]
0x180084156  xor     rcx, rsp; StackCookie
0x180084159  call    __security_check_cookie
0x18008415e  movaps  xmm6, [rsp+1B0h+var_50]
  ... truncated ...
```
