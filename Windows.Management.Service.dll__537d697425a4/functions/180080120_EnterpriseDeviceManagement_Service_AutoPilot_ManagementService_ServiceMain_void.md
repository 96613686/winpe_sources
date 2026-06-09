# EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceMain(void)

- ea: `0x180080120`
- end: `0x1800802f5`
- name: `?ServiceMain@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAXXZ`
- size: `469`
- prototype: `void __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180081320`

## callees

- `0x18000b8f0`
- `0x180073768`
- `0x180077d0c`
- `0x18007e26c`
- `0x18007ff54`
- `0x180080120`
- `0x1800802fc`
- `0x180080b6c`
- `0x180080c10`
- `0x1800810f0`
- `0x180081150`
- `0x18008e378`
- `0x18008e664`
- `0x1800b50d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800802a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800802a7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180080146`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180080146`

## string_xrefs

- `0x180080192`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x1800801c3`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x1800801f4`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x180080230`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`
- `0x180080289`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`

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
  int v6; // eax
  Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *Instance; // rax
  int v8; // eax
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // edi
  EnterpriseDeviceManagement::Service::AutoPilot::ManagementService *v14; // rcx
  EnterpriseDeviceManagement::Service::AutoPilot *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  int *v19; // [rsp+20h] [rbp-38h]
  int v20[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  hServiceStatus = RegisterServiceCtrlHandlerExW(
                     lpServiceName,
                     EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceControlCallback,
                     0);
  if ( hServiceStatus )
  {
    v6 = EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotGlobals::Initialize((EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotGlobals *)&EnterpriseDeviceManagement::Service::AutoPilot::g_singleton);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
        (const char *)(unsigned int)v6,
        (int)v19);
    Instance = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance();
    v8 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(Instance, hServiceStatus);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
        (const char *)(unsigned int)v8,
        (int)v19);
    v10 = EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(v9);
    v13 = v10;
    if ( v10 >= 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        v19 = v20;
        McGenEventWrite_EventWriteTransfer(v11, ManagementServiceStartSuccess, v12, 1);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
      {
        v16 = EnterpriseDeviceManagement::Service::AutoPilot::EventCurrentOsVersion(v15);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
            (const char *)(unsigned int)v16,
            (int)v19);
      }
      WaitForSingleObject(qword_1802A34E8, 0xFFFFFFFF);
    }
    else
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x40) != 0 )
        McTemplateU0q_EventWriteTransfer(v11, ManagementServiceStartFailed, (unsigned int)v10);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
        (const char *)(unsigned int)v13,
        (int)v19);
    }
    EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceShutdown(v14);
    if ( v13 >= 0 && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      McGenEventWrite_EventWriteTransfer(v17, ManagementServiceShutdown, v18, 1);
  }
  else
  {
    wil::details::in1diag3::_Log_NullAlloc(retaddr, v1, v2, v3);
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x40) != 0 )
    {
      v19 = v20;
      McGenEventWrite_EventWriteTransfer(v4, ManagementServiceRegistrationFailed, v5, 1);
    }
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\dllsrv\\servicemain.cpp",
      (const char *)0x8007000ELL,
      (int)v19);
  }
}

