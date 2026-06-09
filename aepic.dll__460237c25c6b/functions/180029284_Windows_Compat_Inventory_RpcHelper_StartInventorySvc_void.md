# Windows::Compat::Inventory::RpcHelper::StartInventorySvc(void)

- ea: `0x180029284`
- end: `0x18002955b`
- name: `?StartInventorySvc@RpcHelper@Inventory@Compat@Windows@@SAJXZ`
- size: `727`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800260e8`
- `0x180027900`

## callees

- `0x180005890`
- `0x180006938`
- `0x18002923c`
- `0x180029284`
- `0x180029564`
- `0x1800295dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002947d`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002947d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002935d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002935d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293fa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180029344`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180029344`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800293f0`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800293f0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800292e0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800292e0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002937a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002937a`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180029457`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180029457`

## string_xrefs

- `0x180029301`: `OpenSCManager failed [%d]`
- `0x180029312`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x1800293d7`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x180029428`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x180029497`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x1800294c5`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x1800294f5`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x180029513`: `Windows::Compat::Inventory::RpcHelper::StartInventorySvc`
- `0x180029363`: `OpenService failed [%d]`
- `0x18002938a`: `QueryServiceStatus failed [%d]`
- `0x180029409`: `StartService failed [%d]`
- `0x18002941b`: `Waiting for InventorySvc to complete startup`
- `0x180029463`: `NotifyServiceStatusChangeW failed [%d]`
- `0x18002948a`: `Waiting for Notify Service callback timed out`
- `0x1800294e8`: `ServiceStatus isn't running [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Windows::Compat::Inventory::RpcHelper::StartInventorySvc(void)
{
  SC_HANDLE v0; // rax
  DWORD LastError; // eax
  const char *v2; // r9
  __int64 v3; // r8
  signed int dwNotificationStatus; // edi
  SC_HANDLE v5; // rax
  SC_HANDLE hService; // [rsp+30h] [rbp-39h] BYREF
  SC_HANDLE hSCManager; // [rsp+38h] [rbp-31h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+40h] [rbp-29h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+90h] [rbp+27h] BYREF

  hService = 0;
  hSCManager = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v0 = OpenSCManagerW(0, 0, 1u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    &hSCManager,
    v0);
  if ( !hSCManager )
  {
    LastError = GetLastError();
    v2 = "OpenSCManager failed [%d]";
    v3 = 25;
LABEL_3:
    dwNotificationStatus = LastError;
LABEL_4:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::RpcHelper::StartInventorySvc", v3, v2, dwNotificationStatus);
    goto LABEL_5;
  }
  v5 = OpenServiceW(hSCManager, L"InventorySvc", 0x14u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    &hService,
    v5);
  if ( !hService )
  {
    LastError = GetLastError();
    v2 = "OpenService failed [%d]";
    v3 = 34;
    goto LABEL_3;
  }
  if ( !QueryServiceStatus(hService, &ServiceStatus) )
  {
    LastError = GetLastError();
    v2 = "QueryServiceStatus failed [%d]";
    v3 = 42;
    goto LABEL_3;
  }
  switch ( ServiceStatus.dwCurrentState )
  {
    case 1u:
      goto LABEL_17;
    case 2u:
      goto LABEL_20;
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_29:
      AslLogCallPrintf(3, "Windows::Compat::Inventory::RpcHelper::StartInventorySvc", 102, "InventorySvc is running");
      goto LABEL_30;
  }
  if ( ServiceStatus.dwCurrentState != 5 )
  {
    if ( ServiceStatus.dwCurrentState - 6 > 1 )
    {
LABEL_30:
      dwNotificationStatus = 0;
      goto LABEL_31;
    }
LABEL_17:
    AslLogCallPrintf(3, "Windows::Compat::Inventory::RpcHelper::StartInventorySvc", 54, "Starting InventorySvc");
    if ( !StartServiceW(hService, 0, 0) )
    {
      dwNotificationStatus = GetLastError();
      if ( dwNotificationStatus != 1056 )
      {
        v2 = "StartService failed [%d]";
        v3 = 60;
        goto LABEL_4;
      }
    }
  }
LABEL_20:
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::RpcHelper::StartInventorySvc",
    69,
    "Waiting for InventorySvc to complete startup");
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)ServiceNotifyCallback;
  dwNotificationStatus = NotifyServiceStatusChangeW(hService, 8u, &pNotifyBuffer);
  if ( dwNotificationStatus )
  {
    v2 = "NotifyServiceStatusChangeW failed [%d]";
    v3 = 76;
    goto LABEL_4;
  }
  if ( SleepEx(0x2710u, 1) != 192 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::RpcHelper::StartInventorySvc",
      83,
      "Waiting for Notify Service callback timed out");
