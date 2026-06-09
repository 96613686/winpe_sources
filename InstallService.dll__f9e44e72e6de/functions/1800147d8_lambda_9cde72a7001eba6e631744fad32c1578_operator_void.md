# _lambda_9cde72a7001eba6e631744fad32c1578_::operator()(void)

- ea: `0x1800147d8`
- end: `0x180014aa4`
- name: `??R_lambda_9cde72a7001eba6e631744fad32c1578_@@QEBA@XZ`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a000`

## callees

- `0x180010b54`
- `0x180010b74`
- `0x1800125a0`
- `0x1800127c8`
- `0x180012fb8`
- `0x180013044`
- `0x180013254`
- `0x1800147d8`
- `0x1800181e0`
- `0x180019fdc`
- `0x18001a19c`
- `0x18001afd0`
- `0x18001b048`
- `0x18001b084`
- `0x18005b89c`
- `0x18016eef8`
- `0x1801da89c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014832`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014832`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800149cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800149cf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800149bf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800149f6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800149bf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800149f6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800147f6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800147f6`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800148fe`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800148fe`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180014a87`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180014a87`

## string_xrefs

- `0x180014812`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180014878`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180014914`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800147ef`: `InstallService`
- `0x180014986`: `onecoreuap\enduser\winstore\installservice\svc\svcmain.cpp`
- `0x180014a5c`: `onecoreuap\enduser\winstore\installservice\svc\svcmain.cpp`
- `0x180014965`: `InstallService Shutting down`
- `0x180014a3b`: `InstallService Shutting down`
- `0x180014979`: `InstallService::ServiceStopped`
- `0x180014a4f`: `InstallService::ServiceStopped`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_9cde72a7001eba6e631744fad32c1578_::operator()(void ***a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  int v5; // edi
  __int64 v6; // rdx
  void **v7; // rcx
  __int64 v8; // rax
  InstallService *v9; // rcx
  DWORD v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  winrt *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  winrt *v17; // rcx
  void *v18; // rcx
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  (*a1)[1] = RegisterServiceCtrlHandlerExW(
               L"InstallService",
               Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>::HandlerExStatic,
               *a1);
  if ( !(*a1)[1] )
  {
    v3 = 509;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  (*a1)[6] = CreateEventW(0, 0, 0, 0);
  if ( !(*a1)[6] )
  {
    v3 = 512;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetImpl'::`2'::impl) )
  {
    v5 = EnforceRedirectionTrustPolicy();
    if ( v5 < 0 )
    {
      v6 = 516;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v5,
        v19);
      return (unsigned int)v5;
    }
  }
  v7 = *a1;
  if ( *(_BYTE *)a1[1] )
    v8 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create<Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>>(
           v7,
           tip2::details::merged_data<TipTests::_tip_FrameworkUpdateTipTest,TipTests::_tip_FrameworkUpdateTipTest>::on_result);
  else
    v8 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create<Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>>(
           v7,
           tip2::details::merged_data<TipTests::_tip_FrameworkUpdateTipTest,TipTests::_tip_FrameworkUpdateTipTest>::on_result);
  *a1[2] = (void *)v8;
  v5 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>(
         (Windows::Internal::ServiceModuleBase *)*a1[2],
         *(_BYTE *)a1[1]);
  if ( v5 < 0 )
  {
    v6 = 545;
    goto LABEL_9;
  }
  v5 = InstallService::ServiceStarted(v9);
  *(_DWORD *)a1[3] = v5;
  if ( v5 < 0 )
  {
    v6 = 547;
    goto LABEL_9;
  }
  v10 = PowerSettingRegisterNotification(
          &Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>::GUID_LOW_POWER_EPOCH_PRV,
          1u,
          (*a1)[1],
          *a1);
  if ( v10 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x23A,
            (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
            (const char *)v10,
            v19);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ServiceStateTransition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ServiceStateTransition>::GetImpl'::`2'::impl) )
    {
      LOBYTE(v12) = 2;
      InstallService::OnServiceStateChanged(v13, v12);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl'::`2'::impl) )
      TerminateQueue();
    LogSimpleMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\svc\\svcmain.cpp",
      0x5Eu,
      "InstallService::ServiceStopped",
      -1,
      L"InstallService Shutting down",
      0,
      0);
    TerminateQueue();
    TerminateQueue2();
    winrt::clear_factory_cache(v14);
    return v11;
  }
  else
  {
    *((_DWORD *)*a1 + 6) |= 0x40u;
    SetServiceStatus((SERVICE_STATUS_HANDLE)(*a1)[1], (LPSERVICE_STATUS)(*a1 + 2));
    WaitForSingleObject((*a1)[6], 0xFFFFFFFF);
    if ( ((*((_DWORD *)*a1 + 5) - 1) & 0xFFFFFFFD) != 0 )
    {
      *((_DWORD *)*a1 + 5) = 3;
      SetServiceStatus((SERVICE_STATUS_HANDLE)(*a1)[1], (LPSERVICE_STATUS)(*a1 + 2));
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ServiceStateTransition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ServiceStateTransition>::GetImpl'::`2'::impl) )
    {
      LOBYTE(v15) = 2;
      InstallService::OnServiceStateChanged(v16, v15);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl'::`2'::impl) )
      TerminateQueue();
    LogSimpleMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\svc\\svcmain.cpp",
      0x5Eu,
      "InstallService::ServiceStopped",
      -1,
      L"InstallService Shutting down",
      0,
      0);
    TerminateQueue();
    TerminateQueue2();
    winrt::clear_factory_cache(v17);
    v18 = **a1;
    if ( v18 )
    {
      PowerSettingUnregisterNotification(v18);
      **a1 = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800147d8  mov     [rsp+arg_0], rbx
0x1800147dd  push    rdi
0x1800147de  sub     rsp, 40h
0x1800147e2  mov     rbx, rcx
0x1800147e5  mov     r8, [rcx]; lpContext
0x1800147e8  lea     rdx, ?HandlerExStatic@?$Service@VInstallService@@$02USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x1800147ef  lea     rcx, ServiceName; "InstallService"
0x1800147f6  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800147fc  mov     rdx, [rbx]
0x1800147ff  mov     [rdx+8], rax
0x180014803  mov     rax, [rbx]
0x180014806  cmp     qword ptr [rax+8], 0
0x18001480b  jnz     short loc_180014828
0x18001480d  mov     edx, 1FDh; void *
0x180014812  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x180014819  mov     rcx, [rsp+48h]; this
0x18001481e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014823  jmp     loc_180014A99
0x180014828  xor     r9d, r9d; lpName
0x18001482b  xor     r8d, r8d; bInitialState
0x18001482e  xor     edx, edx; bManualReset
0x180014830  xor     ecx, ecx; lpEventAttributes
0x180014832  call    cs:__imp_CreateEventW
0x180014838  mov     rcx, [rbx]
0x18001483b  mov     [rcx+30h], rax
0x18001483f  mov     rax, [rbx]
0x180014842  cmp     qword ptr [rax+30h], 0
0x180014847  jnz     short loc_180014850
0x180014849  mov     edx, 200h
0x18001484e  jmp     short loc_180014812
0x180014850  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy> `wil::Feature<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetImpl(void)'::`2'::impl
0x180014857  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::__private_IsEnabled(void)
0x18001485c  test    al, al
0x18001485e  jz      short loc_18001488B
0x180014860  call    ?EnforceRedirectionTrustPolicy@@YAJXZ; EnforceRedirectionTrustPolicy(void)
0x180014865  mov     edi, eax
0x180014867  test    eax, eax
0x180014869  jns     short loc_18001488B
0x18001486b  mov     edx, 204h; void *
0x180014870  mov     rcx, [rsp+48h]; this
0x180014875  mov     r9d, edi; char *
0x180014878  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18001487f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014884  mov     eax, edi
0x180014886  jmp     loc_180014A99
0x18001488b  mov     rax, [rbx+8]
0x18001488f  lea     rdx, ?on_result@?$merged_data@U_tip_FrameworkUpdateTipTest@TipTests@@U12@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<TipTests::_tip_FrameworkUpdateTipTest,TipTests::_tip_FrameworkUpdateTipTest>::on_result(TipReportingInfo const &)
0x180014896  mov     rcx, [rbx]
0x180014899  cmp     byte ptr [rax], 0
0x18001489c  jz      short loc_1800148A5
0x18001489e  call    ??$Create@V?$Service@VInstallService@@$02USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@PEAV?$Service@VInstallService@@$02USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@45@@56@P8756@EAAXXZ@Z; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create<Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>>(Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>> *,void (Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>::*)(void))
0x1800148a3  jmp     short loc_1800148AA
0x1800148a5  call    ??$Create@V?$Service@VInstallService@@$02USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@PEAV?$Service@VInstallService@@$02USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@45@@56@P8756@EAAXXZ@Z; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create<Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>>(Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>> *,void (Windows::Internal::Service<InstallService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>::*)(void))
0x1800148aa  mov     rcx, [rbx+10h]
0x1800148ae  mov     [rcx], rax
0x1800148b1  mov     rdx, [rbx+8]
0x1800148b5  mov     rcx, [rbx+10h]
0x1800148b9  mov     dl, [rdx]
0x1800148bb  mov     rcx, [rcx]
0x1800148be  call    ??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::ModuleServerDescriptor<InstallService>>(uchar,uchar,uchar,uchar,void *,ulong)
0x1800148c3  mov     edi, eax
0x1800148c5  test    eax, eax
0x1800148c7  jns     short loc_1800148D0
0x1800148c9  mov     edx, 221h
0x1800148ce  jmp     short loc_180014870
0x1800148d0  call    ?ServiceStarted@InstallService@@QEAAJXZ; InstallService::ServiceStarted(void)
0x1800148d5  mov     edi, eax
0x1800148d7  mov     rcx, [rbx+18h]
0x1800148db  mov     [rcx], eax
0x1800148dd  test    eax, eax
0x1800148df  jns     short loc_1800148E8
0x1800148e1  mov     edx, 223h
0x1800148e6  jmp     short loc_180014870
0x1800148e8  mov     r8, [rbx]
0x1800148eb  mov     r9, r8; RegistrationHandle
0x1800148ee  mov     r8, [r8+8]; Recipient
0x1800148f2  mov     edx, 1; Flags
0x1800148f7  lea     rcx, ?GUID_LOW_POWER_EPOCH_PRV@?$Service@VInstallService@@$02USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01U?$ModuleServerDescriptor@VInstallService@@@45@@Internal@Windows@@0U_GUID@@B; SettingGuid
0x1800148fe  call    cs:__imp_PowerSettingRegisterNotification
0x180014904  test    eax, eax
0x180014906  jz      loc_1800149AD
0x18001490c  mov     rcx, [rsp+48h]; this
0x180014911  mov     r9d, eax; char *
0x180014914  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18001491b  mov     edx, 23Ah; void *
0x180014920  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180014925  mov     ebx, eax
0x180014927  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ServiceStateTransition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ServiceStateTransition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ServiceStateTransition> `wil::Feature<__WilFeatureTraits_Feature_ServiceStateTransition>::GetImpl(void)'::`2'::impl
0x18001492e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ServiceStateTransition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ServiceStateTransition>::__private_IsEnabled(void)
0x180014933  test    al, al
0x180014935  jz      short loc_18001493E
0x180014937  mov     dl, 2
0x180014939  call    ?OnServiceStateChanged@InstallService@@QEAAXW4ServiceState@1@@Z; InstallService::OnServiceStateChanged(InstallService::ServiceState)
0x18001493e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown> `wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl(void)'::`2'::impl
0x180014945  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(void)
0x18001494a  test    al, al
0x18001494c  jnz     short loc_180014953
0x18001494e  call    ?TerminateQueue@@YAXXZ; TerminateQueue(void)
0x180014953  mov     [rsp+48h+var_10], 0; unsigned __int16 *
0x18001495c  mov     [rsp+48h+var_18], 0; char *
0x180014965  lea     rax, aInstallservice_17; "InstallService Shutting down"
0x18001496c  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180014971  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x180014979  lea     r9, aInstallservice_13; "InstallService::ServiceStopped"
0x180014980  mov     r8d, 5Eh ; '^'; unsigned int
0x180014986  lea     rdx, aOnecoreuapEndu_30; "onecoreuap\\enduser\\winstore\\installs"...
0x18001498d  lea     ecx, [r8-5Ah]; unsigned int
0x180014991  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180014996  call    ?TerminateQueue@@YAXXZ; TerminateQueue(void)
0x18001499b  call    ?TerminateQueue2@@YAXXZ; TerminateQueue2(void)
0x1800149a0  call    ?clear_factory_cache@winrt@@YAXXZ; winrt::clear_factory_cache(void)
0x1800149a5  nop
0x1800149a6  mov     eax, ebx
0x1800149a8  jmp     loc_180014A99
0x1800149ad  mov     rax, [rbx]
0x1800149b0  or      dword ptr [rax+18h], 40h
0x1800149b4  mov     rcx, [rbx]
0x1800149b7  lea     rdx, [rcx+10h]; lpServiceStatus
0x1800149bb  mov     rcx, [rcx+8]; hServiceStatus
0x1800149bf  call    cs:__imp_SetServiceStatus
0x1800149c5  mov     rcx, [rbx]
0x1800149c8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800149cb  mov     rcx, [rcx+30h]; hHandle
0x1800149cf  call    cs:__imp_WaitForSingleObject
0x1800149d5  mov     rcx, [rbx]
0x1800149d8  mov     eax, [rcx+14h]
0x1800149db  dec     eax
0x1800149dd  test    eax, 0FFFFFFFDh
0x1800149e2  jz      short loc_1800149FD
0x1800149e4  mov     dword ptr [rcx+14h], 3
0x1800149eb  mov     rcx, [rbx]
0x1800149ee  lea     rdx, [rcx+10h]; lpServiceStatus
0x1800149f2  mov     rcx, [rcx+8]; hServiceStatus
0x1800149f6  call    cs:__imp_SetServiceStatus
0x1800149fc  nop
0x1800149fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ServiceStateTransition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ServiceStateTransition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ServiceStateTransition> `wil::Feature<__WilFeatureTraits_Feature_ServiceStateTransition>::GetImpl(void)'::`2'::impl
0x180014a04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ServiceStateTransition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ServiceStateTransition>::__private_IsEnabled(void)
0x180014a09  test    al, al
0x180014a0b  jz      short loc_180014A14
0x180014a0d  mov     dl, 2
0x180014a0f  call    ?OnServiceStateChanged@InstallService@@QEAAXW4ServiceState@1@@Z; InstallService::OnServiceStateChanged(InstallService::ServiceState)
0x180014a14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown> `wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl(void)'::`2'::impl
0x180014a1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(void)
0x180014a20  test    al, al
0x180014a22  jnz     short loc_180014A29
0x180014a24  call    ?TerminateQueue@@YAXXZ; TerminateQueue(void)
0x180014a29  mov     [rsp+48h+var_10], 0; unsigned __int16 *
0x180014a32  mov     [rsp+48h+var_18], 0; char *
0x180014a3b  lea     rax, aInstallservice_17; "InstallService Shutting down"
0x180014a42  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180014a47  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x180014a4f  lea     r9, aInstallservice_13; "InstallService::ServiceStopped"
0x180014a56  mov     r8d, 5Eh ; '^'; unsigned int
0x180014a5c  lea     rdx, aOnecoreuapEndu_30; "onecoreuap\\enduser\\winstore\\installs"...
0x180014a63  lea     ecx, [r8-5Ah]; unsigned int
0x180014a67  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180014a6c  call    ?TerminateQueue@@YAXXZ; TerminateQueue(void)
0x180014a71  call    ?TerminateQueue2@@YAXXZ; TerminateQueue2(void)
0x180014a76  call    ?clear_factory_cache@winrt@@YAXXZ; winrt::clear_factory_cache(void)
0x180014a7b  nop
0x180014a7c  mov     rax, [rbx]
0x180014a7f  mov     rcx, [rax]; RegistrationHandle
0x180014a82  test    rcx, rcx
0x180014a85  jz      short loc_180014A97
0x180014a87  call    cs:__imp_PowerSettingUnregisterNotification
0x180014a8d  mov     rax, [rbx]
0x180014a90  mov     qword ptr [rax], 0
0x180014a97  xor     eax, eax
0x180014a99  mov     rbx, [rsp+48h+arg_0]
0x180014a9e  add     rsp, 40h
0x180014aa2  pop     rdi
0x180014aa3  retn
```