```

## disassembly

```asm
0x180080120  push    rdi
0x180080122  sub     rsp, 50h
0x180080126  mov     rax, cs:__security_cookie
0x18008012d  xor     rax, rsp
0x180080130  mov     [rsp+58h+var_18], rax
0x180080135  mov     rcx, cs:lpServiceName; lpServiceName
0x18008013c  lea     rdx, ?ServiceControlCallback@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@CAKKKPEAX0@Z; lpHandlerProc
0x180080143  xor     r8d, r8d; lpContext
0x180080146  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18008014d  nop     dword ptr [rax+rax+00h]
0x180080152  mov     cs:hServiceStatus, rax
0x180080159  test    rax, rax
0x18008015c  jnz     short loc_1800801AE
0x18008015e  mov     rcx, [rsp+58h]; this
0x180080163  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x180080168  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 40h
0x18008016f  jz      short loc_18008018D
0x180080171  lea     rax, [rsp+58h+var_28]
0x180080176  mov     r9d, 1
0x18008017c  lea     rdx, ManagementServiceRegistrationFailed
0x180080183  mov     qword ptr [rsp+58h+var_38], rax; int
0x180080188  call    McGenEventWrite_EventWriteTransfer
0x18008018d  mov     rcx, [rsp+58h]; this
0x180080192  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x180080199  mov     r9d, 8007000Eh; char *
0x18008019f  mov     edx, 16Fh; void *
0x1800801a4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800801a9  jmp     loc_1800802E1
0x1800801ae  lea     rcx, ?g_singleton@AutoPilot@Service@EnterpriseDeviceManagement@@3VAutoPilotGlobals@123@A; this
0x1800801b5  call    ?Initialize@AutoPilotGlobals@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotGlobals::Initialize(void)
0x1800801ba  test    eax, eax
0x1800801bc  jns     short loc_1800801D7
0x1800801be  mov     rcx, [rsp+58h]; this
0x1800801c3  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800801ca  mov     r9d, eax; char *
0x1800801cd  mov     edx, 173h; void *
0x1800801d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800801d7  call    ?GetInstance@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAPEAV1234@XZ; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetInstance(void)
0x1800801dc  mov     rdx, cs:hServiceStatus; struct SERVICE_STATUS_HANDLE__ *
0x1800801e3  mov     rcx, rax; this
0x1800801e6  call    ?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)
0x1800801eb  test    eax, eax
0x1800801ed  jns     short loc_180080208
0x1800801ef  mov     rcx, [rsp+58h]; this
0x1800801f4  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800801fb  mov     r9d, eax; char *
0x1800801fe  mov     edx, 174h; void *
0x180080203  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080208  call    ?ServiceInitialization@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceInitialization(void)
0x18008020d  mov     edi, eax
0x18008020f  test    eax, eax
0x180080211  jns     short loc_180080246
0x180080213  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 40h
0x18008021a  jz      short loc_18008022B
0x18008021c  mov     r8d, eax
0x18008021f  lea     rdx, ManagementServiceStartFailed
0x180080226  call    McTemplateU0q_EventWriteTransfer
0x18008022b  mov     rcx, [rsp+58h]; this
0x180080230  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x180080237  mov     r9d, edi; char *
0x18008023a  mov     edx, 17Ch; void *
0x18008023f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180080244  jmp     short loc_1800802B3
0x180080246  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18008024d  jge     short loc_18008026B
0x18008024f  lea     rax, [rsp+58h+var_28]
0x180080254  mov     r9d, 1
0x18008025a  lea     rdx, ManagementServiceStartSuccess
0x180080261  mov     qword ptr [rsp+58h+var_38], rax; int
0x180080266  call    McGenEventWrite_EventWriteTransfer
0x18008026b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180080272  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180080277  test    al, al
0x180080279  jz      short loc_18008029D
0x18008027b  call    ?EventCurrentOsVersion@AutoPilot@Service@EnterpriseDeviceManagement@@YAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::EventCurrentOsVersion(void)
0x180080280  test    eax, eax
0x180080282  jns     short loc_18008029D
0x180080284  mov     rcx, [rsp+58h]; this
0x180080289  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\moderndeployment\\au"...
0x180080290  mov     r9d, eax; char *
0x180080293  mov     edx, 184h; void *
0x180080298  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008029d  mov     rcx, cs:qword_1802A34E8; hHandle
0x1800802a4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800802a7  call    cs:__imp_WaitForSingleObject
0x1800802ae  nop     dword ptr [rax+rax+00h]
0x1800802b3  call    ?ServiceShutdown@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceShutdown(void)
0x1800802b8  test    edi, edi
0x1800802ba  js      short loc_1800802E1
0x1800802bc  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x1800802c3  jge     short loc_1800802E1
0x1800802c5  lea     rax, [rsp+58h+var_28]
0x1800802ca  mov     r9d, 1
0x1800802d0  lea     rdx, ManagementServiceShutdown
0x1800802d7  mov     qword ptr [rsp+58h+var_38], rax
0x1800802dc  call    McGenEventWrite_EventWriteTransfer
0x1800802e1  mov     rcx, [rsp+58h+var_18]
0x1800802e6  xor     rcx, rsp; StackCookie
0x1800802e9  call    __security_check_cookie
0x1800802ee  add     rsp, 50h
0x1800802f2  pop     rdi
0x1800802f3  retn
```
