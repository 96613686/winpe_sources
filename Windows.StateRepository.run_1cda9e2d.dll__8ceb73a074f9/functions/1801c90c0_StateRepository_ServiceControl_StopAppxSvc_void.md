# StateRepository::ServiceControl::StopAppxSvc(void)

- ea: `0x1801c90c0`
- end: `0x1801c938f`
- name: `?StopAppxSvc@ServiceControl@StateRepository@@YAJXZ`
- size: `719`
- prototype: `__int64 __fastcall(StateRepository::ServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18016d6b0`

## callees

- `0x18000e8dc`
- `0x180018400`
- `0x18001a9e0`
- `0x18006a278`
- `0x1800b4dbc`
- `0x18018f650`
- `0x180190234`
- `0x1801c87d4`
- `0x1801c90c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1801c92b3`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1801c92b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c9201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c92fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c933a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c9201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c92fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c933a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801c91da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801c91da`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1801c914d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1801c914d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1801c9298`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1801c9298`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801c91f7`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801c91f7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801c910d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801c910d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801c90e7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801c90e7`

## string_xrefs

- `0x1801c915b`: `onecore\base\appmodel\StateRepository\common\inc\ServiceControl.hpp`
- `0x1801c91a1`: `onecore\base\appmodel\StateRepository\common\inc\ServiceControl.hpp`
- `0x1801c924f`: `onecore\base\appmodel\StateRepository\common\inc\ServiceControl.hpp`
- `0x1801c9320`: `onecore\base\appmodel\StateRepository\common\inc\ServiceControl.hpp`
- `0x1801c9357`: `onecore\base\appmodel\StateRepository\common\inc\ServiceControl.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ServiceControl::StopAppxSvc(StateRepository::ServiceControl *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  StateRepository::Time *v3; // rcx
  const char *v4; // r9
  signed int v5; // eax
  signed int dwNotificationStatus; // ebx
  int v7; // edi
  unsigned __int64 UnbiasedInterruptTimeAsMSec; // rsi
  DWORD v9; // eax
  StateRepository::Time *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  bool v13; // sf
  signed int v15; // eax
  signed int LastError; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-99h]
  char *v18; // [rsp+28h] [rbp-91h]
  DWORD v19; // [rsp+30h] [rbp-89h] BYREF
  SC_HANDLE v20; // [rsp+38h] [rbp-81h] BYREF
  SC_HANDLE v21[2]; // [rsp+40h] [rbp-79h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+50h] [rbp-69h] BYREF
  BYTE Buffer[16]; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-9h]
  int v25; // [rsp+C0h] [rbp+7h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v1 = OpenSCManagerW(0, 0, 1u);
  v20 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    dwNotificationStatus = LastError;
    if ( LastError > 0 )
      dwNotificationStatus = (unsigned __int16)LastError | 0x80070000;
    if ( dwNotificationStatus < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\common\\inc\\ServiceControl.hpp",
        (const char *)(unsigned int)dwNotificationStatus,
        pcbBytesNeeded);
    goto LABEL_44;
  }
  v21[0] = OpenServiceW(v1, L"appxsvc", 0x24u);
  v2 = v21[0];
  if ( !v21[0] )
  {
    v15 = GetLastError();
    dwNotificationStatus = v15;
    if ( v15 > 0 )
      dwNotificationStatus = (unsigned __int16)v15 | 0x80070000;
    if ( dwNotificationStatus >= 0 )
      goto LABEL_39;
    v11 = 20;
    goto LABEL_38;
  }
  v25 = 0;
  v19 = 0;
  *(_OWORD *)Buffer = 0;
  v24 = 0;
  if ( QueryServiceStatusEx(v21[0], SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v19) )
  {
    if ( *(_DWORD *)&Buffer[4] == 1 )
      goto LABEL_33;
    if ( *(_DWORD *)&Buffer[4] != 2 )
    {
      if ( *(_DWORD *)&Buffer[4] == 3 )
      {
LABEL_25:
        *(_QWORD *)&pNotifyBuffer.dwVersion = 2;
        pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        memset_0(&pNotifyBuffer.pContext, 0, 0x40u);
        v9 = NotifyServiceStatusChangeW(v2, 1u, &pNotifyBuffer);
        if ( v9 )
        {
          v12 = 84;
LABEL_23:
          v5 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v12,
                 (unsigned int)"onecore\\base\\appmodel\\StateRepository\\common\\inc\\ServiceControl.hpp",
                 (const char *)v9,
                 pcbBytesNeeded);
          goto LABEL_5;
        }
        if ( SleepEx(0x1D4C0u, 1) != 192 )
        {
          dwNotificationStatus = -2147023436;
          v11 = 87;
LABEL_38:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\base\\appmodel\\StateRepository\\common\\inc\\ServiceControl.hpp",
            (const char *)(unsigned int)dwNotificationStatus,
            pcbBytesNeeded);
          goto LABEL_39;
        }
        dwNotificationStatus = pNotifyBuffer.dwNotificationStatus;
        v13 = (pNotifyBuffer.dwNotificationStatus & 0x80000000) != 0;
        if ( (int)pNotifyBuffer.dwNotificationStatus > 0 )
        {
          dwNotificationStatus = LOWORD(pNotifyBuffer.dwNotificationStatus) | 0x80070000;
          v13 = 1;
        }
        if ( v13 )
        {
          v11 = 88;
          goto LABEL_38;
        }
LABEL_33:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v21);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
        return 0;
      }
      if ( *(_DWORD *)&Buffer[4] != 4 )
      {
        LODWORD(v18) = *(_DWORD *)&Buffer[4];
        dwNotificationStatus = -2147418113;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\common\\inc\\ServiceControl.hpp",
          (const char *)0x8000FFFFLL,
          (int)"appxsvc status=%u",
          v18);
        goto LABEL_39;
      }
    }
    v7 = 0;
    UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v3);
    while ( 1 )
    {
      if ( (unsigned int)++v7 > 1 )
        Sleep(0x64u);
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(v2, 1u, &ServiceStatus) )
        goto LABEL_25;
      v9 = GetLastError();
      if ( v9 == 1062 )
        goto LABEL_24;
      if ( v9 != 1052 && v9 != 1061 && v9 != 1460 )
      {
        if ( v9 )
        {
          v12 = 73;
          goto LABEL_23;
        }
LABEL_24:
        dwNotificationStatus = 0;
        goto LABEL_39;
      }
      if ( StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v10) - UnbiasedInterruptTimeAsMSec >= 0x1388 )
      {
        dwNotificationStatus = -2147023436;
        v11 = 78;
        goto LABEL_38;
      }
    }
  }
  v5 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x19,
         (unsigned int)"onecore\\base\\appmodel\\StateRepository\\common\\inc\\ServiceControl.hpp",
         v4);
