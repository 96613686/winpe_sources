# StartMaintenance

- ea: `0x180009730`
- end: `0x18000980b`
- name: `StartMaintenance`
- size: `219`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x180007228`
- `0x180008a18`
- `0x180009730`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180009785`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180009785`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000974d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000974d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800097d1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800097d1`

## string_xrefs

- `0x180009762`: `shellcommon\shell\sharedpc\accountmanager\dll\service.cpp`
- `0x18000979d`: `shellcommon\shell\sharedpc\accountmanager\dll\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 StartMaintenance()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  unsigned int LastError; // ebx
  SC_HANDLE v3; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  SC_HANDLE v7; // [rsp+20h] [rbp-48h] BYREF
  SC_HANDLE v8; // [rsp+28h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 1u);
  v8 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"shpamsvc", 0x100u);
    v7 = v3;
    if ( v3 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(v3, 0x80u, &ServiceStatus) )
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v7);
        LastError = 0;
        goto LABEL_9;
      }
      v5 = 66;
    }
    else
    {
      v5 = 60;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\dll\\service.cpp",
                  v4);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x39,
                  (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\dll\\service.cpp",
                  v1);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v8);
  return LastError;
}

```

## disassembly

```asm
0x180009730  push    rbx
0x180009732  sub     rsp, 60h
0x180009736  mov     rax, cs:__security_cookie
0x18000973d  xor     rax, rsp
0x180009740  mov     [rsp+68h+var_18], rax
0x180009745  xor     edx, edx; lpDatabaseName
0x180009747  xor     ecx, ecx; lpMachineName
0x180009749  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000974d  call    cs:__imp_OpenSCManagerW
0x180009753  mov     [rsp+68h+var_40], rax
0x180009758  test    rax, rax
0x18000975b  jnz     short loc_180009775
0x18000975d  mov     rcx, [rsp+68h]; this
0x180009762  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\sharedpc\\accountma"...
0x180009769  lea     edx, [rax+39h]; void *
0x18000976c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009771  mov     ebx, eax
0x180009773  jmp     short loc_1800097EC
0x180009775  mov     r8d, 100h; dwDesiredAccess
0x18000977b  lea     rdx, ServiceName; "shpamsvc"
0x180009782  mov     rcx, rax; hSCManager
0x180009785  call    cs:__imp_OpenServiceW
0x18000978b  mov     [rsp+68h+var_48], rax
0x180009790  test    rax, rax
0x180009793  jnz     short loc_1800097B7
0x180009795  lea     edx, [rax+3Ch]; void *
0x180009798  mov     rcx, [rsp+68h]; this
0x18000979d  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800097a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800097a9  lea     rcx, [rsp+68h+var_48]
0x1800097ae  mov     ebx, eax
0x1800097b0  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800097b5  jmp     short loc_1800097EC
0x1800097b7  xorps   xmm0, xmm0
0x1800097ba  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1800097bf  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1800097c4  mov     edx, 80h; dwControl
0x1800097c9  mov     rcx, rax; hService
0x1800097cc  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800097d1  call    cs:__imp_ControlService
0x1800097d7  test    eax, eax
0x1800097d9  jnz     short loc_1800097E0
0x1800097db  lea     edx, [rax+42h]
0x1800097de  jmp     short loc_180009798
0x1800097e0  lea     rcx, [rsp+68h+var_48]
0x1800097e5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800097ea  xor     ebx, ebx
0x1800097ec  lea     rcx, [rsp+68h+var_40]
0x1800097f1  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800097f6  mov     eax, ebx
0x1800097f8  mov     rcx, [rsp+68h+var_18]
0x1800097fd  xor     rcx, rsp; StackCookie
0x180009800  call    __security_check_cookie
0x180009805  add     rsp, 60h
0x180009809  pop     rbx
0x18000980a  retn
```
