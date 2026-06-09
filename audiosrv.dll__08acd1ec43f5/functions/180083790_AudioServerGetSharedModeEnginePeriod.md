# AudioServerGetSharedModeEnginePeriod

- ea: `0x180083790`
- end: `0x180083c7a`
- name: `AudioServerGetSharedModeEnginePeriod`
- size: `1258`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x18001b520`
- `0x18001e92c`
- `0x18001fb90`
- `0x180025eb4`
- `0x180044bd8`
- `0x180050730`
- `0x180055ab4`
- `0x180083790`
- `0x180083df0`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x180122054`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180083816`
- `ntdll!EtwEventActivityIdControl` at `0x180083c4a`
- `ntdll!EtwEventActivityIdControl` at `0x180083816`
- `ntdll!EtwEventActivityIdControl` at `0x180083c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008397d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008397d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c27`

## string_xrefs

- `0x1800838f6`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180083958`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800839b4`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180083ae2`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180083b6b`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x180083790  mov     rax, rsp
0x180083793  push    rbp
0x180083794  push    rbx
0x180083795  push    rsi
0x180083796  push    rdi
0x180083797  push    r12
0x180083799  push    r13
0x18008379b  push    r14
0x18008379d  push    r15
0x18008379f  lea     rbp, [rsp-78h]
0x1800837a4  sub     rsp, 178h
0x1800837ab  movaps  xmmword ptr [rax-58h], xmm6
0x1800837af  mov     rax, cs:__security_cookie
0x1800837b6  xor     rax, rsp
0x1800837b9  mov     [rbp+0B0h+var_60], rax
0x1800837bd  mov     rax, [rbp+0B0h+arg_30]
0x1800837c4  mov     r13, rcx
0x1800837c7  mov     rcx, [rbp+0B0h+arg_38]
0x1800837ce  mov     r12, rdx
0x1800837d1  movups  xmm0, xmmword ptr [r8]
0x1800837d5  mov     rdi, [rbp+0B0h+arg_28]
0x1800837dc  lea     rdx, [rbp+0B0h+var_70]
0x1800837e0  mov     [rbp+0B0h+var_A0], rax
0x1800837e4  mov     r15, r9
0x1800837e7  mov     rax, [rbp+0B0h+arg_40]
0x1800837ee  mov     rsi, r8
0x1800837f1  mov     [rbp+0B0h+var_B0], rax
0x1800837f5  mov     rax, [r8]
0x1800837f8  mov     [rbp+0B0h+var_70], rax
0x1800837fc  mov     rax, [r8+8]
0x180083800  mov     [rbp+0B0h+var_A8], rcx
0x180083804  mov     ecx, 4
0x180083809  mov     [rbp+0B0h+var_68], rax
0x18008380d  mov     qword ptr [rbp+0B0h+var_120.Data1], rdi
0x180083811  movdqu  [rbp+0B0h+var_80], xmm0
0x180083816  call    cs:__imp_EtwEventActivityIdControl
0x18008381c  mov     [rbp+0B0h+var_D0], 0
0x180083824  mov     [rbp+0B0h+var_D8], 0
0x18008382c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180083833  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180083838  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008383f  mov     ecx, 38h ; '8'; unsigned __int64
0x180083844  test    al, al
0x180083846  jz      short loc_180083894
0x180083848  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008384d  mov     r14, rax
0x180083850  test    rax, rax
0x180083853  jz      short loc_180083886
0x180083855  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18008385c  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180083862  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180083867  lea     r9, aAudioserverget_14; "AudioServerGetSharedModeEnginePeriod"
0x18008386e  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x180083873  mov     r8d, edi
0x180083876  mov     rcx, r14; pv
0x180083879  mov     rdx, [rax+8]
0x18008387d  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180083882  mov     rdi, qword ptr [rbp+0B0h+var_120.Data1]
0x180083886  mov     rdx, rax
0x180083889  lea     rcx, [rbp+0B0h+var_D0]
0x18008388d  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180083892  jmp     short loc_1800838DE
0x180083894  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180083899  mov     r14, rax
0x18008389c  test    rax, rax
0x18008389f  jz      short loc_1800838D2
0x1800838a1  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1800838a8  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x1800838ae  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800838b3  lea     r9, aAudioserverget_14; "AudioServerGetSharedModeEnginePeriod"
0x1800838ba  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], rbx; int
0x1800838bf  mov     r8d, edi
0x1800838c2  mov     rcx, r14; pv
0x1800838c5  mov     rdx, [rax+8]
0x1800838c9  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x1800838ce  mov     rdi, qword ptr [rbp+0B0h+var_120.Data1]
0x1800838d2  mov     rdx, rax
0x1800838d5  lea     rcx, [rbp+0B0h+var_D8]
0x1800838d9  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x1800838de  mov     rcx, rsi; struct VadServerSettings *
0x1800838e1  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x1800838e6  xor     r14d, r14d
0x1800838e9  mov     ebx, eax
0x1800838eb  test    eax, eax
0x1800838ed  jns     short loc_18008390F
0x1800838ef  mov     rcx, [rbp+0B8h]; this
0x1800838f6  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800838fd  mov     r9d, eax; char *
0x180083900  mov     edx, 0FF8h; void *
0x180083905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008390a  jmp     loc_180083C2F
0x18008390f  lea     rax, [rbp+0B0h+pv]
0x180083913  mov     [rbp+0B0h+pv], r14
0x180083917  mov     qword ptr [rbp+0B0h+var_110.Data1], rax
0x18008391b  mov     r9, rsi
0x18008391e  lea     rax, [rbp+0B0h+var_110.Data4]
0x180083922  mov     qword ptr [rbp+0B0h+var_110.Data4], r14
0x180083926  mov     [rsp+1B0h+var_188], rax
0x18008392b  xor     r8d, r8d
0x18008392e  mov     rdx, r12
0x180083931  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], r15; int
0x180083936  mov     rcx, r13
0x180083939  mov     [rbp+0B0h+var_100], 1
0x18008393d  call    AudioServerIsFormatSupported
0x180083942  lea     rcx, [rbp+0B0h+var_110]
0x180083946  mov     ebx, eax
0x180083948  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008394d  test    ebx, ebx
0x18008394f  jns     short loc_180083988
0x180083951  mov     rcx, [rbp+0B8h]; this
0x180083958  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18008395f  mov     r9d, ebx; char *
0x180083962  mov     edx, 0FFCh; void *
0x180083967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008396c  mov     rcx, [rbp+0B0h+pv]; pv
0x180083970  mov     [rbp+0B0h+pv], r14
0x180083974  test    rcx, rcx
0x180083977  jz      loc_180083C2F
0x18008397d  call    cs:__imp_CoTaskMemFree
0x180083983  jmp     loc_180083C2F
0x180083988  xorps   xmm0, xmm0
0x18008398b  mov     [rbp+0B0h+var_E0], r14
0x18008398f  lea     r8, [rbp+0B0h+var_F0]; struct EndpointCharacteristicsDescriptor *
0x180083993  xor     edx, edx; int
0x180083995  mov     rcx, r12; unsigned __int16 *
0x180083998  movdqu  [rbp+0B0h+var_F0], xmm0
0x18008399d  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x1800839a2  mov     ebx, eax
0x1800839a4  test    eax, eax
0x1800839a6  jns     short loc_1800839CE
0x1800839a8  mov     edx, 0FFFh; void *
0x1800839ad  mov     rcx, [rbp+0B8h]; this
0x1800839b4  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800839bb  mov     r9d, eax; char *
0x1800839be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800839c3  lea     rcx, [rbp+0B0h+var_F0]; this
0x1800839c7  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800839cc  jmp     short loc_18008396C
0x1800839ce  mov     rcx, qword ptr [rbp+0B0h+var_F0]
0x1800839d2  xorps   xmm0, xmm0
0x1800839d5  mov     ebx, [rsi+34h]
0x1800839d8  xorps   xmm1, xmm1
0x1800839db  movups  xmmword ptr [rbp+0B0h+var_120.Data1], xmm0
0x1800839df  mov     rax, [rcx]
0x1800839e2  movups  xmmword ptr [rbp+0B0h+var_C0.Data1], xmm1
0x1800839e6  movups  xmmword ptr [rbp+0B0h+var_110.Data1], xmm0
0x1800839ea  mov     rax, [rax+38h]
0x1800839ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839f3  mov     r8d, [rsi+80h]
0x1800839fa  lea     r9, [rbp+0B0h+var_F0]
0x1800839fe  mov     edx, [rsi+38h]
0x180083a01  cmp     eax, 1
0x180083a04  mov     [rsp+1B0h+var_138], r14
0x180083a09  lea     rax, [rbp+0B0h+var_110]
0x180083a0d  mov     [rsp+1B0h+var_140], r14
0x180083a12  mov     ecx, r14d
0x180083a15  mov     [rsp+1B0h+var_148], rax
0x180083a1a  setz    cl
0x180083a1d  lea     rax, [rbp+0B0h+var_C0]
0x180083a21  mov     [rsp+1B0h+var_150], rax
0x180083a26  lea     rax, [rbp+0B0h+var_120]
0x180083a2a  mov     [rsp+1B0h+var_158], rax
0x180083a2f  mov     [rsp+1B0h+var_160], r14
0x180083a34  mov     [rsp+1B0h+var_168], r14d
0x180083a39  mov     dword ptr [rsp+1B0h+var_170], r14d
0x180083a3e  mov     [rsp+1B0h+var_178], r14
0x180083a43  mov     [rsp+1B0h+var_180], ebx
0x180083a47  mov     dword ptr [rsp+1B0h+var_188], r14d
0x180083a4c  mov     [rsp+1B0h+pftDueTime.dwLowDateTime], ecx
0x180083a50  mov     ecx, [rsi+30h]
0x180083a53  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x180083a58  mov     ebx, eax
0x180083a5a  test    eax, eax
0x180083a5c  jns     short loc_180083A68
0x180083a5e  mov     edx, 1015h
0x180083a63  jmp     loc_1800839AD
0x180083a68  movaps  xmm6, xmmword ptr [rbp+0B0h+var_120.Data1]
0x180083a6c  lea     rax, [rbp+0B0h+var_128]
0x180083a70  movaps  xmm0, xmmword ptr [rbp+0B0h+var_C0.Data1]
0x180083a74  lea     r9, [rbp+0B0h+var_110]; struct _GUID
0x180083a78  movaps  xmm1, xmmword ptr [rbp+0B0h+var_110.Data1]
0x180083a7c  lea     rcx, [rbp+0B0h+var_F0]; struct EndpointCharacteristicsDescriptor *
0x180083a80  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180083a83  mov     r8, r15; Src
0x180083a86  mov     [rbp+0B0h+var_98], rax
0x180083a8a  lea     rax, [rbp+0B0h+var_90]
0x180083a8e  mov     [rsp+1B0h+var_178], rax; struct tWAVEFORMATEX **
0x180083a93  mov     eax, [rsi+44h]
0x180083a96  mov     [rsp+1B0h+var_180], eax; int
0x180083a9a  lea     rax, [rbp+0B0h+var_120]
0x180083a9e  mov     [rsp+1B0h+var_188], rax; struct _GUID *
0x180083aa3  lea     rax, [rbp+0B0h+var_C0]
0x180083aa7  mov     qword ptr [rsp+1B0h+pftDueTime.dwLowDateTime], rax; int
0x180083aac  mov     [rbp+0B0h+var_128], r14
0x180083ab0  mov     [rbp+0B0h+var_90], r14
0x180083ab4  mov     [rbp+0B0h+var_88], 1
0x180083ab8  movdqa  xmmword ptr [rbp+0B0h+var_120.Data1], xmm6
0x180083abd  movdqa  xmmword ptr [rbp+0B0h+var_C0.Data1], xmm0
0x180083ac2  movdqa  xmmword ptr [rbp+0B0h+var_110.Data1], xmm1
0x180083ac7  call    ?DeriveConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@33HPEAPEAU3@@Z; DeriveConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,_GUID,_GUID,int,tWAVEFORMATEX * *)
0x180083acc  lea     rcx, [rbp+0B0h+var_98]
0x180083ad0  mov     ebx, eax
0x180083ad2  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180083ad7  test    ebx, ebx
0x180083ad9  jns     short loc_180083B12
0x180083adb  mov     rcx, [rbp+0B8h]; this
0x180083ae2  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083ae9  mov     r9d, ebx; char *
0x180083aec  mov     edx, 101Fh; void *
0x180083af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083af6  mov     rcx, [rbp+0B0h+var_128]; pv
0x180083afa  mov     [rbp+0B0h+var_128], r14
0x180083afe  test    rcx, rcx
0x180083b01  jz      loc_1800839C3
0x180083b07  call    cs:__imp_CoTaskMemFree
0x180083b0d  jmp     loc_1800839C3
0x180083b12  cmp     [rbp+0B0h+arg_20], r14d
0x180083b19  lea     r9, [rbp+0B0h+var_110]
0x180083b1d  mov     r13, [rbp+0B0h+var_B0]
0x180083b21  mov     eax, r14d
0x180083b24  mov     r12, [rbp+0B0h+var_A8]
0x180083b28  setnz   al
0x180083b2b  mov     r14, [rbp+0B0h+var_A0]
0x180083b2f  mov     r8, [rbp+0B0h+var_128]
0x180083b33  mov     edx, [rsi+34h]
0x180083b36  mov     rcx, qword ptr [rbp+0B0h+var_F0+8]
0x180083b3a  mov     [rsp+1B0h+var_170], r13
0x180083b3f  mov     [rsp+1B0h+var_178], r12
0x180083b44  mov     qword ptr [rsp+1B0h+var_180], r14
0x180083b49  mov     [rsp+1B0h+var_188], rdi
0x180083b4e  mov     [rsp+1B0h+pftDueTime.dwLowDateTime], eax; int
0x180083b52  movdqa  xmmword ptr [rbp+0B0h+var_110.Data1], xmm6
0x180083b57  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x180083b5c  xor     esi, esi
0x180083b5e  mov     ebx, eax
0x180083b60  test    eax, eax
0x180083b62  jns     short loc_180083BA8
0x180083b64  mov     rcx, [rbp+0B8h]; this
0x180083b6b  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180083b72  mov     r9d, eax; char *
0x180083b75  mov     edx, 1021h; void *
0x180083b7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083b7f  mov     rcx, [rbp+0B0h+var_128]; pv
0x180083b83  mov     [rbp+0B0h+var_128], rsi
0x180083b87  test    rcx, rcx
0x180083b8a  jz      short loc_180083B92
0x180083b8c  call    cs:__imp_CoTaskMemFree
0x180083b92  lea     rcx, [rbp+0B0h+var_F0]; this
0x180083b96  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x180083b9b  mov     rcx, [rbp+0B0h+pv]
0x180083b9f  mov     [rbp+0B0h+pv], rsi
0x180083ba3  jmp     loc_180083974
0x180083ba8  mov     r9, [rbp+0B0h+var_128]
0x180083bac  mov     r8d, [r15+4]; unsigned int
0x180083bb0  mov     edx, [r9+4]; unsigned int
0x180083bb4  cmp     r8d, edx
0x180083bb7  jz      short loc_180083BFF
0x180083bb9  mov     ecx, [rdi]; unsigned int
0x180083bbb  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180083bc0  mov     [rdi], eax
0x180083bc2  mov     ecx, [r14]; unsigned int
0x180083bc5  mov     r8d, [r15+4]; unsigned int
0x180083bc9  mov     edx, [r9+4]; unsigned int
0x180083bcd  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180083bd2  mov     [r14], eax
0x180083bd5  mov     ecx, [r12]; unsigned int
0x180083bd9  mov     r8d, [r15+4]; unsigned int
0x180083bdd  mov     edx, [r9+4]; unsigned int
0x180083be1  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180083be6  mov     [r12], eax
0x180083bea  mov     ecx, [r13+0]; unsigned int
0x180083bee  mov     r8d, [r15+4]; unsigned int
0x180083bf2  mov     edx, [r9+4]; unsigned int
0x180083bf6  call    ?TranslateFrameCountBetweenSamplingRates@@YAIIII@Z; TranslateFrameCountBetweenSamplingRates(uint,uint,uint)
0x180083bfb  mov     [r13+0], eax
0x180083bff  mov     [rbp+0B0h+var_128], rsi
0x180083c03  test    r9, r9
0x180083c06  jz      short loc_180083C11
0x180083c08  mov     rcx, r9; pv
0x180083c0b  call    cs:__imp_CoTaskMemFree
0x180083c11  lea     rcx, [rbp+0B0h+var_F0]; this
0x180083c15  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x180083c1a  mov     rcx, [rbp+0B0h+pv]; pv
0x180083c1e  mov     [rbp+0B0h+pv], rsi
0x180083c22  test    rcx, rcx
0x180083c25  jz      short loc_180083C2D
0x180083c27  call    cs:__imp_CoTaskMemFree
0x180083c2d  mov     ebx, esi
0x180083c2f  lea     rcx, [rbp+0B0h+var_D8]
0x180083c33  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180083c38  lea     rcx, [rbp+0B0h+var_D0]
0x180083c3c  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180083c41  lea     rdx, [rbp+0B0h+var_70]
0x180083c45  mov     ecx, 4
0x180083c4a  call    cs:__imp_EtwEventActivityIdControl
0x180083c50  mov     eax, ebx
0x180083c52  mov     rcx, [rbp+0B0h+var_60]
0x180083c56  xor     rcx, rsp; StackCookie
0x180083c59  call    __security_check_cookie
0x180083c5e  movaps  xmm6, [rsp+1B0h+var_50]
  ... truncated ...
```