LABEL_24:
    dwNotificationStatus = -2147467259;
    goto LABEL_31;
  }
  if ( !pNotifyBuffer.dwNotificationStatus )
  {
    if ( pNotifyBuffer.ServiceStatus.dwCurrentState != 4 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::RpcHelper::StartInventorySvc",
        97,
        "ServiceStatus isn't running [%d]",
        pNotifyBuffer.ServiceStatus.dwCurrentState);
      goto LABEL_24;
    }
    goto LABEL_29;
  }
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::RpcHelper::StartInventorySvc",
    90,
    "NotificationStatus failed [%d]",
    pNotifyBuffer.dwNotificationStatus);
  dwNotificationStatus = pNotifyBuffer.dwNotificationStatus;
LABEL_5:
  if ( dwNotificationStatus > 0 )
    dwNotificationStatus = (unsigned __int16)dwNotificationStatus | 0x80070000;
LABEL_31:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hSCManager);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hService);
  return (unsigned int)dwNotificationStatus;
}

```

## disassembly

```asm
0x180029284  mov     [rsp-8+arg_0], rdi
0x180029289  mov     [rsp-8+arg_8], r14
0x18002928e  push    rbp
0x18002928f  lea     rbp, [rsp-57h]
0x180029294  sub     rsp, 0C0h
0x18002929b  mov     rax, cs:__security_cookie
0x1800292a2  xor     rax, rsp
0x1800292a5  mov     [rbp+57h+var_10], rax
0x1800292a9  mov     [rbp+57h+hService], 0
0x1800292b1  mov     [rbp+57h+hSCManager], 0
0x1800292b9  xorps   xmm0, xmm0
0x1800292bc  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1800292c0  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800292c4  xor     edx, edx; Val
0x1800292c6  lea     r8d, [rdx+50h]; Size
0x1800292ca  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x1800292ce  call    memset_0
0x1800292d3  mov     r14d, 1
0x1800292d9  mov     r8d, r14d; dwDesiredAccess
0x1800292dc  xor     edx, edx; lpDatabaseName
0x1800292de  xor     ecx, ecx; lpMachineName
0x1800292e0  call    cs:__imp_OpenSCManagerW
0x1800292e6  mov     rdx, rax
0x1800292e9  lea     rcx, [rbp+57h+hSCManager]
0x1800292ed  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800292f2  mov     rcx, [rbp+57h+hSCManager]; hSCManager
0x1800292f6  test    rcx, rcx
0x1800292f9  jnz     short loc_180029337
0x1800292fb  call    cs:__imp_GetLastError
0x180029301  lea     r9, aOpenscmanagerF; "OpenSCManager failed [%d]"
0x180029308  lea     r8d, [r14+18h]
0x18002930c  mov     edi, eax
0x18002930e  mov     [rsp+0C0h+var_A0], edi
0x180029312  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x180029319  mov     ecx, r14d
0x18002931c  call    AslLogCallPrintf
0x180029321  test    edi, edi
0x180029323  jle     loc_180029525
0x180029329  movzx   edi, di
0x18002932c  or      edi, 80070000h
0x180029332  jmp     loc_180029525
0x180029337  mov     r8d, 14h; dwDesiredAccess
0x18002933d  lea     rdx, ServiceName; "InventorySvc"
0x180029344  call    cs:__imp_OpenServiceW
0x18002934a  mov     rdx, rax
0x18002934d  lea     rcx, [rbp+57h+hService]
0x180029351  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180029356  cmp     [rbp+57h+hService], 0
0x18002935b  jnz     short loc_180029372
0x18002935d  call    cs:__imp_GetLastError
0x180029363  lea     r9, aOpenserviceFai; "OpenService failed [%d]"
0x18002936a  mov     r8d, 22h ; '"'
0x180029370  jmp     short loc_18002930C
0x180029372  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180029376  mov     rcx, [rbp+57h+hService]; hService
0x18002937a  call    cs:__imp_QueryServiceStatus
0x180029380  test    eax, eax
0x180029382  jnz     short loc_18002939C
0x180029384  call    cs:__imp_GetLastError
0x18002938a  lea     r9, aQueryservicest; "QueryServiceStatus failed [%d]"
0x180029391  mov     r8d, 2Ah ; '*'
0x180029397  jmp     loc_18002930C
0x18002939c  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x18002939f  sub     eax, r14d
0x1800293a2  jz      short loc_1800293CA
0x1800293a4  sub     eax, r14d
0x1800293a7  jz      short loc_18002941B
0x1800293a9  sub     eax, r14d
0x1800293ac  jz      short loc_1800293CA
0x1800293ae  sub     eax, r14d
0x1800293b1  jz      loc_180029506
0x1800293b7  sub     eax, r14d
0x1800293ba  jz      short loc_18002941B
0x1800293bc  sub     eax, r14d
0x1800293bf  jz      short loc_1800293CA
0x1800293c1  cmp     eax, r14d
0x1800293c4  jnz     loc_180029523
0x1800293ca  lea     r9, aStartingInvent_0; "Starting InventorySvc"
0x1800293d1  mov     r8d, 36h ; '6'
0x1800293d7  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x1800293de  lea     ecx, [r8-33h]
0x1800293e2  call    AslLogCallPrintf
0x1800293e7  xor     r8d, r8d; lpServiceArgVectors
0x1800293ea  xor     edx, edx; dwNumServiceArgs
0x1800293ec  mov     rcx, [rbp+57h+hService]; hService
0x1800293f0  call    cs:__imp_StartServiceW
0x1800293f6  test    eax, eax
0x1800293f8  jnz     short loc_18002941B
0x1800293fa  call    cs:__imp_GetLastError
0x180029400  mov     edi, eax
0x180029402  cmp     eax, 420h
0x180029407  jz      short loc_18002941B
0x180029409  lea     r9, aStartserviceFa; "StartService failed [%d]"
0x180029410  mov     r8d, 3Ch ; '<'
0x180029416  jmp     loc_18002930E
0x18002941b  lea     r9, aWaitingForInve; "Waiting for InventorySvc to complete st"...
0x180029422  mov     r8d, 45h ; 'E'
0x180029428  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x18002942f  lea     ecx, [r8-42h]
0x180029433  call    AslLogCallPrintf
0x180029438  mov     [rbp+57h+pNotifyBuffer.dwVersion], 2
0x18002943f  lea     rax, ?ServiceNotifyCallback@@YAXPEAX@Z; ServiceNotifyCallback(void *)
0x180029446  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x18002944a  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x18002944e  mov     edx, 8; dwNotifyMask
0x180029453  mov     rcx, [rbp+57h+hService]; hService
0x180029457  call    cs:__imp_NotifyServiceStatusChangeW
0x18002945d  mov     edi, eax
0x18002945f  test    eax, eax
0x180029461  jz      short loc_180029475
0x180029463  lea     r9, aNotifyservices; "NotifyServiceStatusChangeW failed [%d]"
0x18002946a  mov     r8d, 4Ch ; 'L'
0x180029470  jmp     loc_18002930E
0x180029475  mov     edx, r14d; bAlertable
0x180029478  mov     ecx, 2710h; dwMilliseconds
0x18002947d  call    cs:__imp_SleepEx
0x180029483  cmp     eax, 0C0h
0x180029488  jz      short loc_1800294AD
0x18002948a  lea     r9, aWaitingForNoti; "Waiting for Notify Service callback tim"...
0x180029491  mov     r8d, 53h ; 'S'
0x180029497  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x18002949e  mov     ecx, r14d
0x1800294a1  call    AslLogCallPrintf
0x1800294a6  mov     edi, 80004005h
0x1800294ab  jmp     short loc_180029525
0x1800294ad  mov     eax, [rbp+57h+pNotifyBuffer.dwNotificationStatus]
0x1800294b0  test    eax, eax
0x1800294b2  jz      short loc_1800294DC
0x1800294b4  mov     [rsp+0C0h+var_A0], eax
0x1800294b8  lea     r9, aNotificationst; "NotificationStatus failed [%d]"
0x1800294bf  mov     r8d, 5Ah ; 'Z'
0x1800294c5  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x1800294cc  mov     ecx, r14d
0x1800294cf  call    AslLogCallPrintf
0x1800294d4  mov     edi, [rbp+57h+pNotifyBuffer.dwNotificationStatus]
0x1800294d7  jmp     loc_180029321
0x1800294dc  mov     eax, [rbp+57h+pNotifyBuffer.ServiceStatus.dwCurrentState]
0x1800294df  cmp     eax, 4
0x1800294e2  jz      short loc_180029506
0x1800294e4  mov     [rsp+0C0h+var_A0], eax
0x1800294e8  lea     r9, aServicestatusI; "ServiceStatus isn't running [%d]"
0x1800294ef  mov     r8d, 61h ; 'a'
0x1800294f5  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x1800294fc  mov     ecx, r14d
0x1800294ff  call    AslLogCallPrintf
0x180029504  jmp     short loc_1800294A6
0x180029506  lea     r9, aInventorysvcIs; "InventorySvc is running"
0x18002950d  mov     r8d, 66h ; 'f'
0x180029513  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::RpcHelper::"...
0x18002951a  lea     ecx, [r8-63h]
0x18002951e  call    AslLogCallPrintf
0x180029523  xor     edi, edi
0x180029525  lea     rcx, [rbp+57h+hSCManager]
0x180029529  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002952e  nop
0x18002952f  lea     rcx, [rbp+57h+hService]
0x180029533  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180029538  mov     eax, edi
0x18002953a  mov     rcx, [rbp+57h+var_10]
0x18002953e  xor     rcx, rsp; StackCookie
0x180029541  call    __security_check_cookie
0x180029546  lea     r11, [rsp+0C0h+var_s0]
0x18002954e  mov     rdi, [r11+10h]
0x180029552  mov     r14, [r11+18h]
0x180029556  mov     rsp, r11
0x180029559  pop     rbp
0x18002955a  retn
```
