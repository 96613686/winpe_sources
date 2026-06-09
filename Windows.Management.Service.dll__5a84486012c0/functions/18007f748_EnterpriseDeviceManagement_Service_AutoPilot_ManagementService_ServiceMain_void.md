# EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceMain(void)

- ea: `0x18007f748`
- end: `0x18007f936`
- name: `?ServiceMain@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAXXZ`
- size: `494`
- prototype: `void __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800808d0`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x1800730b4`
- `0x18007748c`
- `0x18007d928`
- `0x18007f5a0`
- `0x18007f748`
- `0x18007f93c`
- `0x18008015c`
- `0x1800801fc`
- `0x1800806b0`
- `0x180080708`
- `0x18008d29c`
- `0x18008d578`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f8ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f8ef`
- `combase!__imp_CoGetSharedServiceId` at `0x18007f7e1`
- `combase!__imp_CoGetSharedServiceId` at `0x18007f7e1`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18007f76e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18007f76e`

## string_xrefs

- `0x18007f7b4`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f80b`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f83c`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f878`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f8d1`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x18007f7f2`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotglobals.cpp`

## pseudocode

```c
void __fastcall EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceMain(
        EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *this)
{
  void *v1; // rdx
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 v4; // rcx
  __int64 v5; // r8
  int SharedServiceId; // eax
  unsigned int v7; // edi
  Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *Instance; // rax
  int v9; // eax
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // edi
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v15; // rcx
  EnterpriseDeviceManagement::Service::AutoPilot *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // [rsp+20h] [rbp-38h]
  int v21; // [rsp+20h] [rbp-38h]
  int v22[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  hServiceStatus = RegisterServiceCtrlHandlerExW(
                     lpServiceName,
                     EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceControlCallback,
                     0);
  if ( hServiceStatus )
  {
    EnterpriseDeviceManagement::Service::AutoPilot::g_singleton = 0;
    SharedServiceId = CoGetSharedServiceId(&EnterpriseDeviceManagement::Service::AutoPilot::g_singleton);
    v7 = SharedServiceId;
    if ( SharedServiceId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotglobals.cpp",
        (const char *)(unsigned int)SharedServiceId,
        v20);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
        (const char *)v7,
        v21);
    }
    Instance = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance();
    v9 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(Instance, hServiceStatus);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
        (const char *)(unsigned int)v9,
        v20);
    v11 = EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(v10);
    v14 = v11;
    if ( v11 >= 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
        McGenEventWrite_EventWriteTransfer(v12, ManagementServiceStartSuccess, v13, 1, v22);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
      {
        v17 = EnterpriseDeviceManagement::Service::AutoPilot::EventCurrentOsVersion(v16);
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
            (const char *)(unsigned int)v17,
            v20);
      }
      WaitForSingleObject(qword_18029E3E8, 0xFFFFFFFF);
    }
    else
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x40) != 0 )
        McTemplateU0q_EventWriteTransfer(v12, ManagementServiceStartFailed, (unsigned int)v11);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
        (const char *)(unsigned int)v14,
        v20);
    }
    EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceShutdown(v15);
    if ( v14 >= 0 && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      McGenEventWrite_EventWriteTransfer(v18, ManagementServiceShutdown, v19, 1, v22);
  }
  else
  {
    wil::details::in1diag3::_Log_NullAlloc(retaddr, v1, v2, v3);
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x40) != 0 )
      McGenEventWrite_EventWriteTransfer(v4, ManagementServiceRegistrationFailed, v5, 1, v22);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
      (const char *)0x8007000ELL,
      v20);
  }
}

