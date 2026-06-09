# Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanServiceChanges(void)

- ea: `0x1800158dc`
- end: `0x180015a7e`
- name: `?_StartListeningToWwanServiceChanges@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBMediaManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001c0cc`

## callees

- `0x18000ad20`
- `0x1800158dc`
- `0x18001b1b4`
- `0x18001b1d4`
- `0x1800265dc`
- `0x18002cd20`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015a24`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015a51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015a5c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015a24`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015a51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015a5c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180015910`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180015910`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001594f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001594f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800159fc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800159fc`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800159a0`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800159a0`

## string_xrefs

- `0x180015a42`: `Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanServiceChanges`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanServiceChanges(
        Windows::Networking::UX::Internal::MBMediaManager *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rdi
  SC_HANDLE v6; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rbx
  unsigned int LastError; // esi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  SC_HANDLE v13; // [rsp+30h] [rbp-78h] BYREF
  SC_HANDLE v14; // [rsp+38h] [rbp-70h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-68h] BYREF
  WCHAR ServiceName[8]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  wcscpy(ServiceName, L"wwansvc");
  v2 = OpenSCManagerW(0, 0, 1u);
  v14 = v2;
  v4 = v2;
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x250,
             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
             v3);
  v6 = OpenServiceW(v2, ServiceName, 4u);
  v13 = v6;
  v8 = v6;
  if ( v6 )
  {
    v10 = SubscribeServiceChangeNotifications(
            v6,
            2,
            Windows::Networking::UX::Internal::MBMediaManager::s_WwanServiceStatusNotification,
            this);
    if ( v10 )
    {
      *((_QWORD *)this + 21) = 0;
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x25F,
              (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
              (const char *)v10,
              (int)this + 168);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
      return v11;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v8, &ServiceStatus) )
    {
      *((_DWORD *)this + 40) = ServiceStatus.dwCurrentState;
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanServiceChanges",
        0x266u,
        "Started listening for WwanSvc changes");
      CloseServiceHandle(v8);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x263,
                    (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
                    v12);
      CloseServiceHandle(v8);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x256,
                  (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
                  v7);
  }
  CloseServiceHandle(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800158dc  push    rbx
0x1800158de  push    rsi
0x1800158df  push    rdi
0x1800158e0  push    r14
0x1800158e2  sub     rsp, 88h
0x1800158e9  mov     rax, cs:__security_cookie
0x1800158f0  xor     rax, rsp
0x1800158f3  mov     [rsp+0A8h+var_38], rax
0x1800158f8  movups  xmm0, xmmword ptr cs:aWwansvc; "wwansvc"
0x1800158ff  xor     edx, edx; lpDatabaseName
0x180015901  mov     rsi, rcx
0x180015904  xor     ecx, ecx; lpMachineName
0x180015906  movdqu  xmmword ptr [rsp+0A8h+ServiceName], xmm0
0x18001590c  lea     r8d, [rdx+1]; dwDesiredAccess
0x180015910  call    cs:__imp_OpenSCManagerW
0x180015916  mov     [rsp+0A8h+var_70], rax
0x18001591b  mov     rdi, rax
0x18001591e  test    rax, rax
0x180015921  jnz     short loc_180015941
0x180015923  mov     rcx, [rsp+0A8h]; this
0x18001592b  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180015932  mov     edx, 250h; void *
0x180015937  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001593c  jmp     loc_180015A64
0x180015941  mov     r8d, 4; dwDesiredAccess
0x180015947  lea     rdx, [rsp+0A8h+ServiceName]; lpServiceName
0x18001594c  mov     rcx, rdi; hSCManager
0x18001594f  call    cs:__imp_OpenServiceW
0x180015955  mov     [rsp+0A8h+var_78], rax
0x18001595a  mov     rbx, rax
0x18001595d  test    rax, rax
0x180015960  jnz     short loc_180015982
0x180015962  mov     rcx, [rsp+0A8h]; this
0x18001596a  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180015971  mov     edx, 256h; void *
0x180015976  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001597b  mov     esi, eax
0x18001597d  jmp     loc_180015A59
0x180015982  lea     r14, [rsi+0A8h]
0x180015989  mov     r9, rsi
0x18001598c  lea     r8, ?s_WwanServiceStatusNotification@MBMediaManager@Internal@UX@Networking@Windows@@SAXKPEAX@Z; Windows::Networking::UX::Internal::MBMediaManager::s_WwanServiceStatusNotification(ulong,void *)
0x180015993  mov     qword ptr [rsp+0A8h+var_88], r14; unsigned int
0x180015998  mov     edx, 2
0x18001599d  mov     rcx, rbx
0x1800159a0  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800159a6  test    eax, eax
0x1800159a8  jz      short loc_1800159E7
0x1800159aa  mov     rcx, [rsp+0A8h]; this
0x1800159b2  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800159b9  mov     r9d, eax; char *
0x1800159bc  mov     qword ptr [r14], 0
0x1800159c3  mov     edx, 25Fh; void *
0x1800159c8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800159cd  lea     rcx, [rsp+0A8h+var_78]
0x1800159d2  mov     ebx, eax
0x1800159d4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800159d9  lea     rcx, [rsp+0A8h+var_70]
0x1800159de  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800159e3  mov     eax, ebx
0x1800159e5  jmp     short loc_180015A64
0x1800159e7  xorps   xmm0, xmm0
0x1800159ea  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800159ef  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1800159f4  mov     rcx, rbx; hService
0x1800159f7  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800159fc  call    cs:__imp_QueryServiceStatus
0x180015a02  test    eax, eax
0x180015a04  jnz     short loc_180015A2C
0x180015a06  mov     rcx, [rsp+0A8h]; this
0x180015a0e  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180015a15  mov     edx, 263h; void *
0x180015a1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015a1f  mov     rcx, rbx; hSCObject
0x180015a22  mov     esi, eax
0x180015a24  call    cs:__imp_CloseServiceHandle
0x180015a2a  jmp     short loc_180015A59
0x180015a2c  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x180015a30  lea     r8, aStartedListeni; "Started listening for WwanSvc changes"
0x180015a37  mov     edx, 266h; unsigned int
0x180015a3c  mov     [rsi+0A0h], eax
0x180015a42  lea     rcx, aWindowsNetwork_27; "Windows::Networking::UX::Internal::MBMe"...
0x180015a49  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180015a4e  mov     rcx, rbx; hSCObject
0x180015a51  call    cs:__imp_CloseServiceHandle
0x180015a57  xor     esi, esi
0x180015a59  mov     rcx, rdi; hSCObject
0x180015a5c  call    cs:__imp_CloseServiceHandle
0x180015a62  mov     eax, esi
0x180015a64  mov     rcx, [rsp+0A8h+var_38]
0x180015a69  xor     rcx, rsp; StackCookie
0x180015a6c  call    __security_check_cookie
0x180015a71  add     rsp, 88h
0x180015a78  pop     r14
0x180015a7a  pop     rdi
0x180015a7b  pop     rsi
0x180015a7c  pop     rbx
0x180015a7d  retn
```
