# s_apmSetPersistedDefaultAudioEndpoint

- ea: `0x180111db0`
- end: `0x180112199`
- name: `s_apmSetPersistedDefaultAudioEndpoint`
- size: `1001`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE Binding@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x1800423cc`
- `0x1800a5358`
- `0x1800cdfbc`
- `0x1800cfd9c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x180111db0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180111ec2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180111ec2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180111e9b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180111e9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011208d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011208d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011205a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011211f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011205a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011211f`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x180111fc4`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x180111fc4`

## string_xrefs

- `0x180111eac`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180111f2c`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180111f86`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180111fd7`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x18011203c`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x1801120a0`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x1801120ef`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`
- `0x180112161`: `avcore\audiocore\server\audiosrv\dll\endpointcontrol.cpp`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x180111db0  push    rbp
0x180111db2  push    rbx
0x180111db3  push    rsi
0x180111db4  push    rdi
0x180111db5  push    r12
0x180111db7  push    r13
0x180111db9  push    r14
0x180111dbb  push    r15
0x180111dbd  lea     rbp, [rsp-17h]
0x180111dc2  sub     rsp, 98h
0x180111dc9  mov     r15d, r9d
0x180111dcc  mov     r13d, r8d
0x180111dcf  mov     r12d, edx
0x180111dd2  mov     r14, rcx
0x180111dd5  mov     [rbp+4Fh+var_68], 0
0x180111ddd  mov     [rbp+4Fh+var_70], 0
0x180111de5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180111dec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180111df1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180111df8  mov     ecx, 38h ; '8'; unsigned __int64
0x180111dfd  test    al, al
0x180111dff  jz      short loc_180111E49
0x180111e01  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180111e06  mov     rsi, rax
0x180111e09  test    rax, rax
0x180111e0c  jz      short loc_180111E3B
0x180111e0e  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180111e15  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180111e1b  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180111e20  mov     qword ptr [rsp+0D0h+ppv], rbx; pftDueTime
0x180111e25  lea     r9, aSApmsetpersist; "s_apmSetPersistedDefaultAudioEndpoint"
0x180111e2c  mov     r8d, edi
0x180111e2f  mov     rdx, [rax+8]
0x180111e33  mov     rcx, rsi; pv
0x180111e36  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180111e3b  mov     rdx, rax
0x180111e3e  lea     rcx, [rbp+4Fh+var_68]
0x180111e42  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180111e47  jmp     short loc_180111E8F
0x180111e49  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180111e4e  mov     rsi, rax
0x180111e51  test    rax, rax
0x180111e54  jz      short loc_180111E83
0x180111e56  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180111e5d  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180111e63  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180111e68  mov     qword ptr [rsp+0D0h+ppv], rbx; int
0x180111e6d  lea     r9, aSApmsetpersist; "s_apmSetPersistedDefaultAudioEndpoint"
0x180111e74  mov     r8d, edi
0x180111e77  mov     rdx, [rax+8]
0x180111e7b  mov     rcx, rsi; pv
0x180111e7e  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180111e83  mov     rdx, rax
0x180111e86  lea     rcx, [rbp+4Fh+var_70]
0x180111e8a  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180111e8f  xor     esi, esi
0x180111e91  mov     [rbp+4Fh+Pid], esi
0x180111e94  lea     rdx, [rbp+4Fh+Pid]; Pid
0x180111e98  mov     rcx, r14; Binding
0x180111e9b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180111ea1  test    eax, eax
0x180111ea3  jz      short loc_180111EC2
0x180111ea5  mov     rcx, [rbp+57h]; this
0x180111ea9  mov     r9d, eax; char *
0x180111eac  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180111eb3  lea     edx, [rsi+54h]; void *
0x180111eb6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180111ebb  mov     ebx, eax
0x180111ebd  jmp     loc_180112171
0x180111ec2  call    cs:__imp_GetCurrentProcessId
0x180111ec8  mov     ecx, [rbp+4Fh+Pid]
0x180111ecb  cmp     ecx, eax
0x180111ecd  setz    dl
0x180111ed0  mov     rax, cs:?g_ADGProcess@@3PEAVCAudioDGProcess@@EA; CAudioDGProcess * g_ADGProcess
0x180111ed7  test    rax, rax
0x180111eda  jz      short loc_180111EE3
0x180111edc  cmp     ecx, [rax+60h]
0x180111edf  mov     al, 1
0x180111ee1  jz      short loc_180111EE6
0x180111ee3  mov     al, sil
0x180111ee6  test    dl, dl
0x180111ee8  jnz     loc_180112154
0x180111eee  test    al, al
0x180111ef0  jnz     loc_180112154
0x180111ef6  cmp     r15d, 2
0x180111efa  ja      loc_18011214D
0x180111f00  mov     [rbp+4Fh+var_A0], rsi
0x180111f04  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA; IAudioPolicyManager * g_PolicyManager
0x180111f0b  mov     rax, [rcx]
0x180111f0e  lea     r8, [rbp+4Fh+var_A0]
0x180111f12  mov     edx, r12d
0x180111f15  mov     rax, [rax+28h]
0x180111f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111f1e  mov     ebx, eax
0x180111f20  test    eax, eax
0x180111f22  jns     short loc_180111F4A
0x180111f24  mov     r9d, eax; char *
0x180111f27  mov     edx, 62h ; 'b'; void *
0x180111f2c  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180111f33  mov     rcx, [rbp+57h]; this
0x180111f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111f3c  lea     rcx, [rbp+4Fh+var_A0]
0x180111f40  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180111f45  jmp     loc_180112171
0x180111f4a  mov     rcx, [rbp+4Fh+var_A0]
0x180111f4e  test    rcx, rcx
0x180111f51  jnz     short loc_180111F60
0x180111f53  mov     ebx, 80070057h
0x180111f58  mov     r9d, ebx
0x180111f5b  lea     edx, [rcx+63h]
0x180111f5e  jmp     short loc_180111F2C
0x180111f60  mov     rax, [rcx]
0x180111f63  mov     rbx, [rbp+4Fh+arg_20]
0x180111f67  mov     r9, rbx
0x180111f6a  mov     r8d, r15d
0x180111f6d  mov     edx, r13d
0x180111f70  mov     rax, [rax+18h]
0x180111f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111f79  mov     edi, eax
0x180111f7b  test    eax, eax
0x180111f7d  jns     short loc_180111FA7
0x180111f7f  mov     rcx, [rbp+57h]; this
0x180111f83  mov     r9d, eax; char *
0x180111f86  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180111f8d  mov     edx, 65h ; 'e'; void *
0x180111f92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111f97  lea     rcx, [rbp+4Fh+var_A0]
0x180111f9b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180111fa0  mov     ebx, edi
0x180111fa2  jmp     loc_180112171
0x180111fa7  mov     [rbp+4Fh+var_90], rsi
0x180111fab  test    rbx, rbx
0x180111fae  jz      loc_180112125
0x180111fb4  lea     rcx, [rbp+4Fh+var_90]
0x180111fb8  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180111fbd  lea     rdx, [rbp+4Fh+var_90]
0x180111fc1  mov     rcx, rbx
0x180111fc4  call    cs:__imp_mmdDevGetMMDeviceFromInterfaceId
0x180111fca  mov     ebx, eax
0x180111fcc  test    eax, eax
0x180111fce  jns     short loc_180111FF6
0x180111fd0  mov     rcx, [rbp+57h]; this
0x180111fd4  mov     r9d, eax; char *
0x180111fd7  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180111fde  mov     edx, 6Ch ; 'l'; void *
0x180111fe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111fe8  lea     rcx, [rbp+4Fh+var_90]
0x180111fec  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180111ff1  jmp     loc_180111F3C
0x180111ff6  mov     [rbp+4Fh+var_80], rsi
0x180111ffa  mov     [rbp+4Fh+pv], rsi
0x180111ffe  mov     rcx, [rbp+4Fh+var_A0]
0x180112002  mov     rax, [rcx]
0x180112005  lea     rdx, [rbp+4Fh+pv]
0x180112009  mov     [rbp+4Fh+var_60], rdx
0x18011200d  mov     [rbp+4Fh+var_58], rsi
0x180112011  mov     [rbp+4Fh+var_50], 1
0x180112015  lea     r8, [rbp+4Fh+var_58]
0x180112019  lea     rdx, [rbp+4Fh+var_80]
0x18011201d  mov     rax, [rax+38h]
0x180112021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112026  mov     ebx, eax
0x180112028  lea     rcx, [rbp+4Fh+var_60]
0x18011202c  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180112031  test    ebx, ebx
0x180112033  jns     short loc_180112062
0x180112035  mov     rcx, [rbp+57h]; this
0x180112039  mov     r9d, ebx; char *
0x18011203c  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180112043  mov     edx, 72h ; 'r'; void *
0x180112048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011204d  mov     rcx, [rbp+4Fh+pv]; pv
0x180112051  mov     [rbp+4Fh+pv], rsi
0x180112055  test    rcx, rcx
0x180112058  jz      short loc_180111FE8
0x18011205a  call    cs:__imp_CoTaskMemFree
0x180112060  jmp     short loc_180111FE8
0x180112062  cmp     [rbp+4Fh+var_80], rsi
0x180112066  jz      loc_180112112
0x18011206c  mov     [rbp+4Fh+var_78], rsi
0x180112070  lea     rax, [rbp+4Fh+var_78]
0x180112074  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x180112079  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x180112080  xor     edx, edx; pUnkOuter
0x180112082  lea     r8d, [rdx+17h]; dwClsContext
0x180112086  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x18011208d  call    cs:__imp_CoCreateInstance
0x180112093  mov     ebx, eax
0x180112095  test    eax, eax
0x180112097  jns     short loc_1801120BC
0x180112099  mov     rcx, [rbp+57h]; this
0x18011209d  mov     r9d, eax; char *
0x1801120a0  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801120a7  mov     edx, 78h ; 'x'; void *
0x1801120ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801120b1  lea     rcx, [rbp+4Fh+var_78]
0x1801120b5  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801120ba  jmp     short loc_18011204D
0x1801120bc  mov     rbx, rsi
0x1801120bf  cmp     [rbp+4Fh+var_80], rsi
0x1801120c3  jbe     short loc_180112109
0x1801120c5  mov     rcx, [rbp+4Fh+var_78]
0x1801120c9  mov     rax, [rcx]
0x1801120cc  mov     r9, [rbp+4Fh+pv]
0x1801120d0  mov     r9d, [r9+rbx*4]
0x1801120d4  mov     r8d, r15d
0x1801120d7  mov     rdx, [rbp+4Fh+var_90]
0x1801120db  mov     rax, [rax+58h]
0x1801120df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801120e4  test    eax, eax
0x1801120e6  jns     short loc_180112100
0x1801120e8  mov     rcx, [rbp+57h]; this
0x1801120ec  mov     r9d, eax; char *
0x1801120ef  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801120f6  mov     edx, 7Ch ; '|'; void *
0x1801120fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180112100  inc     rbx
0x180112103  cmp     rbx, [rbp+4Fh+var_80]
0x180112107  jb      short loc_1801120C5
0x180112109  lea     rcx, [rbp+4Fh+var_78]
0x18011210d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180112112  mov     rcx, [rbp+4Fh+pv]; pv
0x180112116  mov     [rbp+4Fh+pv], rsi
0x18011211a  test    rcx, rcx
0x18011211d  jz      short loc_180112125
0x18011211f  call    cs:__imp_CoTaskMemFree
0x180112125  lea     rcx, [rbp+4Fh+var_90]
0x180112129  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18011212e  lea     rcx, [rbp+4Fh+var_A0]
0x180112132  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180112137  lea     rcx, [rbp+4Fh+var_70]
0x18011213b  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180112140  lea     rcx, [rbp+4Fh+var_68]
0x180112144  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180112149  xor     eax, eax
0x18011214b  jmp     short loc_180112185
0x18011214d  mov     edx, 5Dh ; ']'
0x180112152  jmp     short loc_180112159
0x180112154  mov     edx, 58h ; 'X'; void *
0x180112159  mov     ebx, 80070057h
0x18011215e  mov     r9d, ebx; char *
0x180112161  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180112168  mov     rcx, [rbp+57h]; this
0x18011216c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112171  lea     rcx, [rbp+4Fh+var_70]
0x180112175  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x18011217a  lea     rcx, [rbp+4Fh+var_68]
0x18011217e  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180112183  mov     eax, ebx
0x180112185  add     rsp, 98h
0x18011218c  pop     r15
0x18011218e  pop     r14
0x180112190  pop     r13
0x180112192  pop     r12
0x180112194  pop     rdi
0x180112195  pop     rsi
0x180112196  pop     rbx
0x180112197  pop     rbp
0x180112198  retn
```
