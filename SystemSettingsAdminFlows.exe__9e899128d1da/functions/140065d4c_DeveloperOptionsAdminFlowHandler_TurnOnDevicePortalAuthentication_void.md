# DeveloperOptionsAdminFlowHandler::TurnOnDevicePortalAuthentication(void)

- ea: `0x140065d4c`
- end: `0x140065e9e`
- name: `?TurnOnDevicePortalAuthentication@DeveloperOptionsAdminFlowHandler@@SAJXZ`
- size: `338`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x14000ed38`
- `0x14001f3d4`
- `0x14001f3f8`
- `0x14002c070`
- `0x1400341e0`
- `0x140036308`
- `0x1400646c8`
- `0x140065110`
- `0x140065200`
- `0x140065c6c`
- `0x140065d4c`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140065dbe`
- `KERNEL32!RegOpenKeyExW` at `0x140065dbe`
- `KERNEL32!RegSetValueExW` at `0x140065dfb`
- `KERNEL32!RegSetValueExW` at `0x140065dfb`

## string_xrefs

- `0x140065db0`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WebManagement\Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DeveloperOptionsAdminFlowHandler::TurnOnDevicePortalAuthentication(void)
{
  HKEY *v0; // rax
  unsigned int v1; // eax
  __int64 v2; // rdx
  unsigned int v3; // ebx
  int started; // eax
  __int64 v5; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-188h]
  BYTE Data[8]; // [rsp+30h] [rbp-178h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-170h] BYREF
  _QWORD v10[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v10);
  v10[0] = &DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication::`vftable';
  DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication::StartActivity((DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication *)v10);
  hKey = 0;
  v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WebManagement\\Service",
         0,
         2u,
         v0);
  if ( v1 )
  {
    v2 = 216;
LABEL_5:
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v2,
           (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\developeroptions\\developeroptionsadminflowhandler.cpp",
           (const char *)v1,
           phkResult);
    goto LABEL_12;
  }
  *(_DWORD *)Data = 1;
  v1 = RegSetValueExW(hKey, L"UseDefaultAuthorizer", 0, 4u, Data, 4u);
  if ( v1 )
  {
    v2 = 225;
    goto LABEL_5;
  }
  started = DeveloperOptionsAdminFlowHandler::StopDevicePortalService();
  v3 = started;
  if ( started >= 0 )
  {
    started = DeveloperOptionsAdminFlowHandler::StartDevicePortalService();
    v3 = started;
    if ( started >= 0 )
    {
      wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v10,
        0);
      v3 = 0;
      goto LABEL_12;
    }
    v5 = 228;
  }
  else
  {
    v5 = 227;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\developeroptions\\developeroptionsadminflowhandler.cpp",
    (const char *)(unsigned int)started,
    phkResult);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication::~TurnOnDevicePortalAuthentication((DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication *)v10);
  return v3;
}

```

## disassembly