```

## disassembly

```asm
0x18007f748  push    rdi
0x18007f74a  sub     rsp, 50h
0x18007f74e  mov     rax, cs:__security_cookie
0x18007f755  xor     rax, rsp
0x18007f758  mov     [rsp+58h+var_18], rax
0x18007f75d  mov     rcx, cs:lpServiceName; lpServiceName
0x18007f764  lea     rdx, ?ServiceControlCallback@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@CAKKKPEAX0@Z; lpHandlerProc
0x18007f76b  xor     r8d, r8d; lpContext
0x18007f76e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18007f774  mov     cs:hServiceStatus, rax
0x18007f77b  test    rax, rax
0x18007f77e  jnz     short loc_18007F7D0
0x18007f780  mov     rcx, [rsp+58h]; this
0x18007f785  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x18007f78a  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 40h
0x18007f791  jz      short loc_18007F7AF
0x18007f793  lea     rax, [rsp+58h+var_28]
0x18007f798  mov     r9d, 1
0x18007f79e  lea     rdx, ManagementServiceRegistrationFailed
0x18007f7a5  mov     qword ptr [rsp+58h+var_38], rax; int
0x18007f7aa  call    McGenEventWrite_EventWriteTransfer
0x18007f7af  mov     rcx, [rsp+58h]; this
0x18007f7b4  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f7bb  mov     r9d, 8007000Eh; char *
0x18007f7c1  mov     edx, 16Fh; void *
0x18007f7c6  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007f7cb  jmp     loc_18007F923
0x18007f7d0  lea     rcx, ?g_singleton@AutoPilot@Service@EnterpriseDeviceManagement@@3VAutoPilotGlobals@123@A; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotGlobals EnterpriseDeviceManagement::Service::AutoPilot::g_singleton
0x18007f7d7  mov     cs:?g_singleton@AutoPilot@Service@EnterpriseDeviceManagement@@3VAutoPilotGlobals@123@A, 0; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotGlobals EnterpriseDeviceManagement::Service::AutoPilot::g_singleton
0x18007f7e1  call    cs:__imp_CoGetSharedServiceId
0x18007f7e7  mov     edi, eax
0x18007f7e9  test    eax, eax
0x18007f7eb  jns     short loc_18007F81F
0x18007f7ed  mov     rcx, [rsp+58h]; this
0x18007f7f2  lea     r8, aOnecoreuapAdmi_141; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f7f9  mov     r9d, eax; char *
0x18007f7fc  mov     edx, 1Ah; void *
0x18007f801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f806  mov     rcx, [rsp+58h]; this
0x18007f80b  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f812  mov     r9d, edi; char *
0x18007f815  mov     edx, 173h; void *
0x18007f81a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f81f  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x18007f824  mov     rdx, cs:hServiceStatus; struct SERVICE_STATUS_HANDLE__ *
0x18007f82b  mov     rcx, rax; this
0x18007f82e  call    ?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)
0x18007f833  test    eax, eax
0x18007f835  jns     short loc_18007F850
0x18007f837  mov     rcx, [rsp+58h]; this
0x18007f83c  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f843  mov     r9d, eax; char *
0x18007f846  mov     edx, 174h; void *
0x18007f84b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f850  call    ?ServiceInitialization@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(void)
0x18007f855  mov     edi, eax
0x18007f857  test    eax, eax
0x18007f859  jns     short loc_18007F88E
0x18007f85b  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 40h
0x18007f862  jz      short loc_18007F873
0x18007f864  mov     r8d, eax
0x18007f867  lea     rdx, ManagementServiceStartFailed
0x18007f86e  call    McTemplateU0q_EventWriteTransfer
0x18007f873  mov     rcx, [rsp+58h]; this
0x18007f878  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f87f  mov     r9d, edi; char *
0x18007f882  mov     edx, 17Ch; void *
0x18007f887  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007f88c  jmp     short loc_18007F8F5
0x18007f88e  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18007f895  jge     short loc_18007F8B3
0x18007f897  lea     rax, [rsp+58h+var_28]
0x18007f89c  mov     r9d, 1
0x18007f8a2  lea     rdx, ManagementServiceStartSuccess
0x18007f8a9  mov     qword ptr [rsp+58h+var_38], rax; int
0x18007f8ae  call    McGenEventWrite_EventWriteTransfer
0x18007f8b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18007f8ba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18007f8bf  test    al, al
0x18007f8c1  jz      short loc_18007F8E5
0x18007f8c3  call    ?EventCurrentOsVersion@AutoPilot@Service@EnterpriseDeviceManagement@@YAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::EventCurrentOsVersion(void)
0x18007f8c8  test    eax, eax
0x18007f8ca  jns     short loc_18007F8E5
0x18007f8cc  mov     rcx, [rsp+58h]; this
0x18007f8d1  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x18007f8d8  mov     r9d, eax; char *
0x18007f8db  mov     edx, 184h; void *
0x18007f8e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f8e5  mov     rcx, cs:qword_18029E3E8; hHandle
0x18007f8ec  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007f8ef  call    cs:__imp_WaitForSingleObject
0x18007f8f5  call    ?ServiceShutdown@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceShutdown(void)
0x18007f8fa  test    edi, edi
0x18007f8fc  js      short loc_18007F923
0x18007f8fe  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18007f905  jge     short loc_18007F923
0x18007f907  lea     rax, [rsp+58h+var_28]
0x18007f90c  mov     r9d, 1
0x18007f912  lea     rdx, ManagementServiceShutdown
0x18007f919  mov     qword ptr [rsp+58h+var_38], rax
0x18007f91e  call    McGenEventWrite_EventWriteTransfer
0x18007f923  mov     rcx, [rsp+58h+var_18]
0x18007f928  xor     rcx, rsp; StackCookie
0x18007f92b  call    __security_check_cookie
0x18007f930  add     rsp, 50h
0x18007f934  pop     rdi
0x18007f935  retn
```
