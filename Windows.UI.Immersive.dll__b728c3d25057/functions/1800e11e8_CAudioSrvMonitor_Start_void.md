# CAudioSrvMonitor::Start(void)

- ea: `0x1800e11e8`
- end: `0x1800e133a`
- name: `?Start@CAudioSrvMonitor@@QEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(CAudioSrvMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800e07d0`

## callees

- `0x180034768`
- `0x180034c6c`
- `0x180050ba0`
- `0x1800e1184`
- `0x1800e11e8`
- `0x1800e1340`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e1253`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e1253`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e1218`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e1218`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e12a0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e12a0`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800e12db`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800e12db`

## string_xrefs

- `0x1800e1209`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CAudioSrvMonitor::Start(CAudioSrvMonitor *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  unsigned int v4; // ebx
  SC_HANDLE v5; // rax
  const char *v6; // r9
  SC_HANDLE v7; // rbx
  __int64 v8; // rdx
  unsigned int LastError; // eax
  unsigned int v10; // eax
  SC_HANDLE v12; // [rsp+30h] [rbp-48h] BYREF
  SC_HANDLE v13; // [rsp+38h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v13 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"AudioSrv", 4u);
    v12 = v5;
    v7 = v5;
    if ( v5 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v5, &ServiceStatus) )
      {
        *((_DWORD *)this + 5) = ServiceStatus.dwCurrentState;
        wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
          (char *)this + 24,
          0);
        v10 = SubscribeServiceChangeNotifications(v7, 2, CAudioSrvMonitor::AudioSrvStatusChangedCallback, this);
        if ( !v10 )
        {
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
          v4 = 0;
          goto LABEL_12;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x25,
                      (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                      (const char *)v10,
                      (int)this + 24);
        goto LABEL_6;
      }
      v8 = 28;
    }
    else
    {
      v8 = 24;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                  v6);
LABEL_6:
    v4 = LastError;
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
    goto LABEL_12;
  }
  v4 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x14,
         (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
         v3);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
  return v4;
}

```

## disassembly

```asm
0x1800e11e8  mov     [rsp+arg_8], rbx
0x1800e11ed  mov     [rsp+arg_10], rsi
0x1800e11f2  push    rdi
0x1800e11f3  sub     rsp, 70h
0x1800e11f7  mov     rax, cs:__security_cookie
0x1800e11fe  xor     rax, rsp
0x1800e1201  mov     [rsp+78h+var_18], rax
0x1800e1206  mov     rsi, rcx
0x1800e1209  lea     rdx, DatabaseName; "ServicesActive"
0x1800e1210  xor     ecx, ecx; lpMachineName
0x1800e1212  mov     r8d, 1; dwDesiredAccess
0x1800e1218  call    cs:__imp_OpenSCManagerW
0x1800e121e  mov     [rsp+78h+var_40], rax
0x1800e1223  test    rax, rax
0x1800e1226  jnz     short loc_1800E1243
0x1800e1228  mov     rcx, [rsp+78h]; this
0x1800e122d  lea     r8, aShellTwinuiPla_0; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800e1234  lea     edx, [rax+14h]; void *
0x1800e1237  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e123c  mov     ebx, eax
0x1800e123e  jmp     loc_1800E130F
0x1800e1243  mov     r8d, 4; dwDesiredAccess
0x1800e1249  lea     rdx, ServiceName; "AudioSrv"
0x1800e1250  mov     rcx, rax; hSCManager
0x1800e1253  call    cs:__imp_OpenServiceW
0x1800e1259  mov     [rsp+78h+var_48], rax
0x1800e125e  mov     rbx, rax
0x1800e1261  test    rax, rax
0x1800e1264  jnz     short loc_1800E128B
0x1800e1266  lea     edx, [rax+18h]; void *
0x1800e1269  mov     rcx, [rsp+78h]; this
0x1800e126e  lea     r8, aShellTwinuiPla_0; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800e1275  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e127a  lea     rcx, [rsp+78h+var_48]
0x1800e127f  mov     ebx, eax
0x1800e1281  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e1286  jmp     loc_1800E130F
0x1800e128b  xorps   xmm0, xmm0
0x1800e128e  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800e1293  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800e1298  mov     rcx, rbx; hService
0x1800e129b  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800e12a0  call    cs:__imp_QueryServiceStatus
0x1800e12a6  test    eax, eax
0x1800e12a8  jnz     short loc_1800E12AF
0x1800e12aa  lea     edx, [rax+1Ch]
0x1800e12ad  jmp     short loc_1800E1269
0x1800e12af  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x1800e12b3  lea     rdi, [rsi+18h]
0x1800e12b7  mov     rcx, rdi
0x1800e12ba  mov     [rsi+14h], eax
0x1800e12bd  xor     edx, edx
0x1800e12bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x1800e12c4  mov     r9, rsi
0x1800e12c7  mov     qword ptr [rsp+78h+var_58], rdi; unsigned int
0x1800e12cc  lea     r8, ?AudioSrvStatusChangedCallback@CAudioSrvMonitor@@SAXKPEAX@Z; CAudioSrvMonitor::AudioSrvStatusChangedCallback(ulong,void *)
0x1800e12d3  mov     edx, 2
0x1800e12d8  mov     rcx, rbx
0x1800e12db  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800e12e1  test    eax, eax
0x1800e12e3  jz      short loc_1800E1303
0x1800e12e5  mov     rcx, [rsp+78h]; this
0x1800e12ea  lea     r8, aShellTwinuiPla_0; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800e12f1  mov     r9d, eax; char *
0x1800e12f4  mov     edx, 25h ; '%'; void *
0x1800e12f9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e12fe  jmp     loc_1800E127A
0x1800e1303  lea     rcx, [rsp+78h+var_48]
0x1800e1308  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e130d  xor     ebx, ebx
0x1800e130f  lea     rcx, [rsp+78h+var_40]
0x1800e1314  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e1319  mov     eax, ebx
0x1800e131b  mov     rcx, [rsp+78h+var_18]
0x1800e1320  xor     rcx, rsp; StackCookie
0x1800e1323  call    __security_check_cookie
0x1800e1328  lea     r11, [rsp+78h+var_8]
0x1800e132d  mov     rbx, [r11+18h]
0x1800e1331  mov     rsi, [r11+20h]
0x1800e1335  mov     rsp, r11
0x1800e1338  pop     rdi
0x1800e1339  retn
```