```asm
0x140065d4c  push    rbx
0x140065d4e  sub     rsp, 1A0h
0x140065d55  mov     rax, cs:__security_cookie
0x140065d5c  xor     rax, rsp
0x140065d5f  mov     [rsp+1A8h+var_18], rax
0x140065d67  lea     rdx, aTurnondevicepo; "TurnOnDevicePortalAuthentication"
0x140065d6e  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x140065d73  call    ??0?$ActivityBase@VSettingsAdminFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140065d78  lea     rax, ??_7TurnOnDevicePortalAuthentication@DeveloperOptionsAdminFlowTelemetry@@6B@; const DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication::`vftable'
0x140065d7f  mov     [rsp+1A8h+var_168], rax
0x140065d84  lea     rcx, [rsp+1A8h+var_168]; this
0x140065d89  call    ?StartActivity@TurnOnDevicePortalAuthentication@DeveloperOptionsAdminFlowTelemetry@@QEAAXXZ; DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication::StartActivity(void)
0x140065d8e  nop
0x140065d8f  mov     [rsp+1A8h+hKey], 0
0x140065d98  lea     rcx, [rsp+1A8h+hKey]
0x140065d9d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140065da2  mov     [rsp+1A8h+phkResult], rax; phkResult
0x140065da7  mov     r9d, 2; samDesired
0x140065dad  xor     r8d, r8d; ulOptions
0x140065db0  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140065db7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140065dbe  call    cs:__imp_RegOpenKeyExW
0x140065dc4  test    eax, eax
0x140065dc6  jz      short loc_140065DCF
0x140065dc8  mov     edx, 0D8h
0x140065dcd  jmp     short loc_140065E0A
0x140065dcf  mov     dword ptr [rsp+1A8h+Data], 1
0x140065dd7  mov     r9d, 4; dwType
0x140065ddd  mov     [rsp+1A8h+cbData], r9d; cbData
0x140065de2  lea     rax, [rsp+1A8h+Data]
0x140065de7  mov     [rsp+1A8h+phkResult], rax; int
0x140065dec  xor     r8d, r8d; Reserved
0x140065def  lea     rdx, aUsedefaultauth; "UseDefaultAuthorizer"
0x140065df6  mov     rcx, [rsp+1A8h+hKey]; hKey
0x140065dfb  call    cs:__imp_RegSetValueExW
0x140065e01  test    eax, eax
0x140065e03  jz      short loc_140065E25
0x140065e05  mov     edx, 0E1h; void *
0x140065e0a  lea     r8, aPcshellShellSy_32; "pcshell\\shell\\systemsettings\\adminfl"...
0x140065e11  mov     r9d, eax; char *
0x140065e14  mov     rcx, [rsp+1A8h]; this
0x140065e1c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140065e21  mov     ebx, eax
0x140065e23  jmp     short loc_140065E6E
0x140065e25  call    ?StopDevicePortalService@DeveloperOptionsAdminFlowHandler@@SAJXZ; DeveloperOptionsAdminFlowHandler::StopDevicePortalService(void)
0x140065e2a  mov     ebx, eax
0x140065e2c  test    eax, eax
0x140065e2e  jns     short loc_140065E4E
0x140065e30  mov     edx, 0E3h; void *
0x140065e35  lea     r8, aPcshellShellSy_32; "pcshell\\shell\\systemsettings\\adminfl"...
0x140065e3c  mov     r9d, eax; char *
0x140065e3f  mov     rcx, [rsp+1A8h]; this
0x140065e47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140065e4c  jmp     short loc_140065E6E
0x140065e4e  call    ?StartDevicePortalService@DeveloperOptionsAdminFlowHandler@@SAJXZ; DeveloperOptionsAdminFlowHandler::StartDevicePortalService(void)
0x140065e53  mov     ebx, eax
0x140065e55  test    eax, eax
0x140065e57  jns     short loc_140065E60
0x140065e59  mov     edx, 0E4h
0x140065e5e  jmp     short loc_140065E35
0x140065e60  xor     edx, edx
0x140065e62  lea     rcx, [rsp+1A8h+var_168]
0x140065e67  call    ?Stop@?$ActivityBase@VSettingsAdminFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SettingsAdminFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140065e6c  xor     ebx, ebx
0x140065e6e  lea     rcx, [rsp+1A8h+hKey]
0x140065e73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140065e78  nop
0x140065e79  lea     rcx, [rsp+1A8h+var_168]; this
0x140065e7e  call    ??1TurnOnDevicePortalAuthentication@DeveloperOptionsAdminFlowTelemetry@@QEAA@XZ; DeveloperOptionsAdminFlowTelemetry::TurnOnDevicePortalAuthentication::~TurnOnDevicePortalAuthentication(void)
0x140065e83  mov     eax, ebx
0x140065e85  mov     rcx, [rsp+1A8h+var_18]
0x140065e8d  xor     rcx, rsp; StackCookie
0x140065e90  call    __security_check_cookie
0x140065e95  add     rsp, 1A0h
0x140065e9c  pop     rbx
0x140065e9d  retn
```
