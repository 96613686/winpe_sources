# AudioServerGetMixFormat

- ea: `0x1800835c0`
- end: `0x180083c82`
- name: `AudioServerGetMixFormat`
- size: `1730`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000402c`
- `0x18000868c`
- `0x1800088dc`
- `0x18000accc`
- `0x18000af90`
- `0x18000e134`
- `0x1800128bc`
- `0x18001b3d0`
- `0x18001e7dc`
- `0x18001f6b0`
- `0x1800214d0`
- `0x180022fb0`
- `0x180025d64`
- `0x1800263c4`
- `0x180029d8c`
- `0x18002ca64`
- `0x18002e1f4`
- `0x18003191c`
- `0x18003cee0`
- `0x180046b40`
- `0x180046c3c`
- `0x18004ec10`
- `0x180050bc0`
- `0x180055f44`
- `0x180073310`
- `0x1800835c0`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18008361a`
- `ntdll!EtwEventActivityIdControl` at `0x180083c52`
- `ntdll!EtwEventActivityIdControl` at `0x18008361a`
- `ntdll!EtwEventActivityIdControl` at `0x180083c52`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800838de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800838de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008392e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008392e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c31`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x180083a2d`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x180083a2d`

## string_xrefs

- `0x180083baf`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c
__int64 __fastcall AudioServerGetMixFormat(__int64 a1, const unsigned __int16 *a2, __int128 *a3, _QWORD *a4)
{
  __int128 v5; // xmm0
  void *v9; // r14
  struct _FILETIME v10; // rbx
  __int64 v11; // rax
  int v12; // ecx
  void *v13; // r14
  struct _FILETIME v14; // rbx
  __int64 v15; // rax
  void *v16; // rcx
  int EndpointCharacteristicsDescriptor; // edi
  int v18; // r8d
  struct _GUID v19; // xmm6
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v20; // edx
  unsigned __int8 v21; // r14
  unsigned __int16 v22; // r8
  struct tWAVEFORMATEX *v23; // rax
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v24; // r8d
  int (__fastcall *v25)(struct IAudioPolicyManager *, __int64, __int64 *); // rbx
  __int64 v26; // rdx
  _DWORD *v27; // r8
  int v28; // r8d
  int v29; // r9d
  void *v30; // rcx
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v31; // edx
  unsigned int v32; // ebx
  void *v33; // rax
  int v34; // eax
  void *v35; // rcx
  void *v36; // rcx
  BOOL pdwType; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  void *Src; // [rsp+88h] [rbp-78h] BYREF
  int pvData; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+94h] [rbp-6Ch] BYREF
  void **p_Src; // [rsp+98h] [rbp-68h] BYREF
  struct tWAVEFORMATEX *v44; // [rsp+A0h] [rbp-60h] BYREF
  char v45; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v47; // [rsp+B8h] [rbp-48h] BYREF
  CEndpointCharacteristics *v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v52; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v53[2]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v54[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v55[2]; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID v56; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v5 = *a3;
  v55[0] = *(_QWORD *)a3;
  v55[1] = *((_QWORD *)a3 + 1);
  v54[1] = v5;
  EtwEventActivityIdControl(4, v55);
  v53[0] = 0;
  v52 = 0;
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
    std::unique_ptr<CWatchdogTimer<1>>::reset(v53, v11);
  }
  else
  {
    v13 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v13 )
    {
      v14 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v15 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v13, v14);
    }
    else
    {
      v15 = 0;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v52, v15);
  }
  Src = 0;
  *(_OWORD *)v48 = 0;
  v47 = 0;
  v54[0] = 0;
  v49 = 0;
  v56 = 0;
  v51 = 0;
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McTemplateU0zqttq_EtwEventWriteTransfer(
      v12,
      (unsigned int)&AudioSrv_GetMixFormat_Task_Start,
      (_DWORD)a2,
      *((_DWORD *)a3 + 12),
      *((_DWORD *)a3 + 14),
      *((_DWORD *)a3 + 17),
      *((_DWORD *)a3 + 13));
  *a4 = 0;
  EndpointCharacteristicsDescriptor = ValidateVadServerSettings((struct VadServerSettings *)a3);
  if ( EndpointCharacteristicsDescriptor >= 0 )
  {
    EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                          a2,
                                          0,
                                          (struct EndpointCharacteristicsDescriptor *)v48);
    if ( EndpointCharacteristicsDescriptor >= 0 )
    {
      wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>((char *)v48[0] + 40, &v51);
      pdwType = (*(__int64 (__fastcall **)(CEndpointCharacteristics *))(*(_QWORD *)v48[0] + 56LL))(v48[0]) == 1;
      EndpointCharacteristicsDescriptor = DeriveAudioProcessingModeConfiguration(
                                            *((unsigned int *)a3 + 12),
                                            *((unsigned int *)a3 + 14),
                                            *((unsigned int *)a3 + 32),
                                            v48);
      if ( EndpointCharacteristicsDescriptor >= 0 )
      {
        v19 = v56;
        v20 = *((_DWORD *)a3 + 13);
        p_Src = &Src;
        v44 = 0;
        v45 = 1;
        EndpointCharacteristicsDescriptor = EffectPack::GetMixFormat(v48[1], v20, &v56, &v44);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
        if ( EndpointCharacteristicsDescriptor >= 0 )
        {
          if ( *((_DWORD *)a3 + 35)
            && !(*(unsigned int (__fastcall **)(CEndpointCharacteristics *))(*(_QWORD *)v48[0] + 56LL))(v48[0])
            && !*((_DWORD *)a3 + 13)
            && *((_WORD *)Src + 1) == 2
            && !(unsigned int)ValidateUncompressedWaveFormatEx((const struct tWAVEFORMATEX *)Src)
            && dword_1801862A0[*((unsigned int *)a3 + 12)] )
          {
            if ( CEndpointCharacteristics::GetVirtualSurroundEffectMode(v48[0]) )
            {
              v21 = 1;
LABEL_25:
              p_Src = &pv;
              pv = 0;
              v44 = 0;
              v45 = 1;
              EndpointCharacteristicsDescriptor = CloneWaveFormat((const struct tWAVEFORMATEX *)Src, &v44);
              wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
              if ( EndpointCharacteristicsDescriptor < 0 )
              {
                v16 = pv;
                pv = 0;
                if ( v16 )
                  CoTaskMemFree(v16);
                goto LABEL_48;
              }
              *((_WORD *)pv + 1) = 8;
              v22 = 8 * (*((_WORD *)pv + 7) >> 3);
              *((_WORD *)pv + 6) = v22;
              *((_DWORD *)pv + 2) = *((_DWORD *)pv + 1) * v22;
              v23 = (struct tWAVEFORMATEX *)pv;
              if ( *(_WORD *)pv == 0xFFFE )
              {
                *((_DWORD *)pv + 5) = 1599;
                v23 = (struct tWAVEFORMATEX *)pv;
              }
              v24 = *((_DWORD *)a3 + 13);
              v56 = (struct _GUID)v54[0];
              if ( !(unsigned int)IsStreamFormatSupportedForMixFormat(
                                    (struct EndpointCharacteristicsDescriptor *)v48,
                                    &v56,
                                    v24,
                                    (const struct tWAVEFORMATEX *)Src,
                                    v23,
                                    0) )
              {
                v46 = 0;
                v25 = *(int (__fastcall **)(struct IAudioPolicyManager *, __int64, __int64 *))(*(_QWORD *)g_PolicyManager
                                                                                             + 32LL);
                wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::reset(&v46);
                if ( v25(g_PolicyManager, a1, &v46) >= 0 )
                {
                  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v46 + 504LL))(v46) )
                  {
                    v50 = 0;
                    p_Src = (void **)&v50;
                    v44 = 0;
                    v45 = 1;
                    mmdDevGetInstanceIdFromMMDeviceId(*((_QWORD *)v48[0] + 6), &v44);
                    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_Src);
                    v27 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
                    if ( *v27 > 4u && (unsigned __int8)tlgKeywordOn(v27, 512) )
                    {
                      *(_QWORD *)&v54[0] = v50;
                      pcbData = *((_DWORD *)a3 + 32);
                      pvData = v21;
                      *(_QWORD *)&v56.Data1 = 0x2000000;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                        v28,
                        (unsigned int)&unk_1801A59FA,
                        v28,
                        v29,
                        (__int64)&v56,
                        (__int64)&pvData,
                        (__int64)&pcbData,
                        (__int64)v54);
                    }
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v50);
                  }
                  LOBYTE(v26) = 1;
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 512LL))(v46, v26);
                  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
                    &Src,
                    &pv);
                }
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
              }
              v30 = pv;
              EndpointCharacteristicsDescriptor = 0;
              pv = 0;
              if ( v30 )
                CoTaskMemFree(v30);
              goto LABEL_41;
            }
            pvData = 0;
            pcbData = 4;
            v21 = 0;
            RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
              L"DisableGetMixFormatChange",
              0x20000018u,
              0,
              &pvData,
              &pcbData);
            if ( !pvData )
              goto LABEL_25;
          }
LABEL_41:
          v31 = *((_DWORD *)a3 + 13);
          p_Src = &v47;
          v44 = 0;
          v45 = 1;
          v56 = v19;
          v32 = (unsigned int)CEndpointCharacteristics::TryGetOverridingMixFormat(v48[0], v31, &v56, &v44) >> 31;
          wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
          if ( (unsigned __int8)v32 != 1 && v47 )
            wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
              &Src,
              &v47);
          v33 = MIDL_user_allocate(*((unsigned __int16 *)Src + 8) + 18LL);
          *a4 = v33;
          if ( v33 )
          {
            memcpy_0(v33, Src, *((unsigned __int16 *)Src + 8) + 18LL);
            v56 = *(struct _GUID *)*((_QWORD *)v48[1] + 196);
            v34 = PublishApoTelemetry(a2, &v56);
            if ( v34 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xE88,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
                (const char *)(unsigned int)v34,
                pdwType);
          }
          else
          {
            EndpointCharacteristicsDescriptor = -2147024882;
          }
        }
      }
    }
  }
LABEL_48:
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v16,
      (unsigned int)&AudioSrv_GetMixFormat_Task_Stop,
      v18,
      1,
      (__int64)&v56);
  if ( EndpointCharacteristicsDescriptor < 0 )
    AudSrvTraceLoggingErrorHelper("AudioServerGetMixFormat", 0xE8Cu, EndpointCharacteristicsDescriptor);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v48);
  v35 = v47;
  v47 = 0;
  if ( v35 )
    CoTaskMemFree(v35);
  v36 = Src;
  Src = 0;
  if ( v36 )
    CoTaskMemFree(v36);
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v52);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(v53);
  EtwEventActivityIdControl(4, v55);
  return (unsigned int)EndpointCharacteristicsDescriptor;
}

```

