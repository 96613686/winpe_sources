# s_apmSetPersistedDefaultAudioEndpoint

- ea: `0x180112060`
- end: `0x180112449`
- name: `s_apmSetPersistedDefaultAudioEndpoint`
- size: `1001`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE Binding@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x18001b520`
- `0x1800424ec`
- `0x1800a4af8`
- `0x1800cbfcc`
- `0x1800cddac`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x180112060`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180112172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180112172`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18011214b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18011214b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011233d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011233d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011230a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801123cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011230a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801123cf`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x180112274`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x180112274`

## string_xrefs

- `0x18011215c`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x1801121dc`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180112236`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180112287`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x1801122ec`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180112350`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x18011239f`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180112411`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_apmSetPersistedDefaultAudioEndpoint(
        RPC_BINDING_HANDLE Binding,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  void *v9; // rax
  void *v10; // rsi
  struct _FILETIME v11; // rbx
  void *v12; // rax
  void *v13; // rsi
  struct _FILETIME v14; // rbx
  unsigned int v15; // eax
  int v16; // ebx
  bool v17; // dl
  char v18; // al
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v23; // edi
  int MMDeviceFromInterfaceId; // eax
  __int64 v25; // rax
  void *v26; // rcx
  HRESULT v27; // eax
  unsigned __int64 i; // rbx
  int v29; // eax
  void *v30; // rcx
  __int64 v32; // rdx
  unsigned int ppv; // [rsp+20h] [rbp-61h]
  int ppva; // [rsp+20h] [rbp-61h]
  __int64 *v35; // [rsp+30h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-49h] BYREF
  __int64 v37; // [rsp+40h] [rbp-41h] BYREF
  unsigned int Pid; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int64 v39; // [rsp+50h] [rbp-31h] BYREF
  LPVOID v40; // [rsp+58h] [rbp-29h] BYREF
  __int64 v41; // [rsp+60h] [rbp-21h] BYREF
  __int64 v42; // [rsp+68h] [rbp-19h] BYREF
  LPVOID *p_pv; // [rsp+70h] [rbp-11h] BYREF
  __int64 v44; // [rsp+78h] [rbp-9h] BYREF
  char v45; // [rsp+80h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v42 = 0;
  v41 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v9 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
    {
      v11 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v9 = (void *)CWatchdogTimer<1>::CWatchdogTimer<1>(v10, v11);
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v42, v9);
  }
  else
  {
    v12 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( v12 )
    {
      v14 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v12 = (void *)CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v13, v14);
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v41, v12);
  }
  Pid = 0;
  v15 = I_RpcBindingInqLocalClientPID(Binding, &Pid);
  if ( !v15 )
  {
    v17 = Pid == GetCurrentProcessId();
    if ( !g_ADGProcess || (v18 = 1, Pid != LODWORD(g_ADGProcess[2].OwningThread)) )
      v18 = 0;
    if ( v17 || v18 )
    {
      v32 = 88;
    }
    else
    {
      if ( a4 <= 2 )
      {
        v35 = 0;
        v19 = (*(__int64 (__fastcall **)(struct IAudioPolicyManager *, _QWORD, __int64 **))(*(_QWORD *)g_PolicyManager
                                                                                          + 40LL))(
                g_PolicyManager,
                a2,
                &v35);
        v16 = v19;
        if ( v19 < 0 )
        {
          v20 = (unsigned int)v19;
          v21 = 98;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
            (const char *)v20,
            ppv);
LABEL_19:
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v35);
          goto LABEL_46;
        }
        if ( !v35 )
        {
          v16 = -2147024809;
          v20 = 2147942487LL;
          v21 = 99;
          goto LABEL_18;
        }
        v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(*v35 + 24))(v35, a3, a4, a5);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
            (const char *)(unsigned int)v22,
            ppv);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v35);
          v16 = v23;
          goto LABEL_46;
        }
        v37 = 0;
        if ( a5 )
        {
          wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v37);
          MMDeviceFromInterfaceId = mmdDevGetMMDeviceFromInterfaceId(a5, &v37);
          v16 = MMDeviceFromInterfaceId;
          if ( MMDeviceFromInterfaceId < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6C,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
              (const char *)(unsigned int)MMDeviceFromInterfaceId,
              ppv);
LABEL_27:
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v37);
            goto LABEL_19;
          }
          v39 = 0;
          pv = 0;
          v25 = *v35;
          p_pv = &pv;
          v44 = 0;
          v45 = 1;
          v16 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64 *, __int64 *))(v25 + 56))(v35, &v39, &v44);
          wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
          if ( v16 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x72,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
              (const char *)(unsigned int)v16,
              ppv);
            goto LABEL_30;
          }
          if ( v39 )
          {
            v40 = 0;
            v27 = CoCreateInstance(
                    &GUID_06cca63e_9941_441b_b004_39f999ada412,
                    0,
                    0x17u,
                    &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
                    &v40);
            v16 = v27;
            if ( v27 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x78,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
                (const char *)(unsigned int)v27,
                ppva);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
LABEL_30:
              v26 = pv;
              pv = 0;
              if ( v26 )
                CoTaskMemFree(v26);
              goto LABEL_27;
            }
            for ( i = 0; i < v39; ++i )
            {
              v29 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v40 + 88LL))(
                      v40,
                      v37,
                      a4,
                      *((unsigned int *)pv + i));
              if ( v29 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x7C,
                  (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
                  (const char *)(unsigned int)v29,
                  ppva);
            }
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
          }
          v30 = pv;
          pv = 0;
          if ( v30 )
            CoTaskMemFree(v30);
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v37);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v35);
        std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v41);
        std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v42);
        return 0;
      }
      v32 = 93;
    }
    v16 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
      (const char *)0x80070057LL,
      ppv);
    goto LABEL_46;
  }
  v16 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x54,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointcontrol.cpp",
          (const char *)v15,
          ppv);
LABEL_46:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v41);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v42);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180112060  push    rbp
0x180112062  push    rbx
0x180112063  push    rsi
0x180112064  push    rdi
0x180112065  push    r12
0x180112067  push    r13
0x180112069  push    r14
0x18011206b  push    r15
0x18011206d  lea     rbp, [rsp-17h]
0x180112072  sub     rsp, 98h
0x180112079  mov     r15d, r9d
0x18011207c  mov     r13d, r8d
0x18011207f  mov     r12d, edx
0x180112082  mov     r14, rcx
0x180112085  mov     [rbp+4Fh+var_68], 0
0x18011208d  mov     [rbp+4Fh+var_70], 0
0x180112095  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x18011209c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x1801120a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801120a8  mov     ecx, 38h ; '8'; unsigned __int64
0x1801120ad  test    al, al
0x1801120af  jz      short loc_1801120F9
0x1801120b1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801120b6  mov     rsi, rax
0x1801120b9  test    rax, rax
0x1801120bc  jz      short loc_1801120EB
0x1801120be  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1801120c5  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x1801120cb  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1801120d0  mov     qword ptr [rsp+0D0h+ppv], rbx; pftDueTime
0x1801120d5  lea     r9, aSApmsetpersist; "s_apmSetPersistedDefaultAudioEndpoint"
0x1801120dc  mov     r8d, edi
0x1801120df  mov     rdx, [rax+8]
0x1801120e3  mov     rcx, rsi; pv
0x1801120e6  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x1801120eb  mov     rdx, rax
0x1801120ee  lea     rcx, [rbp+4Fh+var_68]
0x1801120f2  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x1801120f7  jmp     short loc_18011213F
0x1801120f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801120fe  mov     rsi, rax
0x180112101  test    rax, rax
0x180112104  jz      short loc_180112133
0x180112106  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18011210d  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180112113  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180112118  mov     qword ptr [rsp+0D0h+ppv], rbx; int
0x18011211d  lea     r9, aSApmsetpersist; "s_apmSetPersistedDefaultAudioEndpoint"
0x180112124  mov     r8d, edi
0x180112127  mov     rdx, [rax+8]
0x18011212b  mov     rcx, rsi; pv
0x18011212e  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180112133  mov     rdx, rax
0x180112136  lea     rcx, [rbp+4Fh+var_70]
0x18011213a  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x18011213f  xor     esi, esi
0x180112141  mov     [rbp+4Fh+Pid], esi
0x180112144  lea     rdx, [rbp+4Fh+Pid]; Pid
0x180112148  mov     rcx, r14; Binding
0x18011214b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180112151  test    eax, eax
0x180112153  jz      short loc_180112172
0x180112155  mov     rcx, [rbp+57h]; this
0x180112159  mov     r9d, eax; char *
0x18011215c  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180112163  lea     edx, [rsi+54h]; void *
0x180112166  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011216b  mov     ebx, eax
0x18011216d  jmp     loc_180112421
0x180112172  call    cs:__imp_GetCurrentProcessId
0x180112178  mov     ecx, [rbp+4Fh+Pid]
0x18011217b  cmp     ecx, eax
0x18011217d  setz    dl
0x180112180  mov     rax, cs:?g_ADGProcess@@3PEAVCAudioDGProcess@@EA; CAudioDGProcess * g_ADGProcess
0x180112187  test    rax, rax
0x18011218a  jz      short loc_180112193
0x18011218c  cmp     ecx, [rax+60h]
0x18011218f  mov     al, 1
0x180112191  jz      short loc_180112196
0x180112193  mov     al, sil
0x180112196  test    dl, dl
0x180112198  jnz     loc_180112404
0x18011219e  test    al, al
0x1801121a0  jnz     loc_180112404
0x1801121a6  cmp     r15d, 2
0x1801121aa  ja      loc_1801123FD
0x1801121b0  mov     [rbp+4Fh+var_A0], rsi
0x1801121b4  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x1801121bb  mov     rax, [rcx]
0x1801121be  lea     r8, [rbp+4Fh+var_A0]
0x1801121c2  mov     edx, r12d
0x1801121c5  mov     rax, [rax+28h]
0x1801121c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801121ce  mov     ebx, eax
0x1801121d0  test    eax, eax
0x1801121d2  jns     short loc_1801121FA
0x1801121d4  mov     r9d, eax; char *
0x1801121d7  mov     edx, 62h ; 'b'; void *
0x1801121dc  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801121e3  mov     rcx, [rbp+57h]; this
0x1801121e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801121ec  lea     rcx, [rbp+4Fh+var_A0]
0x1801121f0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801121f5  jmp     loc_180112421
0x1801121fa  mov     rcx, [rbp+4Fh+var_A0]
0x1801121fe  test    rcx, rcx
0x180112201  jnz     short loc_180112210
0x180112203  mov     ebx, 80070057h
0x180112208  mov     r9d, ebx
0x18011220b  lea     edx, [rcx+63h]
0x18011220e  jmp     short loc_1801121DC
0x180112210  mov     rax, [rcx]
0x180112213  mov     rbx, [rbp+4Fh+arg_20]
0x180112217  mov     r9, rbx
0x18011221a  mov     r8d, r15d
0x18011221d  mov     edx, r13d
0x180112220  mov     rax, [rax+18h]
0x180112224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112229  mov     edi, eax
0x18011222b  test    eax, eax
0x18011222d  jns     short loc_180112257
0x18011222f  mov     rcx, [rbp+57h]; this
0x180112233  mov     r9d, eax; char *
0x180112236  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011223d  mov     edx, 65h ; 'e'; void *
0x180112242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112247  lea     rcx, [rbp+4Fh+var_A0]
0x18011224b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180112250  mov     ebx, edi
0x180112252  jmp     loc_180112421
0x180112257  mov     [rbp+4Fh+var_90], rsi
0x18011225b  test    rbx, rbx
0x18011225e  jz      loc_1801123D5
0x180112264  lea     rcx, [rbp+4Fh+var_90]
0x180112268  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18011226d  lea     rdx, [rbp+4Fh+var_90]
0x180112271  mov     rcx, rbx
0x180112274  call    cs:__imp_mmdDevGetMMDeviceFromInterfaceId
0x18011227a  mov     ebx, eax
0x18011227c  test    eax, eax
0x18011227e  jns     short loc_1801122A6
0x180112280  mov     rcx, [rbp+57h]; this
0x180112284  mov     r9d, eax; char *
0x180112287  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011228e  mov     edx, 6Ch ; 'l'; void *
0x180112293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112298  lea     rcx, [rbp+4Fh+var_90]
0x18011229c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801122a1  jmp     loc_1801121EC
0x1801122a6  mov     [rbp+4Fh+var_80], rsi
0x1801122aa  mov     [rbp+4Fh+pv], rsi
0x1801122ae  mov     rcx, [rbp+4Fh+var_A0]
0x1801122b2  mov     rax, [rcx]
0x1801122b5  lea     rdx, [rbp+4Fh+pv]
0x1801122b9  mov     [rbp+4Fh+var_60], rdx
0x1801122bd  mov     [rbp+4Fh+var_58], rsi
0x1801122c1  mov     [rbp+4Fh+var_50], 1
0x1801122c5  lea     r8, [rbp+4Fh+var_58]
0x1801122c9  lea     rdx, [rbp+4Fh+var_80]
0x1801122cd  mov     rax, [rax+38h]
0x1801122d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801122d6  mov     ebx, eax
0x1801122d8  lea     rcx, [rbp+4Fh+var_60]
0x1801122dc  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801122e1  test    ebx, ebx
0x1801122e3  jns     short loc_180112312
0x1801122e5  mov     rcx, [rbp+57h]; this
0x1801122e9  mov     r9d, ebx; char *
0x1801122ec  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801122f3  mov     edx, 72h ; 'r'; void *
0x1801122f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801122fd  mov     rcx, [rbp+4Fh+pv]; pv
0x180112301  mov     [rbp+4Fh+pv], rsi
0x180112305  test    rcx, rcx
0x180112308  jz      short loc_180112298
0x18011230a  call    cs:__imp_CoTaskMemFree
0x180112310  jmp     short loc_180112298
0x180112312  cmp     [rbp+4Fh+var_80], rsi
0x180112316  jz      loc_1801123C2
0x18011231c  mov     [rbp+4Fh+var_78], rsi
0x180112320  lea     rax, [rbp+4Fh+var_78]
0x180112324  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x180112329  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x180112330  xor     edx, edx; pUnkOuter
0x180112332  lea     r8d, [rdx+17h]; dwClsContext
0x180112336  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x18011233d  call    cs:__imp_CoCreateInstance
0x180112343  mov     ebx, eax
0x180112345  test    eax, eax
0x180112347  jns     short loc_18011236C
0x180112349  mov     rcx, [rbp+57h]; this
0x18011234d  mov     r9d, eax; char *
0x180112350  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180112357  mov     edx, 78h ; 'x'; void *
0x18011235c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112361  lea     rcx, [rbp+4Fh+var_78]
0x180112365  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18011236a  jmp     short loc_1801122FD
0x18011236c  mov     rbx, rsi
0x18011236f  cmp     [rbp+4Fh+var_80], rsi
0x180112373  jbe     short loc_1801123B9
0x180112375  mov     rcx, [rbp+4Fh+var_78]
0x180112379  mov     rax, [rcx]
0x18011237c  mov     r9, [rbp+4Fh+pv]
0x180112380  mov     r9d, [r9+rbx*4]
0x180112384  mov     r8d, r15d
0x180112387  mov     rdx, [rbp+4Fh+var_90]
0x18011238b  mov     rax, [rax+58h]
0x18011238f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112394  test    eax, eax
0x180112396  jns     short loc_1801123B0
0x180112398  mov     rcx, [rbp+57h]; this
0x18011239c  mov     r9d, eax; char *
0x18011239f  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801123a6  mov     edx, 7Ch ; '|'; void *
0x1801123ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801123b0  inc     rbx
0x1801123b3  cmp     rbx, [rbp+4Fh+var_80]
0x1801123b7  jb      short loc_180112375
0x1801123b9  lea     rcx, [rbp+4Fh+var_78]
0x1801123bd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801123c2  mov     rcx, [rbp+4Fh+pv]; pv
0x1801123c6  mov     [rbp+4Fh+pv], rsi
0x1801123ca  test    rcx, rcx
0x1801123cd  jz      short loc_1801123D5
0x1801123cf  call    cs:__imp_CoTaskMemFree
0x1801123d5  lea     rcx, [rbp+4Fh+var_90]
0x1801123d9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801123de  lea     rcx, [rbp+4Fh+var_A0]
0x1801123e2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801123e7  lea     rcx, [rbp+4Fh+var_70]
0x1801123eb  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x1801123f0  lea     rcx, [rbp+4Fh+var_68]
0x1801123f4  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x1801123f9  xor     eax, eax
0x1801123fb  jmp     short loc_180112435
0x1801123fd  mov     edx, 5Dh ; ']'
0x180112402  jmp     short loc_180112409
0x180112404  mov     edx, 58h ; 'X'; void *
0x180112409  mov     ebx, 80070057h
0x18011240e  mov     r9d, ebx; char *
0x180112411  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180112418  mov     rcx, [rbp+57h]; this
0x18011241c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112421  lea     rcx, [rbp+4Fh+var_70]
0x180112425  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x18011242a  lea     rcx, [rbp+4Fh+var_68]
0x18011242e  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180112433  mov     eax, ebx
0x180112435  add     rsp, 98h
0x18011243c  pop     r15
0x18011243e  pop     r14
0x180112440  pop     r13
0x180112442  pop     r12
0x180112444  pop     rdi
0x180112445  pop     rsi
0x180112446  pop     rbx
0x180112447  pop     rbp
0x180112448  retn
```
