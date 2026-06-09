# DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(ulong,ulong,ulong)

- ea: `0x18001260c`
- end: `0x180012850`
- name: `?_ChangeSpoolerServiceState@ConfigurationManager@DeviceConfiguration@@AEAAJKKK@Z`
- size: `580`
- prototype: `__int64 __fastcall(DeviceConfiguration::ConfigurationManager *this, int, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180012df8`
- `0x180013600`

## callees

- `0x1800020c0`
- `0x18000b7f8`
- `0x18000b92c`
- `0x18000c19c`
- `0x18000f9ec`
- `0x18001260c`
- `0x180013644`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800126fb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800127c0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800126fb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800127c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012779`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001263e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001263e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800127f3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800127f3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012682`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012682`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800126c1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180012708`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800126c1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180012708`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001276b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800127d2`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001276b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800127d2`

## string_xrefs

- `0x18001265e`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x18001264f`: `OpenSCManager failed!`
- `0x180012693`: `OpenService failed!`
- `0x1800126d0`: `QueryServiceStatus failed!`
- `0x180012717`: `QueryServiceStatus failed!`
- `0x180012795`: `ControlService (Service Stop) failed! Hr: 0x%x`
- `0x18001279c`: `DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState`
- `0x1800127d8`: `ControlService (Service Stop) failed!`
- `0x1800127f9`: `StartService failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(
        DeviceConfiguration::ConfigurationManager *this,
        int a2,
        int a3,
        int a4)
{
  SC_HANDLE v7; // rdi
  SC_HANDLE v8; // rbx
  BOOL v9; // eax
  DWORD dwCurrentState; // eax
  int v11; // esi
  BOOL v12; // eax
  signed int LastError; // eax
  signed int v14; // esi
  __int64 v15; // r8
  DeviceConfiguration::ConfigurationManager *v16; // rcx
  BOOL v17; // eax
  BOOL started; // eax
  const char *v20; // [rsp+28h] [rbp-48h]
  const char *v21; // [rsp+28h] [rbp-48h]
  SC_HANDLE v22; // [rsp+30h] [rbp-40h] BYREF
  SC_HANDLE v23; // [rsp+38h] [rbp-38h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v7 = OpenSCManagerW(0, 0, 0xF003Fu);
  v23 = v7;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    (int)retaddr,
    626,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (__int64)v7,
    (__int64)"OpenSCManager failed!");
  v8 = OpenServiceW(v7, L"Spooler", 0xF01FFu);
  v22 = v8;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    (int)retaddr,
    629,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (__int64)v8,
    (__int64)"OpenService failed!");
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v9 = QueryServiceStatus(v8, &ServiceStatus);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x278,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)!v9,
    (bool)"QueryServiceStatus failed!",
    v20);
  dwCurrentState = ServiceStatus.dwCurrentState;
  if ( a2 == ServiceStatus.dwCurrentState )
  {
    v11 = 0;
    while ( 1 )
    {
      Sleep(0x3E8u);
      v12 = QueryServiceStatus(v8, &ServiceStatus);
      wil::details::in1diag3::Throw_GetLastErrorIfMsg(
        retaddr,
        (void *)0x27F,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
        (const char *)!v12,
        (bool)"QueryServiceStatus failed!",
        v21);
      dwCurrentState = ServiceStatus.dwCurrentState;
      if ( a3 == ServiceStatus.dwCurrentState )
        break;
      if ( (unsigned int)++v11 >= 5 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    if ( a3 != dwCurrentState )
      goto LABEL_16;
  }
  if ( a4 == 16 )
  {
    started = StartServiceW(v8, 0, 0);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)!started,
      (bool)"StartService failed!",
      v21);
  }
  else if ( a4 == 32 && !ControlService(v8, 1u, &ServiceStatus) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    else
      v15 = (unsigned int)LastError;
    DeviceConfigurationTelemetry::WriteDbgTraceWarning(
      "DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState",
      L"ControlService (Service Stop) failed! Hr: 0x%x",
      v15);
    if ( v14 == 1051 )
      DeviceConfiguration::ConfigurationManager::_StopDependentServices(v16, v7, v8);
    Sleep(0x3E8u);
    v17 = ControlService(v8, 1u, &ServiceStatus);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x29B,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)!v17,
      (bool)"ControlService (Service Stop) failed!",
      v21);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v22);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v23);
  return 0;
}

```

