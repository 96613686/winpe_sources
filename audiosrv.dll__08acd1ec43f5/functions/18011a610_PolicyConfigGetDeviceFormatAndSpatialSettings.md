# PolicyConfigGetDeviceFormatAndSpatialSettings

- ea: `0x18011a610`
- end: `0x18011aa12`
- name: `PolicyConfigGetDeviceFormatAndSpatialSettings`
- size: `1026`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008a2c`
- `0x18000b0e0`
- `0x18001280c`
- `0x18001b520`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x180118698`
- `0x18011a610`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a9c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a9d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a9c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a9d9`

## string_xrefs

- `0x18011a71c`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011a814`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011a67e`: `PolicyConfigGetDeviceFormatAndSpatialSettings`
- `0x18011a6cb`: `PolicyConfigGetDeviceFormatAndSpatialSettings`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x18011a610  mov     rax, rsp
0x18011a613  mov     [rax+8], rbx
0x18011a617  mov     [rax+10h], rsi
0x18011a61b  mov     [rax+20h], r9
0x18011a61f  push    rbp
0x18011a620  push    rdi
0x18011a621  push    r12
0x18011a623  push    r14
0x18011a625  push    r15
0x18011a627  lea     rbp, [rax-47h]
0x18011a62b  sub     rsp, 0E0h
0x18011a632  xor     r12d, r12d
0x18011a635  mov     r14d, r8d
0x18011a638  mov     [rbp+3Fh+var_98], r12
0x18011a63c  mov     r15, rdx
0x18011a63f  mov     [rbp+3Fh+var_A0], r12
0x18011a643  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x18011a64a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x18011a64f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011a656  lea     ecx, [r12+38h]; unsigned __int64
0x18011a65b  test    al, al
0x18011a65d  jz      short loc_18011A6AC
0x18011a65f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011a664  mov     rsi, rax
0x18011a667  test    rax, rax
0x18011a66a  jz      short loc_18011A69B
0x18011a66c  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18011a673  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18011a679  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18011a67e  lea     r9, aPolicyconfigge_1; "PolicyConfigGetDeviceFormatAndSpatialSe"...
0x18011a685  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18011a68a  mov     r8d, edi
0x18011a68d  mov     rcx, rsi; pv
0x18011a690  mov     rdx, [rax+8]
0x18011a694  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x18011a699  jmp     short loc_18011A69E
0x18011a69b  mov     rax, r12
0x18011a69e  mov     rdx, rax
0x18011a6a1  lea     rcx, [rbp+3Fh+var_98]
0x18011a6a5  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x18011a6aa  jmp     short loc_18011A6F7
0x18011a6ac  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011a6b1  mov     rsi, rax
0x18011a6b4  test    rax, rax
0x18011a6b7  jz      short loc_18011A6E8
0x18011a6b9  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18011a6c0  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18011a6c6  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18011a6cb  lea     r9, aPolicyconfigge_1; "PolicyConfigGetDeviceFormatAndSpatialSe"...
0x18011a6d2  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x18011a6d7  mov     r8d, edi
0x18011a6da  mov     rcx, rsi; pv
0x18011a6dd  mov     rdx, [rax+8]
0x18011a6e1  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x18011a6e6  jmp     short loc_18011A6EB
0x18011a6e8  mov     rax, r12
0x18011a6eb  mov     rdx, rax
0x18011a6ee  lea     rcx, [rbp+3Fh+var_A0]
0x18011a6f2  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x18011a6f7  mov     rax, [rbp+3Fh+arg_18]
0x18011a6fb  test    rax, rax
0x18011a6fe  jnz     short loc_18011A707
0x18011a700  mov     edx, 0B64h
0x18011a705  jmp     short loc_18011A718
0x18011a707  mov     [rax], r12
0x18011a70a  mov     rax, [rbp+3Fh+arg_20]
0x18011a70e  test    rax, rax
0x18011a711  jnz     short loc_18011A735
0x18011a713  mov     edx, 0B67h; void *
0x18011a718  mov     rcx, [rbp+47h]; this
0x18011a71c  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011a723  mov     ebx, 80004003h
0x18011a728  mov     r9d, ebx; char *
0x18011a72b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a730  jmp     loc_18011A9E2
0x18011a735  mov     [rax], r12
0x18011a738  mov     rax, [rbp+3Fh+arg_30]
0x18011a73c  test    rax, rax
0x18011a73f  jz      short loc_18011A748
0x18011a741  mov     [rax], r12
0x18011a744  mov     rax, [rbp+3Fh+arg_30]
0x18011a748  lea     rcx, [rbp+3Fh+arg_18]
0x18011a74c  mov     [rsp+100h+Src], r12
0x18011a751  mov     [rbp+3Fh+var_60], rcx
0x18011a755  test    rax, rax
0x18011a758  lea     rcx, [rbp+3Fh+arg_20]
0x18011a75c  mov     [rbp+3Fh+var_B8], r12
0x18011a760  mov     [rbp+3Fh+var_58], rcx
0x18011a764  mov     r8d, r14d
0x18011a767  lea     rcx, [rbp+3Fh+arg_30]
0x18011a76b  mov     [rbp+3Fh+pv], r12
0x18011a76f  mov     [rbp+3Fh+var_50], rcx
0x18011a773  mov     rcx, cs:?g_PolicyConfig@@3V?$ComPtr@VCPolicyConfig@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CPolicyConfig> g_PolicyConfig
0x18011a77a  mov     [rbp+3Fh+var_A8], r12d
0x18011a77e  mov     rax, [rcx]
0x18011a781  mov     [rbp+3Fh+var_70], r12
0x18011a785  mov     [rbp+3Fh+var_68], 1
0x18011a789  mov     qword ptr [rbp+3Fh+var_88], r12
0x18011a78d  mov     rax, [rax+110h]
0x18011a794  mov     [rbp+3Fh+var_80], 1
0x18011a798  jz      loc_18011A870
0x18011a79e  lea     rdx, [rbp+3Fh+pv]
0x18011a7a2  mov     [rbp+3Fh+var_38], r12
0x18011a7a6  mov     [rbp+3Fh+var_78], rdx
0x18011a7aa  lea     r9, [rbp+3Fh+var_38]
0x18011a7ae  lea     rdx, [rbp+3Fh+var_B8]
0x18011a7b2  mov     [rbp+3Fh+var_30], 1
0x18011a7b6  mov     [rbp+3Fh+var_90], rdx
0x18011a7ba  lea     rdx, [rsp+100h+Src]
0x18011a7bf  mov     [rbp+3Fh+var_40], rdx
0x18011a7c3  lea     rdx, [rbp+3Fh+var_70]
0x18011a7c7  mov     [rsp+100h+var_D0], rdx
0x18011a7cc  lea     rdx, [rbp+3Fh+var_A8]
0x18011a7d0  mov     [rsp+100h+var_D8], rdx
0x18011a7d5  lea     rdx, [rbp+3Fh+var_88]
0x18011a7d9  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rdx; int
0x18011a7de  mov     rdx, r15
0x18011a7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a7e6  lea     rcx, [rbp+3Fh+var_40]
0x18011a7ea  mov     ebx, eax
0x18011a7ec  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a7f1  lea     rcx, [rbp+3Fh+var_90]
0x18011a7f5  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a7fa  lea     rcx, [rbp+3Fh+var_78]
0x18011a7fe  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a803  test    ebx, ebx
0x18011a805  jns     loc_18011A8C6
0x18011a80b  mov     edx, 0B8Bh; void *
0x18011a810  mov     rcx, [rbp+47h]; this
0x18011a814  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011a81b  mov     r9d, ebx; char *
0x18011a81e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a823  mov     rcx, [rbp+3Fh+pv]; pv
0x18011a827  mov     [rbp+3Fh+pv], r12
0x18011a82b  test    rcx, rcx
0x18011a82e  jz      short loc_18011A836
0x18011a830  call    cs:__imp_CoTaskMemFree
0x18011a836  mov     rcx, [rbp+3Fh+var_B8]; pv
0x18011a83a  mov     [rbp+3Fh+var_B8], r12
0x18011a83e  test    rcx, rcx
0x18011a841  jz      short loc_18011A849
0x18011a843  call    cs:__imp_CoTaskMemFree
0x18011a849  mov     rcx, [rsp+100h+Src]; pv
0x18011a84e  mov     [rsp+100h+Src], r12
0x18011a853  test    rcx, rcx
0x18011a856  jz      short loc_18011A85E
0x18011a858  call    cs:__imp_CoTaskMemFree
0x18011a85e  lea     rcx, [rbp+3Fh+var_60]
0x18011a862  mov     [rbp+3Fh+var_48], r12b
0x18011a866  call    _lambda_4a543277d9c921e33bd9dfb8d5328f97___operator__
0x18011a86b  jmp     loc_18011A9E2
0x18011a870  lea     rdx, [rbp+3Fh+var_B8]
0x18011a874  mov     [rsp+100h+var_D0], r12
0x18011a879  mov     [rbp+3Fh+var_90], rdx
0x18011a87d  lea     r9, [rbp+3Fh+var_70]
0x18011a881  lea     rdx, [rsp+100h+Src]
0x18011a886  mov     [rbp+3Fh+var_78], rdx
0x18011a88a  lea     rdx, [rbp+3Fh+var_A8]
0x18011a88e  mov     [rsp+100h+var_D8], rdx
0x18011a893  lea     rdx, [rbp+3Fh+var_88]
0x18011a897  mov     qword ptr [rsp+100h+pftDueTime.dwLowDateTime], rdx
0x18011a89c  mov     rdx, r15
0x18011a89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011a8a4  lea     rcx, [rbp+3Fh+var_78]
0x18011a8a8  mov     ebx, eax
0x18011a8aa  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a8af  lea     rcx, [rbp+3Fh+var_90]
0x18011a8b3  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18011a8b8  test    ebx, ebx
0x18011a8ba  jns     short loc_18011A8C6
0x18011a8bc  mov     edx, 0B93h
0x18011a8c1  jmp     loc_18011A810
0x18011a8c6  mov     rax, [rsp+100h+Src]
0x18011a8cb  movzx   ecx, word ptr [rax+10h]
0x18011a8cf  add     rcx, 12h; size
0x18011a8d3  call    MIDL_user_allocate
0x18011a8d8  mov     rcx, [rbp+3Fh+arg_18]
0x18011a8dc  mov     [rcx], rax
0x18011a8df  test    rax, rax
0x18011a8e2  jnz     short loc_18011A8EE
0x18011a8e4  mov     edx, 0B99h
0x18011a8e9  jmp     loc_18011A984
0x18011a8ee  mov     rdx, [rsp+100h+Src]; Src
0x18011a8f3  mov     rcx, rax; void *
0x18011a8f6  movzx   r8d, word ptr [rdx+10h]
0x18011a8fb  add     r8, 12h; Size
0x18011a8ff  call    memcpy_0
0x18011a904  mov     ecx, 48h ; 'H'; size
0x18011a909  call    MIDL_user_allocate
0x18011a90e  mov     rcx, [rbp+3Fh+arg_20]
0x18011a912  mov     rdx, rax
0x18011a915  mov     [rcx], rax
0x18011a918  test    rax, rax
0x18011a91b  jnz     short loc_18011A924
0x18011a91d  mov     edx, 0B9Dh
0x18011a922  jmp     short loc_18011A984
0x18011a924  mov     rax, [rbp+3Fh+var_B8]
0x18011a928  mov     rcx, [rbp+3Fh+arg_28]
0x18011a92c  movups  xmm0, xmmword ptr [rax]
0x18011a92f  movups  xmmword ptr [rdx], xmm0
0x18011a932  movups  xmm1, xmmword ptr [rax+10h]
0x18011a936  movups  xmmword ptr [rdx+10h], xmm1
0x18011a93a  movups  xmm0, xmmword ptr [rax+20h]
0x18011a93e  movups  xmmword ptr [rdx+20h], xmm0
0x18011a942  movups  xmm1, xmmword ptr [rax+30h]
0x18011a946  movups  xmmword ptr [rdx+30h], xmm1
0x18011a94a  movsd   xmm0, qword ptr [rax+40h]
0x18011a94f  movsd   qword ptr [rdx+40h], xmm0
0x18011a954  mov     eax, [rbp+3Fh+var_A8]
0x18011a957  test    rcx, rcx
0x18011a95a  jz      short loc_18011A95E
0x18011a95c  mov     [rcx], eax
0x18011a95e  cmp     [rbp+3Fh+arg_30], r12
0x18011a962  jz      short loc_18011A9A4
0x18011a964  imul    rcx, rax, 342h; size
0x18011a96b  call    MIDL_user_allocate
0x18011a970  mov     rcx, [rbp+3Fh+arg_30]
0x18011a974  mov     r9, rax
0x18011a977  mov     [rcx], rax
0x18011a97a  test    rax, rax
0x18011a97d  jnz     short loc_18011A98E
0x18011a97f  mov     edx, 0BA8h
0x18011a984  mov     ebx, 8007000Eh
0x18011a989  jmp     loc_18011A810
0x18011a98e  mov     eax, [rbp+3Fh+var_A8]
0x18011a991  mov     rcx, r9; void *
0x18011a994  mov     rdx, [rbp+3Fh+pv]; Src
0x18011a998  imul    r8, rax, 342h; Size
0x18011a99f  call    memcpy_0
0x18011a9a4  mov     rcx, [rbp+3Fh+pv]; pv
0x18011a9a8  mov     [rbp+3Fh+pv], r12
0x18011a9ac  test    rcx, rcx
0x18011a9af  jz      short loc_18011A9B7
0x18011a9b1  call    cs:__imp_CoTaskMemFree
0x18011a9b7  mov     rcx, [rbp+3Fh+var_B8]; pv
0x18011a9bb  mov     [rbp+3Fh+var_B8], r12
0x18011a9bf  test    rcx, rcx
0x18011a9c2  jz      short loc_18011A9CA
0x18011a9c4  call    cs:__imp_CoTaskMemFree
0x18011a9ca  mov     rcx, [rsp+100h+Src]; pv
0x18011a9cf  mov     [rsp+100h+Src], r12
0x18011a9d4  test    rcx, rcx
0x18011a9d7  jz      short loc_18011A9DF
0x18011a9d9  call    cs:__imp_CoTaskMemFree
0x18011a9df  mov     ebx, r12d
0x18011a9e2  lea     rcx, [rbp+3Fh+var_A0]
0x18011a9e6  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x18011a9eb  lea     rcx, [rbp+3Fh+var_98]
0x18011a9ef  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x18011a9f4  lea     r11, [rsp+100h+var_20]
0x18011a9fc  mov     eax, ebx
0x18011a9fe  mov     rbx, [r11+30h]
0x18011aa02  mov     rsi, [r11+38h]
0x18011aa06  mov     rsp, r11
0x18011aa09  pop     r15
0x18011aa0b  pop     r14
0x18011aa0d  pop     r12
0x18011aa0f  pop     rdi
0x18011aa10  pop     rbp
0x18011aa11  retn
```
