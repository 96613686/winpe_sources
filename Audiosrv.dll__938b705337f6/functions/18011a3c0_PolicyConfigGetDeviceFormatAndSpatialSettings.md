# PolicyConfigGetDeviceFormatAndSpatialSettings

- ea: `0x18011a3c0`
- end: `0x18011a7c2`
- name: `PolicyConfigGetDeviceFormatAndSpatialSettings`
- size: `1026`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800088dc`
- `0x18000af90`
- `0x1800126bc`
- `0x18001b3d0`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x180118448`
- `0x18011a3c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a5f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a5f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a789`

## string_xrefs

- `0x18011a4cc`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011a5c4`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011a42e`: `PolicyConfigGetDeviceFormatAndSpatialSettings`
- `0x18011a47b`: `PolicyConfigGetDeviceFormatAndSpatialSettings`

## pseudocode

```c
__int64 PolicyConfigGetDeviceFormatAndSpatialSettings(__int64 a1, __int64 a2, unsigned int a3, ...)
{
  void *v5; // rsi
  struct _FILETIME v6; // rbx
  __int64 v7; // rax
  void *v8; // rsi
  struct _FILETIME v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // ebx
  _QWORD *v13; // rax
  bool v14; // zf
  __int64 v15; // rax
  __int64 (__fastcall *v16)(CPolicyConfig *, __int64, _QWORD, __int64 *); // rax
  __int64 v17; // rdx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rax
  _OWORD *v22; // rdx
  _OWORD *v23; // rax
  unsigned int *v24; // rcx
  __int64 v25; // rax
  void *v26; // r9
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  int pftDueTime; // [rsp+28h] [rbp-A1h]
  LPVOID Src; // [rsp+48h] [rbp-81h] BYREF
  LPVOID v33; // [rsp+50h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-69h]
  __int64 v36; // [rsp+68h] [rbp-61h] BYREF
  __int64 v37; // [rsp+70h] [rbp-59h] BYREF
  LPVOID *v38; // [rsp+78h] [rbp-51h] BYREF
  int v39[2]; // [rsp+80h] [rbp-49h] BYREF
  char v40; // [rsp+88h] [rbp-41h]
  LPVOID *p_Src; // [rsp+90h] [rbp-39h] BYREF
  __int64 v42; // [rsp+98h] [rbp-31h] BYREF
  char v43; // [rsp+A0h] [rbp-29h]
  _QWORD v44[3]; // [rsp+A8h] [rbp-21h] BYREF
  char v45; // [rsp+C0h] [rbp-9h]
  LPVOID *v46; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v47; // [rsp+D0h] [rbp+7h] BYREF
  char v48; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+47h]
  _QWORD *v50; // [rsp+130h] [rbp+67h] BYREF
  va_list va; // [rsp+130h] [rbp+67h]
  _QWORD *v52; // [rsp+138h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+138h] [rbp+6Fh]
  unsigned int *v54; // [rsp+140h] [rbp+77h]
  _QWORD *v55; // [rsp+148h] [rbp+7Fh] BYREF
  va_list va2; // [rsp+148h] [rbp+7Fh]
  va_list va3; // [rsp+150h] [rbp+87h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v50 = va_arg(va1, _QWORD *);
  va_copy(va2, va1);
  v52 = va_arg(va2, _QWORD *);
  v54 = va_arg(va2, unsigned int *);
  va_copy(va3, va2);
  v55 = va_arg(va3, _QWORD *);
  v37 = 0;
  v36 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v5 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v5 )
    {
      v6 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v7 = CWatchdogTimer<1>::CWatchdogTimer<1>(v5, v6);
    }
    else
    {
      v7 = 0;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v37, v7);
  }
  else
  {
    v8 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v9 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v10 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v8, v9);
    }
    else
    {
      v10 = 0;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v36, v10);
  }
  if ( !v50 )
  {
    v11 = 2916;
LABEL_14:
    v12 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)0x80004003LL,
      pftDueTime);
    goto LABEL_47;
  }
  *v50 = 0;
  if ( !v52 )
  {
    v11 = 2919;
    goto LABEL_14;
  }
  *v52 = 0;
  v13 = v55;
  if ( v55 )
  {
    *v55 = 0;
    v13 = v55;
  }
  Src = 0;
  va_copy((va_list)v44, va);
  v14 = v13 == 0;
  v33 = 0;
  va_copy((va_list)&v44[1], va1);
  pv = 0;
  va_copy((va_list)&v44[2], va2);
  v35 = 0;
  v15 = *(_QWORD *)g_PolicyConfig;
  v42 = 0;
  v43 = 1;
  *(_QWORD *)v39 = 0;
  v16 = *(__int64 (__fastcall **)(CPolicyConfig *, __int64, _QWORD, __int64 *))(v15 + 272);
  v40 = 1;
  if ( v14 )
  {
    v38 = &v33;
    p_Src = &Src;
    v12 = v16(g_PolicyConfig, a2, a3, &v42);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v38);
    if ( v12 < 0 )
    {
      v17 = 2963;
      goto LABEL_20;
    }
  }
  else
  {
    v47 = 0;
    p_Src = &pv;
    v48 = 1;
    v38 = &v33;
    v46 = &Src;
    v12 = v16(g_PolicyConfig, a2, a3, &v47);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v46);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v38);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
    if ( v12 < 0 )
    {
      v17 = 2955;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)(unsigned int)v12,
        (int)v39);
      v18 = pv;
      pv = 0;
      if ( v18 )
        CoTaskMemFree(v18);
      v19 = v33;
      v33 = 0;
      if ( v19 )
        CoTaskMemFree(v19);
      v20 = Src;
      Src = 0;
      if ( v20 )
        CoTaskMemFree(v20);
      v45 = 0;
      lambda_4a543277d9c921e33bd9dfb8d5328f97_::operator()(v44);
      goto LABEL_47;
    }
  }
  v21 = MIDL_user_allocate(*((unsigned __int16 *)Src + 8) + 18LL);
  *v50 = v21;
  if ( !v21 )
  {
    v17 = 2969;
LABEL_38:
    v12 = -2147024882;
    goto LABEL_20;
  }
  memcpy_0(v21, Src, *((unsigned __int16 *)Src + 8) + 18LL);
  v22 = MIDL_user_allocate(0x48u);
  *v52 = v22;
  if ( !v22 )
  {
    v17 = 2973;
    goto LABEL_38;
  }
  v23 = v33;
  v24 = v54;
  *v22 = *(_OWORD *)v33;
  v22[1] = v23[1];
  v22[2] = v23[2];
  v22[3] = v23[3];
  *((_QWORD *)v22 + 8) = *((_QWORD *)v23 + 8);
  v25 = v35;
  if ( v24 )
    *v24 = v35;
  if ( v55 )
  {
    v26 = MIDL_user_allocate(834 * v25);
    *v55 = v26;
    if ( !v26 )
    {
      v17 = 2984;
      goto LABEL_38;
    }
    memcpy_0(v26, pv, 834LL * v35);
  }
  v27 = pv;
  pv = 0;
  if ( v27 )
    CoTaskMemFree(v27);
  v28 = v33;
  v33 = 0;
  if ( v28 )
    CoTaskMemFree(v28);
  v29 = Src;
  Src = 0;
  if ( v29 )
    CoTaskMemFree(v29);
  v12 = 0;
LABEL_47:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v36);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v37);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18011a3c0  mov     rax, rsp
0x18011a3c3  mov     [rax+8], rbx
0x18011a3c7  mov     [rax+10h], rsi
0x18011a3cb  mov     [rax+20h], r9
0x18011a3cf  push    rbp
0x18011a3d0  push    rdi
0x18011a3d1  push    r12
0x18011a3d3  push    r14
0x18011a3d5  push    r15
0x18011a3d7  lea     rbp, [rax-47h]
0x18011a3db  sub     rsp, 0E0h
0x18011a3e2  xor     r12d, r12d
0x18011a3e5  mov     r14d, r8d
0x18011a3e8  mov     [rbp+3Fh+var_98], r12
0x18011a3ec  mov     r15, rdx
0x18011a3ef  mov     [rbp+3Fh+var_A0], r12
0x18011a3f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x18011a3fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x18011a3ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011a406  lea     ecx, [r12+38h]; unsigned __int64
0x18011a40b  test    al, al
0x18011a40d  jz      short loc_18011A45C
0x18011a40f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011a414  mov     rsi, rax
0x18011a417  test    rax, rax
0x18011a41a  jz      short loc_18011A44B
0x18011a41c  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18011a423  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18011a429  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18011a42e  lea     r9, aPolicyconfigge_1; "PolicyConfigGetDeviceFormatAndSpatialSe"...
0x18011a435  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18011a43a  mov     r8d, edi
0x18011a43d  mov     rcx, rsi; pv
0x18011a440  mov     rdx, [rax+8]
0x18011a444  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x18011a449  jmp     short loc_18011A44E
0x18011a44b  mov     rax, r12
0x18011a44e  mov     rdx, rax
0x18011a451  lea     rcx, [rbp+3Fh+var_98]
0x18011a455  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x18011a45a  jmp     short loc_18011A4A7
0x18011a45c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011a461  mov     rsi, rax
0x18011a464  test    rax, rax
0x18011a467  jz      short loc_18011A498
0x18011a469  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18011a470  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18011a476  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18011a47b  lea     r9, aPolicyconfigge_1; "PolicyConfigGetDeviceFormatAndSpatialSe"...
0x18011a482  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18011a487  mov     r8d, edi
0x18011a48a  mov     rcx, rsi; pv
0x18011a48d  mov     rdx, [rax+8]
0x18011a491  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x18011a496  jmp     short loc_18011A49B
0x18011a498  mov     rax, r12
0x18011a49b  mov     rdx, rax
0x18011a49e  lea     rcx, [rbp+3Fh+var_A0]
0x18011a4a2  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x18011a4a7  mov     rax, [rbp+3Fh+arg_18]
0x18011a4ab  test    rax, rax
0x18011a4ae  jnz     short loc_18011A4B7
0x18011a4b0  mov     edx, 0B64h
0x18011a4b5  jmp     short loc_18011A4C8
0x18011a4b7  mov     [rax], r12
0x18011a4ba  mov     rax, [rbp+3Fh+arg_20]
0x18011a4be  test    rax, rax
0x18011a4c1  jnz     short loc_18011A4E5
0x18011a4c3  mov     edx, 0B67h; void *
0x18011a4c8  mov     rcx, [rbp+47h]; this
0x18011a4cc  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011a4d3  mov     ebx, 80004003h
0x18011a4d8  mov     r9d, ebx; char *
0x18011a4db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a4e0  jmp     loc_18011A792
0x18011a4e5  mov     [rax], r12
0x18011a4e8  mov     rax, [rbp+3Fh+arg_30]
0x18011a4ec  test    rax, rax
0x18011a4ef  jz      short loc_18011A4F8
0x18011a4f1  mov     [rax], r12
0x18011a4f4  mov     rax, [rbp+3Fh+arg_30]
0x18011a4f8  lea     rcx, [rbp+3Fh+arg_18]
0x18011a4fc  mov     [rsp+100h+Src], r12
0x18011a501  mov     [rbp+3Fh+var_60], rcx
0x18011a505  test    rax, rax
0x18011a508  lea     rcx, [rbp+3Fh+arg_20]
0x18011a50c  mov     [rbp+3Fh+var_B8], r12
0x18011a510  mov     [rbp+3Fh+var_58], rcx
0x18011a514  mov     r8d, r14d
0x18011a517  lea     rcx, [rbp+3Fh+arg_30]
0x18011a51b  mov     [rbp+3Fh+pv], r12
0x18011a51f  mov     [rbp+3Fh+var_50], rcx
0x18011a523  mov     rcx, cs:?g_PolicyConfig@@3V?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CPolicyConfig> g_PolicyConfig
0x18011a52a  mov     [rbp+3Fh+var_A8], r12d
0x18011a52e  mov     rax, [rcx]
0x18011a531  mov     [rbp+3Fh+var_70], r12
0x18011a535  mov     [rbp+3Fh+var_68], 1
0x18011a539  mov     qword ptr [rbp+3Fh+var_88], r12
0x18011a53d  mov     rax, [rax+110h]
0x18011a544  mov     [rbp+3Fh+var_80], 1
0x18011a548  jz      loc_18011A620
0x18011a54e  lea     rdx, [rbp+3Fh+pv]
0x18011a552  mov     [rbp+3Fh+var_38], r12
0x18011a556  mov     [rbp+3Fh+var_78], rdx
0x18011a55a  lea     r9, [rbp+3Fh+var_38]
0x18011a55e  lea     rdx, [rbp+3Fh+var_B8]
0x18011a562  mov     [rbp+3Fh+var_30], 1
0x18011a566  mov     [rbp+3Fh+var_90], rdx
0x18011a56a  lea     rdx, [rsp+100h+Src]
0x18011a56f  mov     [rbp+3Fh+var_40], rdx
0x18011a573  lea     rdx, [rbp+3Fh+var_70]
0x18011a577  mov     [rsp+100h+var_D0], rdx
0x18011a57c  lea     rdx, [rbp+3Fh+var_A8]
0x18011a580  mov     [rsp+100h+var_D8], rdx
0x18011a585  lea     rdx, [rbp+3Fh+var_88]
0x18011a589  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rdx; int
0x18011a58e  mov     rdx, r15
0x18011a591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a596  lea     rcx, [rbp+3Fh+var_40]
0x18011a59a  mov     ebx, eax
0x18011a59c  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a5a1  lea     rcx, [rbp+3Fh+var_90]
0x18011a5a5  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a5aa  lea     rcx, [rbp+3Fh+var_78]
0x18011a5ae  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a5b3  test    ebx, ebx
0x18011a5b5  jns     loc_18011A676
0x18011a5bb  mov     edx, 0B8Bh; void *
0x18011a5c0  mov     rcx, [rbp+47h]; this
0x18011a5c4  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011a5cb  mov     r9d, ebx; char *
0x18011a5ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a5d3  mov     rcx, [rbp+3Fh+pv]; pv
0x18011a5d7  mov     [rbp+3Fh+pv], r12
0x18011a5db  test    rcx, rcx
0x18011a5de  jz      short loc_18011A5E6
0x18011a5e0  call    cs:__imp_CoTaskMemFree
0x18011a5e6  mov     rcx, [rbp+3Fh+var_B8]; pv
0x18011a5ea  mov     [rbp+3Fh+var_B8], r12
0x18011a5ee  test    rcx, rcx
0x18011a5f1  jz      short loc_18011A5F9
0x18011a5f3  call    cs:__imp_CoTaskMemFree
0x18011a5f9  mov     rcx, [rsp+100h+Src]; pv
0x18011a5fe  mov     [rsp+100h+Src], r12
0x18011a603  test    rcx, rcx
0x18011a606  jz      short loc_18011A60E
0x18011a608  call    cs:__imp_CoTaskMemFree
0x18011a60e  lea     rcx, [rbp+3Fh+var_60]
0x18011a612  mov     [rbp+3Fh+var_48], r12b
0x18011a616  call    _lambda_4a543277d9c921e33bd9dfb8d5328f97___operator__
0x18011a61b  jmp     loc_18011A792
0x18011a620  lea     rdx, [rbp+3Fh+var_B8]
0x18011a624  mov     [rsp+100h+var_D0], r12
0x18011a629  mov     [rbp+3Fh+var_90], rdx
0x18011a62d  lea     r9, [rbp+3Fh+var_70]
0x18011a631  lea     rdx, [rsp+100h+Src]
0x18011a636  mov     [rbp+3Fh+var_78], rdx
0x18011a63a  lea     rdx, [rbp+3Fh+var_A8]
0x18011a63e  mov     [rsp+100h+var_D8], rdx
0x18011a643  lea     rdx, [rbp+3Fh+var_88]
0x18011a647  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rdx
0x18011a64c  mov     rdx, r15
0x18011a64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a654  lea     rcx, [rbp+3Fh+var_78]
0x18011a658  mov     ebx, eax
0x18011a65a  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a65f  lea     rcx, [rbp+3Fh+var_90]
0x18011a663  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a668  test    ebx, ebx
0x18011a66a  jns     short loc_18011A676
0x18011a66c  mov     edx, 0B93h
0x18011a671  jmp     loc_18011A5C0
0x18011a676  mov     rax, [rsp+100h+Src]
0x18011a67b  movzx   ecx, word ptr [rax+10h]
0x18011a67f  add     rcx, 12h; size
0x18011a683  call    MIDL_user_allocate
0x18011a688  mov     rcx, [rbp+3Fh+arg_18]
0x18011a68c  mov     [rcx], rax
0x18011a68f  test    rax, rax
0x18011a692  jnz     short loc_18011A69E
0x18011a694  mov     edx, 0B99h
0x18011a699  jmp     loc_18011A734
0x18011a69e  mov     rdx, [rsp+100h+Src]; Src
0x18011a6a3  mov     rcx, rax; void *
0x18011a6a6  movzx   r8d, word ptr [rdx+10h]
0x18011a6ab  add     r8, 12h; Size
0x18011a6af  call    memcpy_0
0x18011a6b4  mov     ecx, 48h ; 'H'; size
0x18011a6b9  call    MIDL_user_allocate
0x18011a6be  mov     rcx, [rbp+3Fh+arg_20]
0x18011a6c2  mov     rdx, rax
0x18011a6c5  mov     [rcx], rax
0x18011a6c8  test    rax, rax
0x18011a6cb  jnz     short loc_18011A6D4
0x18011a6cd  mov     edx, 0B9Dh
0x18011a6d2  jmp     short loc_18011A734
0x18011a6d4  mov     rax, [rbp+3Fh+var_B8]
0x18011a6d8  mov     rcx, [rbp+3Fh+arg_28]
0x18011a6dc  movups  xmm0, xmmword ptr [rax]
0x18011a6df  movups  xmmword ptr [rdx], xmm0
0x18011a6e2  movups  xmm1, xmmword ptr [rax+10h]
0x18011a6e6  movups  xmmword ptr [rdx+10h], xmm1
0x18011a6ea  movups  xmm0, xmmword ptr [rax+20h]
0x18011a6ee  movups  xmmword ptr [rdx+20h], xmm0
0x18011a6f2  movups  xmm1, xmmword ptr [rax+30h]
0x18011a6f6  movups  xmmword ptr [rdx+30h], xmm1
0x18011a6fa  movsd   xmm0, qword ptr [rax+40h]
0x18011a6ff  movsd   qword ptr [rdx+40h], xmm0
0x18011a704  mov     eax, [rbp+3Fh+var_A8]
0x18011a707  test    rcx, rcx
0x18011a70a  jz      short loc_18011A70E
0x18011a70c  mov     [rcx], eax
0x18011a70e  cmp     [rbp+3Fh+arg_30], r12
0x18011a712  jz      short loc_18011A754
0x18011a714  imul    rcx, rax, 342h; size
0x18011a71b  call    MIDL_user_allocate
0x18011a720  mov     rcx, [rbp+3Fh+arg_30]
0x18011a724  mov     r9, rax
0x18011a727  mov     [rcx], rax
0x18011a72a  test    rax, rax
0x18011a72d  jnz     short loc_18011A73E
0x18011a72f  mov     edx, 0BA8h
0x18011a734  mov     ebx, 8007000Eh
0x18011a739  jmp     loc_18011A5C0
0x18011a73e  mov     eax, [rbp+3Fh+var_A8]
0x18011a741  mov     rcx, r9; void *
0x18011a744  mov     rdx, [rbp+3Fh+pv]; Src
0x18011a748  imul    r8, rax, 342h; Size
0x18011a74f  call    memcpy_0
0x18011a754  mov     rcx, [rbp+3Fh+pv]; pv
0x18011a758  mov     [rbp+3Fh+pv], r12
0x18011a75c  test    rcx, rcx
0x18011a75f  jz      short loc_18011A767
0x18011a761  call    cs:__imp_CoTaskMemFree
0x18011a767  mov     rcx, [rbp+3Fh+var_B8]; pv
0x18011a76b  mov     [rbp+3Fh+var_B8], r12
0x18011a76f  test    rcx, rcx
0x18011a772  jz      short loc_18011A77A
0x18011a774  call    cs:__imp_CoTaskMemFree
0x18011a77a  mov     rcx, [rsp+100h+Src]; pv
0x18011a77f  mov     [rsp+100h+Src], r12
0x18011a784  test    rcx, rcx
0x18011a787  jz      short loc_18011A78F
0x18011a789  call    cs:__imp_CoTaskMemFree
0x18011a78f  mov     ebx, r12d
0x18011a792  lea     rcx, [rbp+3Fh+var_A0]
0x18011a796  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x18011a79b  lea     rcx, [rbp+3Fh+var_98]
0x18011a79f  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x18011a7a4  lea     r11, [rsp+100h+var_20]
0x18011a7ac  mov     eax, ebx
0x18011a7ae  mov     rbx, [r11+30h]
0x18011a7b2  mov     rsi, [r11+38h]
0x18011a7b6  mov     rsp, r11
0x18011a7b9  pop     r15
0x18011a7bb  pop     r14
0x18011a7bd  pop     r12
0x18011a7bf  pop     rdi
0x18011a7c0  pop     rbp
0x18011a7c1  retn
```
