# OSIntegration::DEH::Internal::FirewallRulesHelper::OpenFirewallStore(void * *)

- ea: `0x1800e4268`
- end: `0x1800e4688`
- name: `?OpenFirewallStore@FirewallRulesHelper@Internal@DEH@OSIntegration@@CAJPEAPEAX@Z`
- size: `1056`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800e4c80`

## callees

- `0x180001c54`
- `0x180012fc8`
- `0x180059570`
- `0x180074248`
- `0x1800864e0`
- `0x1800aed10`
- `0x1800e2c4c`
- `0x1800e4268`
- `0x1800e50d0`
- `0x1800e512c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e43dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e43dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4449`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e4332`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e4332`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e42e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e433e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e42e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e433e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e43b0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e43fb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e43b0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e43fb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e4381`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e4381`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e43cc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e4420`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e43cc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e4420`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800e42c8`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800e4317`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800e42c8`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800e4317`

## string_xrefs

- `0x1800e4378`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::FirewallRulesHelper::OpenFirewallStore(void **a1)
{
  __int64 result; // rax
  ULONGLONG TickCount64; // r14
  int v3; // edi
  DWORD v4; // esi
  DWORD LastError; // r14d
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbx
  DWORD v8; // r15d
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rax
  int v11; // edx
  unsigned __int64 v12; // r9
  unsigned int v13; // ebx
  int v14; // ecx
  unsigned int v15; // ecx
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  DWORD dwServiceSpecificExitCode; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwWin32ExitCode; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwCurrentState; // [rsp+90h] [rbp-70h] BYREF
  DWORD v22; // [rsp+98h] [rbp-68h] BYREF
  DWORD v23; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v24; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v25; // [rsp+B0h] [rbp-50h] BYREF
  DWORD v26; // [rsp+B8h] [rbp-48h] BYREF
  DWORD v27; // [rsp+C0h] [rbp-40h] BYREF
  SC_HANDLE hService; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-30h] BYREF
  SC_HANDLE v30; // [rsp+D8h] [rbp-28h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+E0h] [rbp-20h] BYREF
  struct _SERVICE_STATUS v32; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *a1 = 0;
  if ( (unsigned int)_InterlockedIncrement(&dword_1802457C8) <= 1 )
  {
    TickCount64 = GetTickCount64();
    do
    {
      v3 = FWOpenPolicyStore(545, 0, 2, 2);
      if ( !v3 )
        return 0;
      Sleep(0x64u);
    }
    while ( GetTickCount64() - TickCount64 < 0x7530 );
    v4 = 0;
    LastError = 0;
    memset(&v32, 0, sizeof(v32));
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    v6 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
    v7 = v6;
    v30 = v6;
    if ( v6 )
    {
      v8 = 0;
      v9 = OpenServiceW(v6, L"mpssvc", 0x80000000);
      hService = v9;
      if ( !v9 || !QueryServiceStatus(v9, &ServiceStatus) )
        LastError = GetLastError();
      v10 = OpenServiceW(v7, L"bfe", 0x80000000);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
        &hService,
        v10);
      if ( !hService || !QueryServiceStatus(hService, &v32) )
        v4 = GetLastError();
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hService);
    }
    else
    {
      v8 = GetLastError();
    }
    if ( v3 > 0 )
      v12 = (unsigned __int16)v3 | 0x80070000;
    else
      v12 = (unsigned int)v3;
    v13 = (unsigned __int16)v3 | 0x80070000;
    v14 = (int)retaddr;
    if ( (v12 & 0x80000000) != 0LL )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewallrules\\firewallruleshelper.cpp",
        (const char *)v12,
        0);
    if ( byte_180245604 < 0 )
      McTemplateU0ddddqddqdd_EventWriteTransfer(
        v14,
        v11,
        v3,
        v8,
        v4,
        LastError,
        v32.dwCurrentState,
        v32.dwWin32ExitCode,
        v32.dwServiceSpecificExitCode,
        ServiceStatus.dwCurrentState,
        ServiceStatus.dwWin32ExitCode,
        ServiceStatus.dwServiceSpecificExitCode);
    v15 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      v15 = v3;
    dwServiceSpecificExitCode = ServiceStatus.dwServiceSpecificExitCode;
    dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
    dwCurrentState = ServiceStatus.dwCurrentState;
    v22 = v32.dwServiceSpecificExitCode;
    v23 = v32.dwWin32ExitCode;
    v24 = v32.dwCurrentState;
    v25 = LastError;
    v26 = v4;
    v27 = v8;
    LODWORD(hService) = v3;
    SetAppXErrorFromLogMessage(
      v15,
      &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
      &TrustFirewallOpenHandleError,
      0xAu,
      &hService,
      &v27,
      &v26,
      &v25,
      &v24,
      &v23,
      &v22,
      &dwCurrentState,
      &dwWin32ExitCode,
      &dwServiceSpecificExitCode);
    v16 = AppXDEHTelemetry::Provider();
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL, v16) )
    {
      v29 = 0x1000000;
      LODWORD(hService) = ServiceStatus.dwServiceSpecificExitCode;
      v27 = ServiceStatus.dwWin32ExitCode;
      v26 = ServiceStatus.dwCurrentState;
      v25 = v32.dwServiceSpecificExitCode;
      v24 = v32.dwWin32ExitCode;
      v23 = v32.dwCurrentState;
      v22 = LastError;
      dwCurrentState = v4;
      dwWin32ExitCode = v8;
      dwServiceSpecificExitCode = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v17,
        (unsigned int)byte_18021CAA1,
        v17,
        v18,
        (__int64)&dwServiceSpecificExitCode,
        (__int64)&dwWin32ExitCode,
        (__int64)&dwCurrentState,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v27,
        (__int64)&hService,
        (__int64)&v29);
    }
    if ( v3 <= 0 )
      v13 = v3;
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v30);
    return v13;
  }
  else
  {
    result = FWOpenPolicyStore(545, 0, 2, 2);
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800e4268  push    rbp
0x1800e426a  push    rbx
0x1800e426b  push    rsi
0x1800e426c  push    rdi
0x1800e426d  push    r14
0x1800e426f  push    r15
0x1800e4271  lea     rbp, [rsp-38h]
0x1800e4276  sub     rsp, 138h
0x1800e427d  mov     rax, cs:__security_cookie
0x1800e4284  xor     rax, rsp
0x1800e4287  mov     [rbp+60h+var_40], rax
0x1800e428b  mov     rsi, rcx
0x1800e428e  mov     qword ptr [rcx], 0
0x1800e4295  mov     eax, 1
0x1800e429a  lock xadd cs:dword_1802457C8, eax
0x1800e42a2  inc     eax
0x1800e42a4  cmp     eax, 1
0x1800e42a7  jbe     short loc_1800E42E9
0x1800e42a9  mov     ecx, 221h
0x1800e42ae  mov     [rsp+160h+var_138], rsi
0x1800e42b3  mov     [rsp+160h+var_140], 0
0x1800e42bb  mov     ebx, 2
0x1800e42c0  mov     r9d, ebx
0x1800e42c3  mov     r8d, ebx
0x1800e42c6  xor     edx, edx
0x1800e42c8  call    cs:__imp_FWOpenPolicyStore
0x1800e42cf  nop     dword ptr [rax+rax+00h]
0x1800e42d4  test    eax, eax
0x1800e42d6  jle     loc_1800E466B
0x1800e42dc  movzx   eax, ax
0x1800e42df  or      eax, 80070000h
0x1800e42e4  jmp     loc_1800E466B
0x1800e42e9  call    cs:__imp_GetTickCount64
0x1800e42f0  nop     dword ptr [rax+rax+00h]
0x1800e42f5  mov     r14, rax
0x1800e42f8  mov     ebx, 2
0x1800e42fd  mov     ecx, 221h
0x1800e4302  mov     [rsp+160h+var_138], rsi
0x1800e4307  mov     [rsp+160h+var_140], 0; int
0x1800e430f  mov     r9d, ebx
0x1800e4312  mov     r8d, ebx
0x1800e4315  xor     edx, edx
0x1800e4317  call    cs:__imp_FWOpenPolicyStore
0x1800e431e  nop     dword ptr [rax+rax+00h]
0x1800e4323  mov     edi, eax
0x1800e4325  test    eax, eax
0x1800e4327  jz      loc_1800E4669
0x1800e432d  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800e4332  call    cs:__imp_Sleep
0x1800e4339  nop     dword ptr [rax+rax+00h]
0x1800e433e  call    cs:__imp_GetTickCount64
0x1800e4345  nop     dword ptr [rax+rax+00h]
0x1800e434a  sub     rax, r14
0x1800e434d  cmp     rax, 7530h
0x1800e4353  jb      short loc_1800E42FD
0x1800e4355  xor     esi, esi
0x1800e4357  xor     r14d, r14d
0x1800e435a  xorps   xmm0, xmm0
0x1800e435d  xor     eax, eax
0x1800e435f  movups  xmmword ptr [rbp+60h+var_60.dwServiceType], xmm0
0x1800e4363  movups  xmmword ptr [rbp+60h+var_60.dwWin32ExitCode], xmm0
0x1800e4367  xorps   xmm1, xmm1
0x1800e436a  movups  xmmword ptr [rbp+60h+ServiceStatus.dwServiceType], xmm1
0x1800e436e  movups  xmmword ptr [rbp+60h+ServiceStatus.dwWin32ExitCode], xmm1
0x1800e4372  mov     r8d, 80000000h; dwDesiredAccess
0x1800e4378  lea     rdx, DatabaseName; "ServicesActive"
0x1800e437f  xor     ecx, ecx; lpMachineName
0x1800e4381  call    cs:__imp_OpenSCManagerW
0x1800e4388  nop     dword ptr [rax+rax+00h]
0x1800e438d  mov     rbx, rax
0x1800e4390  mov     [rbp+60h+var_88], rax
0x1800e4394  test    rax, rax
0x1800e4397  jz      loc_1800E4449
0x1800e439d  xor     r15d, r15d
0x1800e43a0  mov     r8d, 80000000h; dwDesiredAccess
0x1800e43a6  lea     rdx, ServiceName; "mpssvc"
0x1800e43ad  mov     rcx, rax; hSCManager
0x1800e43b0  call    cs:__imp_OpenServiceW
0x1800e43b7  nop     dword ptr [rax+rax+00h]
0x1800e43bc  mov     [rbp+60h+hService], rax
0x1800e43c0  test    rax, rax
0x1800e43c3  jz      short loc_1800E43DC
0x1800e43c5  lea     rdx, [rbp+60h+ServiceStatus]; lpServiceStatus
0x1800e43c9  mov     rcx, rax; hService
0x1800e43cc  call    cs:__imp_QueryServiceStatus
0x1800e43d3  nop     dword ptr [rax+rax+00h]
0x1800e43d8  test    eax, eax
0x1800e43da  jnz     short loc_1800E43EB
0x1800e43dc  call    cs:__imp_GetLastError
0x1800e43e3  nop     dword ptr [rax+rax+00h]
0x1800e43e8  mov     r14d, eax
0x1800e43eb  mov     r8d, 80000000h; dwDesiredAccess
0x1800e43f1  lea     rdx, aBfe; "bfe"
0x1800e43f8  mov     rcx, rbx; hSCManager
0x1800e43fb  call    cs:__imp_OpenServiceW
0x1800e4402  nop     dword ptr [rax+rax+00h]
0x1800e4407  mov     rdx, rax
0x1800e440a  lea     rcx, [rbp+60h+hService]
0x1800e440e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800e4413  mov     rcx, [rbp+60h+hService]; hService
0x1800e4417  test    rcx, rcx
0x1800e441a  jz      short loc_1800E4430
0x1800e441c  lea     rdx, [rbp+60h+var_60]; lpServiceStatus
0x1800e4420  call    cs:__imp_QueryServiceStatus
0x1800e4427  nop     dword ptr [rax+rax+00h]
0x1800e442c  test    eax, eax
0x1800e442e  jnz     short loc_1800E443E
0x1800e4430  call    cs:__imp_GetLastError
0x1800e4437  nop     dword ptr [rax+rax+00h]
0x1800e443c  mov     esi, eax
0x1800e443e  lea     rcx, [rbp+60h+hService]
0x1800e4442  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e4447  jmp     short loc_1800E4458
0x1800e4449  call    cs:__imp_GetLastError
0x1800e4450  nop     dword ptr [rax+rax+00h]
0x1800e4455  mov     r15d, eax
0x1800e4458  movzx   ebx, di
0x1800e445b  mov     ecx, 80070000h
0x1800e4460  test    edi, edi
0x1800e4462  jg      short loc_1800E4469
0x1800e4464  mov     r9d, edi
0x1800e4467  jmp     short loc_1800E446F
0x1800e4469  mov     r9d, ebx
0x1800e446c  or      r9d, ecx; char *
0x1800e446f  or      ebx, ecx
0x1800e4471  mov     rcx, [rbp+68h]; this
0x1800e4475  test    r9d, r9d
0x1800e4478  jns     short loc_1800E448B
0x1800e447a  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e4481  mov     edx, 259h; void *
0x1800e4486  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e448b  cmp     cs:byte_180245604, 0
0x1800e4492  jge     short loc_1800E44D2
0x1800e4494  mov     eax, [rbp+60h+ServiceStatus.dwServiceSpecificExitCode]
0x1800e4497  mov     dword ptr [rsp+160h+var_108], eax
0x1800e449b  mov     eax, [rbp+60h+ServiceStatus.dwWin32ExitCode]
0x1800e449e  mov     dword ptr [rsp+160h+var_110], eax
0x1800e44a2  mov     eax, [rbp+60h+ServiceStatus.dwCurrentState]
0x1800e44a5  mov     dword ptr [rsp+160h+var_118], eax
0x1800e44a9  mov     eax, [rbp+60h+var_60.dwServiceSpecificExitCode]
0x1800e44ac  mov     dword ptr [rsp+160h+var_120], eax
0x1800e44b0  mov     eax, [rbp+60h+var_60.dwWin32ExitCode]
0x1800e44b3  mov     dword ptr [rsp+160h+var_128], eax
0x1800e44b7  mov     eax, [rbp+60h+var_60.dwCurrentState]
0x1800e44ba  mov     dword ptr [rsp+160h+var_130], eax
0x1800e44be  mov     dword ptr [rsp+160h+var_138], r14d
0x1800e44c3  mov     [rsp+160h+var_140], esi
0x1800e44c7  mov     r9d, r15d
0x1800e44ca  mov     r8d, edi
0x1800e44cd  call    McTemplateU0ddddqddqdd_EventWriteTransfer
0x1800e44d2  mov     ecx, ebx
0x1800e44d4  test    edi, edi
0x1800e44d6  cmovle  ecx, edi; int
0x1800e44d9  mov     eax, [rbp+60h+ServiceStatus.dwServiceSpecificExitCode]
0x1800e44dc  mov     [rbp+60h+var_E0], eax
0x1800e44df  mov     eax, [rbp+60h+ServiceStatus.dwWin32ExitCode]
0x1800e44e2  mov     [rbp+60h+var_D8], eax
0x1800e44e5  mov     eax, [rbp+60h+ServiceStatus.dwCurrentState]
0x1800e44e8  mov     [rbp+60h+var_D0], eax
0x1800e44eb  mov     eax, [rbp+60h+var_60.dwServiceSpecificExitCode]
0x1800e44ee  mov     [rbp+60h+var_C8], eax
0x1800e44f1  mov     eax, [rbp+60h+var_60.dwWin32ExitCode]
0x1800e44f4  mov     [rbp+60h+var_C0], eax
0x1800e44f7  mov     eax, [rbp+60h+var_60.dwCurrentState]
0x1800e44fa  mov     [rbp+60h+var_B8], eax
0x1800e44fd  mov     [rbp+60h+var_B0], r14d
0x1800e4501  mov     [rbp+60h+var_A8], esi
0x1800e4504  mov     [rbp+60h+var_A0], r15d
0x1800e4508  mov     dword ptr [rbp+60h+hService], edi
0x1800e450b  lea     rax, [rbp+60h+var_E0]
0x1800e450f  mov     [rsp+160h+var_F8], rax
0x1800e4514  lea     rax, [rbp+60h+var_D8]
0x1800e4518  mov     [rsp+160h+var_100], rax
0x1800e451d  lea     rax, [rbp+60h+var_D0]
0x1800e4521  mov     [rsp+160h+var_108], rax
0x1800e4526  lea     rax, [rbp+60h+var_C8]
0x1800e452a  mov     [rsp+160h+var_110], rax
0x1800e452f  lea     rax, [rbp+60h+var_C0]
0x1800e4533  mov     [rsp+160h+var_118], rax
0x1800e4538  lea     rax, [rbp+60h+var_B8]
0x1800e453c  mov     [rsp+160h+var_120], rax
0x1800e4541  lea     rax, [rbp+60h+var_B0]
0x1800e4545  mov     [rsp+160h+var_128], rax
0x1800e454a  lea     rax, [rbp+60h+var_A8]
0x1800e454e  mov     [rsp+160h+var_130], rax
0x1800e4553  lea     rax, [rbp+60h+var_A0]
0x1800e4557  mov     [rsp+160h+var_138], rax
0x1800e455c  lea     rax, [rbp+60h+hService]
0x1800e4560  mov     qword ptr [rsp+160h+var_140], rax
0x1800e4565  mov     r9d, 0Ah; unsigned int
0x1800e456b  lea     r8, TrustFirewallOpenHandleError; struct _EVENT_DESCRIPTOR *
0x1800e4572  lea     rdx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID; struct _GUID *
0x1800e4579  call    ?SetAppXErrorFromLogMessage@@YAJJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@KZZ; SetAppXErrorFromLogMessage(long,_GUID const &,_EVENT_DESCRIPTOR const &,ulong,...)
0x1800e457e  call    ?Provider@AppXDEHTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDEHTelemetry::Provider(void)
0x1800e4583  mov     r8, rax
0x1800e4586  mov     ecx, [rax]
0x1800e4588  cmp     ecx, 5
0x1800e458b  jbe     loc_1800E4657
0x1800e4591  mov     rdx, 400000000000h
0x1800e459b  mov     rcx, rax
0x1800e459e  call    _tlgKeywordOn
0x1800e45a3  test    al, al
0x1800e45a5  jz      loc_1800E4657
0x1800e45ab  mov     [rbp+60h+var_90], 1000000h
0x1800e45b3  mov     ecx, [rbp+60h+ServiceStatus.dwServiceSpecificExitCode]
0x1800e45b6  mov     dword ptr [rbp+60h+hService], ecx
0x1800e45b9  mov     eax, [rbp+60h+ServiceStatus.dwWin32ExitCode]
0x1800e45bc  mov     [rbp+60h+var_A0], eax
0x1800e45bf  mov     eax, [rbp+60h+ServiceStatus.dwCurrentState]
0x1800e45c2  mov     [rbp+60h+var_A8], eax
0x1800e45c5  mov     eax, [rbp+60h+var_60.dwServiceSpecificExitCode]
0x1800e45c8  mov     [rbp+60h+var_B0], eax
0x1800e45cb  mov     eax, [rbp+60h+var_60.dwWin32ExitCode]
0x1800e45ce  mov     [rbp+60h+var_B8], eax
0x1800e45d1  mov     eax, [rbp+60h+var_60.dwCurrentState]
0x1800e45d4  mov     [rbp+60h+var_C0], eax
0x1800e45d7  mov     [rbp+60h+var_C8], r14d
0x1800e45db  mov     [rbp+60h+var_D0], esi
0x1800e45de  mov     [rbp+60h+var_D8], r15d
0x1800e45e2  mov     [rbp+60h+var_E0], edi
0x1800e45e5  lea     rax, [rbp+60h+var_90]
0x1800e45e9  mov     [rsp+160h+var_F0], rax
0x1800e45ee  lea     rax, [rbp+60h+hService]
0x1800e45f2  mov     [rsp+160h+var_F8], rax
0x1800e45f7  lea     rax, [rbp+60h+var_A0]
0x1800e45fb  mov     [rsp+160h+var_100], rax
0x1800e4600  lea     rax, [rbp+60h+var_A8]
0x1800e4604  mov     [rsp+160h+var_108], rax
0x1800e4609  lea     rax, [rbp+60h+var_B0]
0x1800e460d  mov     [rsp+160h+var_110], rax
0x1800e4612  lea     rax, [rbp+60h+var_B8]
0x1800e4616  mov     [rsp+160h+var_118], rax
0x1800e461b  lea     rax, [rbp+60h+var_C0]
0x1800e461f  mov     [rsp+160h+var_120], rax
0x1800e4624  lea     rax, [rbp+60h+var_C8]
0x1800e4628  mov     [rsp+160h+var_128], rax
0x1800e462d  lea     rax, [rbp+60h+var_D0]
0x1800e4631  mov     [rsp+160h+var_130], rax
0x1800e4636  lea     rax, [rbp+60h+var_D8]
0x1800e463a  mov     [rsp+160h+var_138], rax
0x1800e463f  lea     rax, [rbp+60h+var_E0]
0x1800e4643  mov     qword ptr [rsp+160h+var_140], rax
0x1800e4648  lea     rdx, byte_18021CAA1
0x1800e464f  mov     rcx, r8
0x1800e4652  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800e4657  test    edi, edi
0x1800e4659  cmovle  ebx, edi
0x1800e465c  lea     rcx, [rbp+60h+var_88]
0x1800e4660  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e4665  mov     eax, ebx
0x1800e4667  jmp     short loc_1800E466B
0x1800e4669  xor     eax, eax
0x1800e466b  mov     rcx, [rbp+60h+var_40]
0x1800e466f  xor     rcx, rsp; StackCookie
0x1800e4672  call    __security_check_cookie
0x1800e4677  add     rsp, 138h
0x1800e467e  pop     r15
0x1800e4680  pop     r14
0x1800e4682  pop     rdi
0x1800e4683  pop     rsi
0x1800e4684  pop     rbx
0x1800e4685  pop     rbp
0x1800e4686  retn
```