## disassembly

```asm
0x18001260c  push    rbp
0x18001260e  push    rbx
0x18001260f  push    rsi
0x180012610  push    rdi
0x180012611  push    r13
0x180012613  push    r14
0x180012615  push    r15
0x180012617  mov     rbp, rsp
0x18001261a  sub     rsp, 70h
0x18001261e  mov     rax, cs:__security_cookie
0x180012625  xor     rax, rsp
0x180012628  mov     [rbp+var_10], rax
0x18001262c  mov     r14d, r9d
0x18001262f  mov     r15d, r8d
0x180012632  mov     esi, edx
0x180012634  xor     edx, edx; lpDatabaseName
0x180012636  xor     ecx, ecx; lpMachineName
0x180012638  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001263e  call    cs:__imp_OpenSCManagerW
0x180012644  mov     rdi, rax
0x180012647  mov     [rbp+var_38], rax
0x18001264b  mov     rcx, [rbp+38h]
0x18001264f  lea     rax, aOpenscmanagerF; "OpenSCManager failed!"
0x180012656  mov     qword ptr [rsp+70h+var_50], rax
0x18001265b  mov     r9, rdi
0x18001265e  lea     r13, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012665  mov     r8, r13
0x180012668  mov     edx, 272h
0x18001266d  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x180012672  mov     r8d, 0F01FFh; dwDesiredAccess
0x180012678  lea     rdx, aSpooler; "Spooler"
0x18001267f  mov     rcx, rdi; hSCManager
0x180012682  call    cs:__imp_OpenServiceW
0x180012688  mov     rbx, rax
0x18001268b  mov     [rbp+var_40], rax
0x18001268f  mov     rcx, [rbp+38h]
0x180012693  lea     rax, aOpenserviceFai; "OpenService failed!"
0x18001269a  mov     qword ptr [rsp+70h+var_50], rax
0x18001269f  mov     r9, rbx
0x1800126a2  mov     r8, r13
0x1800126a5  mov     edx, 275h
0x1800126aa  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x1800126af  xorps   xmm0, xmm0
0x1800126b2  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1800126b6  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1800126ba  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800126be  mov     rcx, rbx; hService
0x1800126c1  call    cs:__imp_QueryServiceStatus
0x1800126c7  test    eax, eax
0x1800126c9  setz    al
0x1800126cc  mov     rcx, [rbp+38h]; this
0x1800126d0  lea     rdx, aQueryservicest_0; "QueryServiceStatus failed!"
0x1800126d7  mov     qword ptr [rsp+70h+var_50], rdx; bool
0x1800126dc  movzx   r9d, al; char *
0x1800126e0  mov     r8, r13; unsigned int
0x1800126e3  mov     edx, 278h; void *
0x1800126e8  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800126ed  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x1800126f0  cmp     esi, eax
0x1800126f2  jnz     short loc_180012743
0x1800126f4  xor     esi, esi
0x1800126f6  mov     ecx, 3E8h; dwMilliseconds
0x1800126fb  call    cs:__imp_Sleep
0x180012701  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180012705  mov     rcx, rbx; hService
0x180012708  call    cs:__imp_QueryServiceStatus
0x18001270e  test    eax, eax
0x180012710  setz    al
0x180012713  mov     rcx, [rbp+38h]; this
0x180012717  lea     rdx, aQueryservicest_0; "QueryServiceStatus failed!"
0x18001271e  mov     qword ptr [rsp+70h+var_50], rdx; bool
0x180012723  movzx   r9d, al; char *
0x180012727  mov     r8, r13; unsigned int
0x18001272a  mov     edx, 27Fh; void *
0x18001272f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180012734  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x180012737  cmp     r15d, eax
0x18001273a  jz      short loc_18001274C
0x18001273c  inc     esi
0x18001273e  cmp     esi, 5
0x180012741  jb      short loc_1800126F6
0x180012743  cmp     r15d, eax
0x180012746  jnz     loc_180012820
0x18001274c  cmp     r14d, 10h
0x180012750  jz      loc_1800127EB
0x180012756  cmp     r14d, 20h ; ' '
0x18001275a  jnz     loc_180012820
0x180012760  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x180012764  lea     edx, [r14-1Fh]; dwControl
0x180012768  mov     rcx, rbx; hService
0x18001276b  call    cs:__imp_ControlService
0x180012771  test    eax, eax
0x180012773  jnz     loc_180012820
0x180012779  call    cs:__imp_GetLastError
0x18001277f  mov     esi, eax
0x180012781  test    eax, eax
0x180012783  jg      short loc_18001278A
0x180012785  mov     r8d, eax
0x180012788  jmp     short loc_180012795
0x18001278a  movzx   r8d, si
0x18001278e  or      r8d, 80070000h
0x180012795  lea     rdx, aControlservice_0; "ControlService (Service Stop) failed! H"...
0x18001279c  lea     rcx, aDeviceconfigur; "DeviceConfiguration::ConfigurationManag"...
0x1800127a3  call    ?WriteDbgTraceWarning@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800127a8  cmp     esi, 41Bh
0x1800127ae  jnz     short loc_1800127BB
0x1800127b0  mov     r8, rbx; struct SC_HANDLE__ *
0x1800127b3  mov     rdx, rdi; struct SC_HANDLE__ *
0x1800127b6  call    ?_StopDependentServices@ConfigurationManager@DeviceConfiguration@@AEAAXPEAUSC_HANDLE__@@0@Z; DeviceConfiguration::ConfigurationManager::_StopDependentServices(SC_HANDLE__ *,SC_HANDLE__ *)
0x1800127bb  mov     ecx, 3E8h; dwMilliseconds
0x1800127c0  call    cs:__imp_Sleep
0x1800127c6  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x1800127ca  mov     edx, 1; dwControl
0x1800127cf  mov     rcx, rbx; hService
0x1800127d2  call    cs:__imp_ControlService
0x1800127d8  lea     rdx, aControlservice_1; "ControlService (Service Stop) failed!"
0x1800127df  mov     qword ptr [rsp+70h+var_50], rdx
0x1800127e4  mov     edx, 29Bh
0x1800127e9  jmp     short loc_18001280A
0x1800127eb  xor     r8d, r8d; lpServiceArgVectors
0x1800127ee  xor     edx, edx; dwNumServiceArgs
0x1800127f0  mov     rcx, rbx; hService
0x1800127f3  call    cs:__imp_StartServiceW
0x1800127f9  lea     rdx, aStartserviceFa; "StartService failed!"
0x180012800  mov     qword ptr [rsp+70h+var_50], rdx; bool
0x180012805  mov     edx, 2A1h; void *
0x18001280a  test    eax, eax
0x18001280c  setz    al
0x18001280f  movzx   r9d, al; char *
0x180012813  mov     r8, r13; unsigned int
0x180012816  mov     rcx, [rbp+38h]; this
0x18001281a  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001281f  nop
0x180012820  lea     rcx, [rbp+var_40]
0x180012824  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180012829  nop
0x18001282a  lea     rcx, [rbp+var_38]
0x18001282e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180012833  xor     eax, eax
0x180012835  mov     rcx, [rbp+var_10]
0x180012839  xor     rcx, rsp; StackCookie
0x18001283c  call    __security_check_cookie
0x180012841  add     rsp, 70h
0x180012845  pop     r15
0x180012847  pop     r14
0x180012849  pop     r13
0x18001284b  pop     rdi
0x18001284c  pop     rsi
0x18001284d  pop     rbx
0x18001284e  pop     rbp
0x18001284f  retn
```