LABEL_5:
  dwNotificationStatus = v5;
LABEL_39:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v21);
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
  return (unsigned int)dwNotificationStatus;
}

```

## disassembly

```asm
0x1801c90c0  push    rbp
0x1801c90c2  push    rbx
0x1801c90c3  push    rsi
0x1801c90c4  push    rdi
0x1801c90c5  lea     rbp, [rsp-3Fh]
0x1801c90ca  sub     rsp, 0F8h
0x1801c90d1  mov     rax, cs:__security_cookie
0x1801c90d8  xor     rax, rsp
0x1801c90db  mov     [rbp+57h+var_28], rax
0x1801c90df  xor     edx, edx; lpDatabaseName
0x1801c90e1  xor     ecx, ecx; lpMachineName
0x1801c90e3  lea     r8d, [rdx+1]; dwDesiredAccess
0x1801c90e7  call    cs:__imp_OpenSCManagerW
0x1801c90ed  mov     [rsp+110h+var_D8], rax
0x1801c90f2  test    rax, rax
0x1801c90f5  jz      loc_1801C933A
0x1801c90fb  mov     edi, 24h ; '$'
0x1801c9100  lea     rdx, aAppxsvc; "appxsvc"
0x1801c9107  mov     r8d, edi; dwDesiredAccess
0x1801c910a  mov     rcx, rax; hSCManager
0x1801c910d  call    cs:__imp_OpenServiceW
0x1801c9113  mov     [rbp+57h+var_D0], rax
0x1801c9117  mov     rbx, rax
0x1801c911a  test    rax, rax
0x1801c911d  jz      loc_1801C92FE
0x1801c9123  xor     eax, eax
0x1801c9125  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1801c9129  xorps   xmm0, xmm0
0x1801c912c  mov     [rbp+57h+var_50], eax
0x1801c912f  mov     [rsp+110h+var_E0], eax
0x1801c9133  mov     r9d, edi; cbBufSize
0x1801c9136  lea     rax, [rsp+110h+var_E0]
0x1801c913b  xor     edx, edx; InfoLevel
0x1801c913d  mov     rcx, rbx; hService
0x1801c9140  mov     [rsp+110h+pcbBytesNeeded], rax; unsigned int
0x1801c9145  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1801c9149  movups  [rbp+57h+var_60], xmm0
0x1801c914d  call    cs:__imp_QueryServiceStatusEx
0x1801c9153  test    eax, eax
0x1801c9155  jnz     short loc_1801C9171
0x1801c9157  mov     rcx, [rbp+5Fh]; this
0x1801c915b  lea     r8, aOnecoreBaseApp_186; "onecore\\base\\appmodel\\StateRepositor"...
0x1801c9162  lea     edx, [rdi-0Bh]; void *
0x1801c9165  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801c916a  mov     ebx, eax
0x1801c916c  jmp     loc_1801C932F
0x1801c9171  mov     edx, dword ptr [rbp+57h+Buffer+4]
0x1801c9174  mov     eax, edx
0x1801c9176  sub     eax, 1
0x1801c9179  jz      loc_1801C92E7
0x1801c917f  sub     eax, 1
0x1801c9182  jz      short loc_1801C91C4
0x1801c9184  sub     eax, 1
0x1801c9187  jz      loc_1801C926A
0x1801c918d  cmp     eax, 1
0x1801c9190  jz      short loc_1801C91C4
0x1801c9192  mov     rcx, [rbp+5Fh]; this
0x1801c9196  lea     rax, aAppxsvcStatusU; "appxsvc status=%u"
0x1801c919d  mov     dword ptr [rsp+110h+var_E8], edx; char *
0x1801c91a1  lea     r8, aOnecoreBaseApp_186; "onecore\\base\\appmodel\\StateRepositor"...
0x1801c91a8  mov     ebx, 8000FFFFh
0x1801c91ad  mov     [rsp+110h+pcbBytesNeeded], rax; int
0x1801c91b2  mov     r9d, ebx; char *
0x1801c91b5  mov     edx, 2Bh ; '+'; void *
0x1801c91ba  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c91bf  jmp     loc_1801C932F
0x1801c91c4  xor     edi, edi
0x1801c91c6  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801c91cb  mov     rsi, rax
0x1801c91ce  inc     edi
0x1801c91d0  cmp     edi, 1
0x1801c91d3  jbe     short loc_1801C91E0
0x1801c91d5  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1801c91da  call    cs:__imp_Sleep
0x1801c91e0  xorps   xmm0, xmm0
0x1801c91e3  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1801c91e7  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1801c91eb  mov     edx, 1; dwControl
0x1801c91f0  mov     rcx, rbx; hService
0x1801c91f3  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1801c91f7  call    cs:__imp_ControlService
0x1801c91fd  test    eax, eax
0x1801c91ff  jnz     short loc_1801C926A
0x1801c9201  call    cs:__imp_GetLastError
0x1801c9207  cmp     eax, 426h
0x1801c920c  jz      short loc_1801C9263
0x1801c920e  cmp     eax, 41Ch
0x1801c9213  jz      short loc_1801C9223
0x1801c9215  cmp     eax, 425h
0x1801c921a  jz      short loc_1801C9223
0x1801c921c  cmp     eax, 5B4h
0x1801c9221  jnz     short loc_1801C9242
0x1801c9223  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801c9228  sub     rax, rsi
0x1801c922b  cmp     rax, 1388h
0x1801c9231  jb      short loc_1801C91CE
0x1801c9233  mov     ebx, 800705B4h
0x1801c9238  mov     edx, 4Eh ; 'N'
0x1801c923d  jmp     loc_1801C931C
0x1801c9242  test    eax, eax
0x1801c9244  jz      short loc_1801C9263
0x1801c9246  mov     edx, 49h ; 'I'; void *
0x1801c924b  mov     rcx, [rbp+5Fh]; this
0x1801c924f  lea     r8, aOnecoreBaseApp_186; "onecore\\base\\appmodel\\StateRepositor"...
0x1801c9256  mov     r9d, eax; char *
0x1801c9259  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801c925e  jmp     loc_1801C916A
0x1801c9263  xor     ebx, ebx
0x1801c9265  jmp     loc_1801C932F
0x1801c926a  xor     edx, edx; Val
0x1801c926c  mov     qword ptr [rbp+57h+pNotifyBuffer.dwVersion], 2
0x1801c9274  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1801c927b  lea     rcx, [rbp+57h+pNotifyBuffer.pContext]; void *
0x1801c927f  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x1801c9283  lea     r8d, [rdx+40h]; Size
0x1801c9287  call    memset_0
0x1801c928c  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x1801c9290  mov     edx, 1; dwNotifyMask
0x1801c9295  mov     rcx, rbx; hService
0x1801c9298  call    cs:__imp_NotifyServiceStatusChangeW
0x1801c929e  test    eax, eax
0x1801c92a0  jz      short loc_1801C92A9
0x1801c92a2  mov     edx, 54h ; 'T'
0x1801c92a7  jmp     short loc_1801C924B
0x1801c92a9  mov     edx, 1; bAlertable
0x1801c92ae  mov     ecx, 1D4C0h; dwMilliseconds
0x1801c92b3  call    cs:__imp_SleepEx
0x1801c92b9  cmp     eax, 0C0h
0x1801c92be  jz      short loc_1801C92CC
0x1801c92c0  mov     ebx, 800705B4h
0x1801c92c5  mov     edx, 57h ; 'W'
0x1801c92ca  jmp     short loc_1801C931C
0x1801c92cc  mov     ebx, [rbp+57h+pNotifyBuffer.dwNotificationStatus]
0x1801c92cf  test    ebx, ebx
0x1801c92d1  jle     short loc_1801C92DE
0x1801c92d3  movzx   ebx, bx
0x1801c92d6  or      ebx, 80070000h
0x1801c92dc  test    ebx, ebx
0x1801c92de  jns     short loc_1801C92E7
0x1801c92e0  mov     edx, 58h ; 'X'
0x1801c92e5  jmp     short loc_1801C931C
0x1801c92e7  lea     rcx, [rbp+57h+var_D0]
0x1801c92eb  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801c92f0  lea     rcx, [rsp+110h+var_D8]
0x1801c92f5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801c92fa  xor     eax, eax
0x1801c92fc  jmp     short loc_1801C9377
0x1801c92fe  call    cs:__imp_GetLastError
0x1801c9304  mov     ebx, eax
0x1801c9306  test    eax, eax
0x1801c9308  jle     short loc_1801C9313
0x1801c930a  movzx   ebx, ax
0x1801c930d  or      ebx, 80070000h
0x1801c9313  test    ebx, ebx
0x1801c9315  jns     short loc_1801C932F
0x1801c9317  mov     edx, 14h; void *
0x1801c931c  mov     rcx, [rbp+5Fh]; this
0x1801c9320  lea     r8, aOnecoreBaseApp_186; "onecore\\base\\appmodel\\StateRepositor"...
0x1801c9327  mov     r9d, ebx; char *
0x1801c932a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c932f  lea     rcx, [rbp+57h+var_D0]
0x1801c9333  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801c9338  jmp     short loc_1801C936B
0x1801c933a  call    cs:__imp_GetLastError
0x1801c9340  mov     ebx, eax
0x1801c9342  test    eax, eax
0x1801c9344  jle     short loc_1801C934F
0x1801c9346  movzx   ebx, ax
0x1801c9349  or      ebx, 80070000h
0x1801c934f  test    ebx, ebx
0x1801c9351  jns     short loc_1801C936B
0x1801c9353  mov     rcx, [rbp+5Fh]; this
0x1801c9357  lea     r8, aOnecoreBaseApp_186; "onecore\\base\\appmodel\\StateRepositor"...
0x1801c935e  mov     r9d, ebx; char *
0x1801c9361  mov     edx, 11h; void *
0x1801c9366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c936b  lea     rcx, [rsp+110h+var_D8]
0x1801c9370  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801c9375  mov     eax, ebx
0x1801c9377  mov     rcx, [rbp+57h+var_28]
0x1801c937b  xor     rcx, rsp; StackCookie
0x1801c937e  call    __security_check_cookie
0x1801c9383  add     rsp, 0F8h
0x1801c938a  pop     rdi
0x1801c938b  pop     rsi
0x1801c938c  pop     rbx
0x1801c938d  pop     rbp
0x1801c938e  retn
```
