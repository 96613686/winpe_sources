# CAudioSrvMonitor::Start(void)

- ea: `0x18003d1f8`
- end: `0x18003d3d2`
- name: `?Start@CAudioSrvMonitor@@QEAAJXZ`
- size: `474`
- prototype: `__int64 __fastcall(CAudioSrvMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18003cf90`

## callees

- `0x18003d1f8`
- `0x18003d434`
- `0x1800b7544`
- `0x1800f1a00`
- `0x180108c7c`
- `0x180142e10`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d303`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d313`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d37d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d38d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d303`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d313`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d37d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003d38d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003d222`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003d222`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003d27a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003d27a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003d2ac`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003d2ac`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18003d2ec`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18003d2ec`

## string_xrefs

- `0x18003d219`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSrvMonitor::Start(CAudioSrvMonitor *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rsi
  SC_HANDLE v6; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rdi
  const char *v9; // r9
  unsigned int v10; // eax
  unsigned int LastError; // ebx
  SC_HANDLE v12; // [rsp+30h] [rbp-68h] BYREF
  SC_HANDLE v13; // [rsp+38h] [rbp-60h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v4 = v2;
  v13 = v2;
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x14,
             (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
             v3);
  v6 = OpenServiceW(v2, L"AudioSrv", 4u);
  v8 = v6;
  v12 = v6;
  if ( v6 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v6, &ServiceStatus) )
    {
      *((_DWORD *)this + 5) = ServiceStatus.dwCurrentState;
      wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
        (char *)this + 24,
        0);
      v10 = SubscribeServiceChangeNotifications(v8, 2, CAudioSrvMonitor::AudioSrvStatusChangedCallback, this);
      if ( !v10 )
      {
        CloseServiceHandle(v8);
        CloseServiceHandle(v4);
        return 0;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x25,
                    (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                    (const char *)v10,
                    (_DWORD)this + 24);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1C,
                    (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                    v9);
      CloseServiceHandle(v8);
      CloseServiceHandle(v4);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x18,
                  (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                  v7);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003d1f8  push    rbx
0x18003d1fa  push    rbp
0x18003d1fb  push    rsi
0x18003d1fc  push    rdi
0x18003d1fd  sub     rsp, 78h
0x18003d201  mov     rax, cs:__security_cookie
0x18003d208  xor     rax, rsp
0x18003d20b  mov     [rsp+98h+var_38], rax
0x18003d210  mov     rbp, rcx
0x18003d213  mov     r8d, 1; dwDesiredAccess
0x18003d219  lea     rdx, DatabaseName; "ServicesActive"
0x18003d220  xor     ecx, ecx; lpMachineName
0x18003d222  call    cs:__imp_OpenSCManagerW
0x18003d229  nop     dword ptr [rax+rax+00h]
0x18003d22e  mov     rsi, rax
0x18003d231  mov     [rsp+98h+var_60], rax
0x18003d236  test    rax, rax
0x18003d239  jnz     short loc_18003D26A
0x18003d23b  mov     rcx, [rsp+98h]; this
0x18003d243  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x18003d24a  lea     edx, [rax+14h]; void *
0x18003d24d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d252  nop
0x18003d253  mov     rcx, [rsp+98h+var_38]
0x18003d258  xor     rcx, rsp; StackCookie
0x18003d25b  call    __security_check_cookie
0x18003d260  add     rsp, 78h
0x18003d264  pop     rdi
0x18003d265  pop     rsi
0x18003d266  pop     rbp
0x18003d267  pop     rbx
0x18003d268  retn
0x18003d26a  mov     r8d, 4; dwDesiredAccess
0x18003d270  lea     rdx, ServiceName; "AudioSrv"
0x18003d277  mov     rcx, rsi; hSCManager
0x18003d27a  call    cs:__imp_OpenServiceW
0x18003d281  nop     dword ptr [rax+rax+00h]
0x18003d286  mov     rdi, rax
0x18003d289  mov     [rsp+98h+var_68], rax
0x18003d28e  test    rax, rax
0x18003d291  jz      loc_18003D327
0x18003d297  xorps   xmm0, xmm0
0x18003d29a  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x18003d29f  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003d2a4  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x18003d2a9  mov     rcx, rax; hService
0x18003d2ac  call    cs:__imp_QueryServiceStatus
0x18003d2b3  nop     dword ptr [rax+rax+00h]
0x18003d2b8  test    eax, eax
0x18003d2ba  jz      loc_18003D35F
0x18003d2c0  mov     eax, [rsp+98h+ServiceStatus.dwCurrentState]
0x18003d2c4  mov     [rbp+14h], eax
0x18003d2c7  lea     rbx, [rbp+18h]
0x18003d2cb  xor     edx, edx
0x18003d2cd  mov     rcx, rbx
0x18003d2d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x18003d2d5  mov     qword ptr [rsp+98h+var_78], rbx; unsigned int
0x18003d2da  mov     r9, rbp
0x18003d2dd  lea     r8, ?AudioSrvStatusChangedCallback@CAudioSrvMonitor@@SAXKPEAX@Z; CAudioSrvMonitor::AudioSrvStatusChangedCallback(ulong,void *)
0x18003d2e4  mov     edx, 2
0x18003d2e9  mov     rcx, rdi
0x18003d2ec  call    cs:__imp_SubscribeServiceChangeNotifications
0x18003d2f3  nop     dword ptr [rax+rax+00h]
0x18003d2f8  test    eax, eax
0x18003d2fa  jnz     loc_18003D39C
0x18003d300  mov     rcx, rdi; hSCObject
0x18003d303  call    cs:__imp_CloseServiceHandle
0x18003d30a  nop     dword ptr [rax+rax+00h]
0x18003d30f  nop
0x18003d310  mov     rcx, rsi; hSCObject
0x18003d313  call    cs:__imp_CloseServiceHandle
0x18003d31a  nop     dword ptr [rax+rax+00h]
0x18003d31f  nop
0x18003d320  xor     eax, eax
0x18003d322  jmp     loc_18003D253
0x18003d327  mov     rcx, [rsp+98h]; this
0x18003d32f  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x18003d336  mov     edx, 18h; void *
0x18003d33b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d340  mov     ebx, eax
0x18003d342  lea     rcx, [rsp+98h+var_68]
0x18003d347  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003d34c  nop
0x18003d34d  lea     rcx, [rsp+98h+var_60]
0x18003d352  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003d357  nop
0x18003d358  mov     eax, ebx
0x18003d35a  jmp     loc_18003D253
0x18003d35f  mov     rcx, [rsp+98h]; this
0x18003d367  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x18003d36e  mov     edx, 1Ch; void *
0x18003d373  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d378  mov     ebx, eax
0x18003d37a  mov     rcx, rdi; hSCObject
0x18003d37d  call    cs:__imp_CloseServiceHandle
0x18003d384  nop     dword ptr [rax+rax+00h]
0x18003d389  nop
0x18003d38a  mov     rcx, rsi; hSCObject
0x18003d38d  call    cs:__imp_CloseServiceHandle
0x18003d394  nop     dword ptr [rax+rax+00h]
0x18003d399  nop
0x18003d39a  jmp     short loc_18003D358
0x18003d39c  mov     rcx, [rsp+98h]; this
0x18003d3a4  mov     r9d, eax; char *
0x18003d3a7  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x18003d3ae  mov     edx, 25h ; '%'; void *
0x18003d3b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003d3b8  mov     ebx, eax
0x18003d3ba  lea     rcx, [rsp+98h+var_68]
0x18003d3bf  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003d3c4  nop
0x18003d3c5  lea     rcx, [rsp+98h+var_60]
0x18003d3ca  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003d3cf  nop
0x18003d3d0  jmp     short loc_18003D358
```