## disassembly

```asm
0x1800835c0  mov     rax, rsp
0x1800835c3  push    rbp
0x1800835c4  push    rbx
0x1800835c5  push    rsi
0x1800835c6  push    rdi
0x1800835c7  push    r12
0x1800835c9  push    r13
0x1800835cb  push    r14
0x1800835cd  push    r15
0x1800835cf  lea     rbp, [rsp-68h]
0x1800835d4  sub     rsp, 168h
0x1800835db  movaps  xmmword ptr [rax-58h], xmm6
0x1800835df  mov     rax, cs:__security_cookie
0x1800835e6  xor     rax, rsp
0x1800835e9  mov     [rbp+0A0h+var_60], rax
0x1800835ed  mov     rax, [r8]
0x1800835f0  mov     r15, rdx
0x1800835f3  movups  xmm0, xmmword ptr [r8]
0x1800835f7  mov     [rbp+0A0h+var_80], rax
0x1800835fb  lea     rdx, [rbp+0A0h+var_80]
0x1800835ff  mov     rax, [r8+8]
0x180083603  mov     r13, rcx
0x180083606  mov     ecx, 4
0x18008360b  mov     [rbp+0A0h+var_78], rax
0x18008360f  mov     r12, r9
0x180083612  mov     rsi, r8
0x180083615  movdqu  [rbp+0A0h+var_90], xmm0
0x18008361a  call    cs:__imp_EtwEventActivityIdControl
0x180083620  xor     ebx, ebx
0x180083622  mov     [rbp+0A0h+var_B0], rbx
0x180083626  mov     [rbp+0A0h+var_B8], rbx
0x18008362a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180083631  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180083636  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008363d  lea     ecx, [rbx+38h]; unsigned __int64
0x180083640  test    al, al
0x180083642  jz      short loc_180083693
0x180083644  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180083649  mov     r14, rax
0x18008364c  test    rax, rax
0x18008364f  jz      short loc_180083682
0x180083651  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180083658  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18008365e  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180083663  lea     r9, aAudioserverget_3; "AudioServerGetMixFormat"
0x18008366a  mov     [rsp+1A0h+pdwType], rbx; pftDueTime
0x18008366f  mov     r8d, edi
0x180083672  mov     rcx, r14; pv
0x180083675  mov     rdx, [rax+8]
0x180083679  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x18008367e  xor     ebx, ebx
0x180083680  jmp     short loc_180083685
0x180083682  mov     rax, rbx
0x180083685  mov     rdx, rax
0x180083688  lea     rcx, [rbp+0A0h+var_B0]
0x18008368c  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180083691  jmp     short loc_1800836E0
0x180083693  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180083698  mov     r14, rax
0x18008369b  test    rax, rax
0x18008369e  jz      short loc_1800836D1
0x1800836a0  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1800836a7  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x1800836ad  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800836b2  lea     r9, aAudioserverget_3; "AudioServerGetMixFormat"
0x1800836b9  mov     [rsp+1A0h+pdwType], rbx; pftDueTime
0x1800836be  mov     r8d, edi
0x1800836c1  mov     rcx, r14; pv
0x1800836c4  mov     rdx, [rax+8]
0x1800836c8  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x1800836cd  xor     ebx, ebx
0x1800836cf  jmp     short loc_1800836D4
0x1800836d1  mov     rax, rbx
0x1800836d4  mov     rdx, rax
0x1800836d7  lea     rcx, [rbp+0A0h+var_B8]
0x1800836db  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x1800836e0  test    cs:Microsoft_Windows_AudioEnableBits, 20h
0x1800836e7  xorps   xmm0, xmm0
0x1800836ea  xorps   xmm1, xmm1
0x1800836ed  mov     [rbp+0A0h+Src], rbx
0x1800836f1  movdqu  xmmword ptr [rbp+0A0h+var_E0], xmm0
0x1800836f6  mov     [rbp+0A0h+var_E8], rbx
0x1800836fa  movups  [rbp+0A0h+var_A0], xmm0
0x1800836fe  mov     [rbp+0A0h+var_D0], rbx
0x180083702  movups  xmmword ptr [rbp+0A0h+var_70.Data1], xmm1
0x180083706  mov     [rbp+0A0h+var_C0], rbx
0x18008370a  jz      short loc_180083734
0x18008370c  mov     eax, [rsi+34h]
0x18008370f  lea     rdx, AudioSrv_GetMixFormat_Task_Start
0x180083716  mov     r9d, [rsi+30h]
0x18008371a  mov     r8, r15
0x18008371d  mov     dword ptr [rsp+1A0h+pcbData], eax
0x180083721  mov     eax, [rsi+44h]
0x180083724  mov     dword ptr [rsp+1A0h+pvData], eax
0x180083728  mov     eax, [rsi+38h]
0x18008372b  mov     dword ptr [rsp+1A0h+pdwType], eax
0x18008372f  call    McTemplateU0zqttq_EtwEventWriteTransfer
0x180083734  mov     rcx, rsi; struct VadServerSettings *
0x180083737  mov     [r12], rbx
0x18008373b  call    ?ValidateVadServerSettings@@YAJPEAUVadServerSettings@@@Z; ValidateVadServerSettings(VadServerSettings *)
0x180083740  mov     edi, eax
0x180083742  test    eax, eax
0x180083744  js      loc_180083BC3
0x18008374a  lea     r8, [rbp+0A0h+var_E0]; struct EndpointCharacteristicsDescriptor *
0x18008374e  xor     edx, edx; int
0x180083750  mov     rcx, r15; unsigned __int16 *
0x180083753  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x180083758  mov     edi, eax
0x18008375a  test    eax, eax
0x18008375c  js      loc_180083BC3
0x180083762  mov     rcx, [rbp+0A0h+var_E0]
0x180083766  lea     rdx, [rbp+0A0h+var_C0]
0x18008376a  add     rcx, 28h ; '('
0x18008376e  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x180083773  mov     rcx, [rbp+0A0h+var_E0]
0x180083777  mov     ebx, [rsi+34h]
0x18008377a  mov     rax, [rcx]
0x18008377d  mov     rax, [rax+38h]
0x180083781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083786  mov     r8d, [rsi+80h]
0x18008378d  lea     r9, [rbp+0A0h+var_E0]
0x180083791  xor     edx, edx
0x180083793  mov     [rsp+1A0h+var_128], rdx
0x180083798  mov     ecx, edx
0x18008379a  mov     [rsp+1A0h+var_130], rdx
0x18008379f  cmp     eax, 1
0x1800837a2  lea     rax, [rbp+0A0h+var_70]
0x1800837a6  mov     [rsp+1A0h+var_138], rax
0x1800837ab  setz    cl
0x1800837ae  lea     rax, [rbp+0A0h+var_A0]
0x1800837b2  mov     [rsp+1A0h+var_140], rax
0x1800837b7  mov     [rsp+1A0h+var_148], rdx
0x1800837bc  mov     [rsp+1A0h+var_150], rdx
0x1800837c1  mov     [rsp+1A0h+var_158], edx
0x1800837c5  mov     [rsp+1A0h+var_160], edx
0x1800837c9  mov     [rsp+1A0h+var_168], rdx
0x1800837ce  mov     edx, [rsi+38h]
0x1800837d1  mov     dword ptr [rsp+1A0h+pcbData], ebx
0x1800837d5  xor     ebx, ebx
0x1800837d7  mov     dword ptr [rsp+1A0h+pvData], ebx
0x1800837db  mov     dword ptr [rsp+1A0h+pdwType], ecx
0x1800837df  mov     ecx, [rsi+30h]
0x1800837e2  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x1800837e7  mov     edi, eax
0x1800837e9  test    eax, eax
0x1800837eb  js      loc_180083BC3
0x1800837f1  movaps  xmm6, xmmword ptr [rbp+0A0h+var_70.Data1]
0x1800837f5  lea     rax, [rbp+0A0h+Src]
0x1800837f9  mov     edx, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800837fc  lea     r9, [rbp+0A0h+var_100]; struct tWAVEFORMATEX **
0x180083800  mov     rcx, [rbp+0A0h+var_E0+8]; this
0x180083804  lea     r8, [rbp+0A0h+var_70]; struct _GUID
0x180083808  mov     [rbp+0A0h+var_108], rax
0x18008380c  movdqa  xmmword ptr [rbp+0A0h+var_70.Data1], xmm6
0x180083811  mov     [rbp+0A0h+var_100], rbx
0x180083815  mov     [rbp+0A0h+var_F8], 1
0x180083819  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18008381e  lea     rcx, [rbp+0A0h+var_108]
0x180083822  mov     edi, eax
0x180083824  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180083829  test    edi, edi
0x18008382b  js      loc_180083BC3
0x180083831  cmp     [rsi+8Ch], ebx
0x180083837  jz      loc_180083AFA
0x18008383d  mov     rcx, [rbp+0A0h+var_E0]
0x180083841  mov     rax, [rcx]
0x180083844  mov     rax, [rax+38h]
0x180083848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008384d  test    eax, eax
0x18008384f  jnz     loc_180083AFA
0x180083855  cmp     [rsi+34h], ebx
0x180083858  jnz     loc_180083AFA
0x18008385e  mov     rcx, [rbp+0A0h+Src]; struct tWAVEFORMATEX *
0x180083862  cmp     word ptr [rcx+2], 2
0x180083867  jnz     loc_180083AFA
0x18008386d  call    ?ValidateUncompressedWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x180083872  test    eax, eax
0x180083874  jnz     loc_180083AFA
0x18008387a  mov     eax, [rsi+30h]
0x18008387d  lea     rcx, dword_1801862A0
0x180083884  cmp     [rcx+rax*4], ebx
0x180083887  jz      loc_180083AFA
0x18008388d  mov     rcx, [rbp+0A0h+var_E0]; this
0x180083891  call    ?GetVirtualSurroundEffectMode@CEndpointCharacteristics@@QEAAIXZ; CEndpointCharacteristics::GetVirtualSurroundEffectMode(void)
0x180083896  test    eax, eax
0x180083898  jz      short loc_18008389F
0x18008389a  mov     r14b, 1
0x18008389d  jmp     short loc_1800838ED
0x18008389f  lea     rax, [rbp+0A0h+var_10C]
0x1800838a3  mov     [rbp+0A0h+var_110], ebx
0x1800838a6  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800838ab  lea     r8, aDisablegetmixf; "DisableGetMixFormatChange"
0x1800838b2  lea     rax, [rbp+0A0h+var_110]
0x1800838b6  mov     [rbp+0A0h+var_10C], 4
0x1800838bd  mov     [rsp+1A0h+pvData], rax; pvData
0x1800838c2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800838c9  mov     r9d, 20000018h; dwFlags
0x1800838cf  mov     [rsp+1A0h+pdwType], rbx; pdwType
0x1800838d4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800838db  mov     r14b, bl
0x1800838de  call    cs:__imp_RegGetValueW
0x1800838e4  cmp     [rbp+0A0h+var_110], ebx
0x1800838e7  jnz     loc_180083AFA
0x1800838ed  mov     rcx, [rbp+0A0h+Src]; Src
0x1800838f1  lea     rax, [rbp+0A0h+pv]
0x1800838f5  lea     rdx, [rbp+0A0h+var_100]; struct tWAVEFORMATEX **
0x1800838f9  mov     [rbp+0A0h+var_108], rax
0x1800838fd  mov     [rbp+0A0h+pv], rbx
0x180083901  mov     [rbp+0A0h+var_100], rbx
0x180083905  mov     [rbp+0A0h+var_F8], 1
0x180083909  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18008390e  lea     rcx, [rbp+0A0h+var_108]
0x180083912  mov     edi, eax
0x180083914  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180083919  test    edi, edi
0x18008391b  jns     short loc_180083939
0x18008391d  mov     rcx, [rbp+0A0h+pv]; pv
0x180083921  mov     [rbp+0A0h+pv], rbx
0x180083925  test    rcx, rcx
0x180083928  jz      loc_180083BC3
0x18008392e  call    cs:__imp_CoTaskMemFree
0x180083934  jmp     loc_180083BC3
0x180083939  mov     rax, [rbp+0A0h+pv]
0x18008393d  mov     edx, 8
0x180083942  mov     [rax+2], dx
0x180083946  mov     rax, [rbp+0A0h+pv]
0x18008394a  movzx   ecx, word ptr [rax+0Eh]
0x18008394e  shr     cx, 3
0x180083952  movzx   r8d, cx
0x180083956  imul    r8d, edx
0x18008395a  mov     [rax+0Ch], r8w
0x18008395f  mov     rax, [rbp+0A0h+pv]
0x180083963  movzx   ecx, r8w
0x180083967  imul    ecx, [rax+4]
0x18008396b  mov     [rax+8], ecx
0x18008396e  mov     ecx, 0FFFEh
0x180083973  mov     rax, [rbp+0A0h+pv]
0x180083977  cmp     [rax], cx
0x18008397a  jnz     short loc_180083987
0x18008397c  mov     dword ptr [rax+14h], 63Fh
0x180083983  mov     rax, [rbp+0A0h+pv]
0x180083987  movaps  xmm0, [rbp+0A0h+var_A0]
0x18008398b  lea     rdx, [rbp+0A0h+var_70]; struct _GUID
0x18008398f  mov     r9, [rbp+0A0h+Src]; struct tWAVEFORMATEX *
0x180083993  lea     rcx, [rbp+0A0h+var_E0]; struct EndpointCharacteristicsDescriptor *
0x180083997  mov     r8d, [rsi+34h]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18008399b  mov     [rsp+1A0h+pvData], rbx; struct tWAVEFORMATEX **
0x1800839a0  movdqa  xmmword ptr [rbp+0A0h+var_70.Data1], xmm0
0x1800839a5  mov     [rsp+1A0h+pdwType], rax; struct tWAVEFORMATEX *
0x1800839aa  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x1800839af  test    eax, eax
0x1800839b1  jnz     loc_180083AE5
0x1800839b7  mov     rax, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x1800839be  mov     [rbp+0A0h+var_F0], rbx
0x1800839c2  mov     rcx, [rax]
0x1800839c5  mov     rbx, [rcx+20h]
0x1800839c9  lea     rcx, [rbp+0A0h+var_F0]
0x1800839cd  call    ?reset@?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::reset(void)
0x1800839d2  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x1800839d9  lea     r8, [rbp+0A0h+var_F0]
0x1800839dd  mov     rdx, r13
0x1800839e0  mov     rax, rbx
0x1800839e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839e8  xor     ebx, ebx
0x1800839ea  test    eax, eax
0x1800839ec  js      loc_180083ADC
0x1800839f2  mov     rcx, [rbp+0A0h+var_F0]
0x1800839f6  mov     rax, [rcx]
0x1800839f9  mov     rax, [rax+1F8h]
0x180083a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a05  test    al, al
0x180083a07  jnz     loc_180083ABA
0x180083a0d  mov     rcx, [rbp+0A0h+var_E0]
0x180083a11  lea     rax, [rbp+0A0h+var_C8]
0x180083a15  mov     [rbp+0A0h+var_C8], rbx
0x180083a19  lea     rdx, [rbp+0A0h+var_100]
0x180083a1d  mov     [rbp+0A0h+var_108], rax
0x180083a21  mov     [rbp+0A0h+var_100], rbx
0x180083a25  mov     [rbp+0A0h+var_F8], 1
0x180083a29  mov     rcx, [rcx+30h]
0x180083a2d  call    cs:__imp_mmdDevGetInstanceIdFromMMDeviceId
0x180083a33  lea     rcx, [rbp+0A0h+var_108]
0x180083a37  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180083a3c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180083a41  mov     r8, [rax+8]
0x180083a45  mov     eax, [r8]
0x180083a48  cmp     eax, 4
0x180083a4b  jbe     short loc_180083AB1
0x180083a4d  mov     edx, 200h
0x180083a52  mov     rcx, r8
0x180083a55  call    _tlgKeywordOn
0x180083a5a  test    al, al
0x180083a5c  jz      short loc_180083AB1
0x180083a5e  mov     rax, [rbp+0A0h+var_C8]
0x180083a62  lea     rdx, unk_1801A59FA
0x180083a69  mov     qword ptr [rbp+0A0h+var_A0], rax
0x180083a6d  mov     rcx, r8
0x180083a70  mov     eax, [rsi+80h]
0x180083a76  mov     [rbp+0A0h+var_10C], eax
0x180083a79  movzx   eax, r14b
  ... truncated ...
```
