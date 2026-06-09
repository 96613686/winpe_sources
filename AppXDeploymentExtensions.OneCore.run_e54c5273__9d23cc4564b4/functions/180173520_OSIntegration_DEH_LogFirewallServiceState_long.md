# OSIntegration::DEH::LogFirewallServiceState(long)

- ea: `0x180173520`
- end: `0x180173850`
- name: `?LogFirewallServiceState@DEH@OSIntegration@@YAXJ@Z`
- size: `816`
- prototype: `void __fastcall(OSIntegration::DEH *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180173e34`

## callees

- `0x180003078`
- `0x18001b84c`
- `0x18007689c`
- `0x180076900`
- `0x1800a219c`
- `0x1800c5988`
- `0x1800f0260`
- `0x180172684`
- `0x180173520`
- `0x180173fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801735c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801735c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173633`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801735a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801735dc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801735a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801735dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801735f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801735f6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18017357b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18017357b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801735b9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180173615`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801735b9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180173615`

## string_xrefs

- `0x180173572`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OSIntegration::DEH::LogFirewallServiceState(OSIntegration::DEH *this)
{
  int v1; // esi
  DWORD v2; // r14d
  DWORD LastError; // r15d
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  DWORD v6; // r12d
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbx
  SC_HANDLE v9; // rdi
  int v10; // edx
  unsigned __int64 v11; // r9
  int v12; // ecx
  unsigned int v13; // ebx
  const struct _tlgProvider_t *v14; // r8
  int v15; // r9d
  int v16; // [rsp+20h] [rbp-E0h]
  DWORD dwServiceSpecificExitCode; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwWin32ExitCode; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwCurrentState; // [rsp+80h] [rbp-80h] BYREF
  DWORD v20; // [rsp+88h] [rbp-78h] BYREF
  DWORD v21; // [rsp+90h] [rbp-70h] BYREF
  DWORD v22; // [rsp+98h] [rbp-68h] BYREF
  DWORD v23; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v24; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v25; // [rsp+B0h] [rbp-50h] BYREF
  SC_HANDLE v26; // [rsp+B8h] [rbp-48h] BYREF
  SC_HANDLE v27; // [rsp+C0h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+C8h] [rbp-38h] BYREF
  struct _SERVICE_STATUS v29; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v1 = (int)this;
  v2 = 0;
  LastError = 0;
  memset(&v29, 0, sizeof(v29));
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v5 = v4;
  v27 = v4;
  if ( v4 )
  {
    v6 = 0;
    v7 = OpenServiceW(v4, L"mpssvc", 0x80000000);
    v8 = v7;
    if ( !v7 || !QueryServiceStatus(v7, &ServiceStatus) )
      LastError = GetLastError();
    v9 = OpenServiceW(v5, L"bfe", 0x80000000);
    if ( v8 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
      CloseServiceHandle(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
    }
    v26 = v9;
    if ( !v9 || !QueryServiceStatus(v9, &v29) )
      v2 = GetLastError();
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
  }
  else
  {
    v6 = GetLastError();
  }
  if ( v1 > 0 )
    v11 = (unsigned __int16)v1 | 0x80070000;
  else
    v11 = (unsigned int)v1;
  v12 = (int)retaddr;
  if ( (v11 & 0x80000000) != 0LL )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
      (const char *)v11,
      v16);
  if ( byte_1802E21C4 < 0 )
    McTemplateU0ddddqddqdd_EventWriteTransfer(
      v12,
      v10,
      v1,
      v6,
      v2,
      LastError,
      v29.dwCurrentState,
      v29.dwWin32ExitCode,
      v29.dwServiceSpecificExitCode,
      ServiceStatus.dwCurrentState,
      ServiceStatus.dwWin32ExitCode,
      ServiceStatus.dwServiceSpecificExitCode);
  if ( v1 > 0 )
    v13 = (unsigned __int16)v1 | 0x80070000;
  else
    v13 = v1;
  dwServiceSpecificExitCode = ServiceStatus.dwServiceSpecificExitCode;
  dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
  dwCurrentState = ServiceStatus.dwCurrentState;
  v20 = v29.dwServiceSpecificExitCode;
  v21 = v29.dwWin32ExitCode;
  v22 = v29.dwCurrentState;
  v23 = LastError;
  v24 = v2;
  v25 = v6;
  LODWORD(v26) = v1;
  SetAppXErrorFromLogMessage(
    v13,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
    &TrustFirewallOpenHandleError,
    0xAu,
    &v26,
    &v25,
    &v24,
    &v23,
    &v22,
    &v21,
    &v20,
    &dwCurrentState,
    &dwWin32ExitCode,
    &dwServiceSpecificExitCode);
  v14 = AppXDEHTelemetry::Provider();
  if ( *(_DWORD *)v14 > 5u )
  {
    LODWORD(v26) = ServiceStatus.dwServiceSpecificExitCode;
    v25 = ServiceStatus.dwWin32ExitCode;
    v24 = ServiceStatus.dwCurrentState;
    v23 = v29.dwServiceSpecificExitCode;
    v22 = v29.dwWin32ExitCode;
    v21 = v29.dwCurrentState;
    v20 = LastError;
    dwCurrentState = v2;
    dwWin32ExitCode = v6;
    dwServiceSpecificExitCode = v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v14,
      (unsigned int)byte_1802B43C9,
      (_DWORD)v14,
      v15,
      (__int64)&dwServiceSpecificExitCode,
      (__int64)&dwWin32ExitCode,
      (__int64)&dwCurrentState,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v26);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v27);
}

```

## disassembly

```asm
0x180173520  mov     [rsp-8+arg_8], rbx
0x180173525  mov     [rsp-8+arg_10], rsi
0x18017352a  push    rbp
0x18017352b  push    rdi
0x18017352c  push    r12
0x18017352e  push    r14
0x180173530  push    r15
0x180173532  lea     rbp, [rsp-10h]
0x180173537  sub     rsp, 110h
0x18017353e  mov     rax, cs:__security_cookie
0x180173545  xor     rax, rsp
0x180173548  mov     [rbp+30h+var_28], rax
0x18017354c  mov     esi, ecx
0x18017354e  xor     r14d, r14d
0x180173551  xor     r15d, r15d
0x180173554  xorps   xmm0, xmm0
0x180173557  xor     eax, eax
0x180173559  movups  xmmword ptr [rbp+30h+var_48.dwServiceType], xmm0
0x18017355d  movups  xmmword ptr [rbp+30h+var_48.dwWin32ExitCode], xmm0
0x180173561  xorps   xmm1, xmm1
0x180173564  movups  xmmword ptr [rbp+30h+ServiceStatus.dwServiceType], xmm1
0x180173568  movups  xmmword ptr [rbp+30h+ServiceStatus.dwWin32ExitCode], xmm1
0x18017356c  mov     r8d, 80000000h; dwDesiredAccess
0x180173572  lea     rdx, DatabaseName; "ServicesActive"
0x180173579  xor     ecx, ecx; lpMachineName
0x18017357b  call    cs:__imp_OpenSCManagerW
0x180173581  mov     rdi, rax
0x180173584  mov     [rbp+30h+var_70], rax
0x180173588  test    rax, rax
0x18017358b  jz      loc_180173633
0x180173591  xor     r12d, r12d
0x180173594  mov     r8d, 80000000h; dwDesiredAccess
0x18017359a  lea     rdx, ServiceName; "mpssvc"
0x1801735a1  mov     rcx, rax; hSCManager
0x1801735a4  call    cs:__imp_OpenServiceW
0x1801735aa  mov     rbx, rax
0x1801735ad  test    rax, rax
0x1801735b0  jz      short loc_1801735C3
0x1801735b2  lea     rdx, [rbp+30h+ServiceStatus]; lpServiceStatus
0x1801735b6  mov     rcx, rax; hService
0x1801735b9  call    cs:__imp_QueryServiceStatus
0x1801735bf  test    eax, eax
0x1801735c1  jnz     short loc_1801735CC
0x1801735c3  call    cs:__imp_GetLastError
0x1801735c9  mov     r15d, eax
0x1801735cc  mov     r8d, 80000000h; dwDesiredAccess
0x1801735d2  lea     rdx, aBfe; "bfe"
0x1801735d9  mov     rcx, rdi; hSCManager
0x1801735dc  call    cs:__imp_OpenServiceW
0x1801735e2  mov     rdi, rax
0x1801735e5  test    rbx, rbx
0x1801735e8  jz      short loc_180173605
0x1801735ea  lea     rcx, [rbp+30h+var_78]; this
0x1801735ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801735f3  mov     rcx, rbx; hSCObject
0x1801735f6  call    cs:__imp_CloseServiceHandle
0x1801735fc  lea     rcx, [rbp+30h+var_78]; this
0x180173600  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180173605  mov     [rbp+30h+var_78], rdi
0x180173609  test    rdi, rdi
0x18017360c  jz      short loc_18017361F
0x18017360e  lea     rdx, [rbp+30h+var_48]; lpServiceStatus
0x180173612  mov     rcx, rdi; hService
0x180173615  call    cs:__imp_QueryServiceStatus
0x18017361b  test    eax, eax
0x18017361d  jnz     short loc_180173628
0x18017361f  call    cs:__imp_GetLastError
0x180173625  mov     r14d, eax
0x180173628  lea     rcx, [rbp+30h+var_78]
0x18017362c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180173631  jmp     short loc_18017363C
0x180173633  call    cs:__imp_GetLastError
0x180173639  mov     r12d, eax
0x18017363c  movzx   ebx, si
0x18017363f  mov     edi, 80070000h
0x180173644  test    esi, esi
0x180173646  jg      short loc_18017364D
0x180173648  mov     r9d, esi
0x18017364b  jmp     short loc_180173653
0x18017364d  mov     r9d, ebx
0x180173650  or      r9d, edi; char *
0x180173653  mov     rcx, [rbp+38h]; this
0x180173657  test    r9d, r9d
0x18017365a  jns     short loc_18017366D
0x18017365c  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180173663  mov     edx, 96h; void *
0x180173668  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017366d  cmp     cs:byte_1802E21C4, 0
0x180173674  jge     short loc_1801736B5
0x180173676  mov     eax, [rbp+30h+ServiceStatus.dwServiceSpecificExitCode]
0x180173679  mov     dword ptr [rsp+130h+var_D8], eax
0x18017367d  mov     eax, [rbp+30h+ServiceStatus.dwWin32ExitCode]
0x180173680  mov     dword ptr [rsp+130h+var_E0], eax
0x180173684  mov     eax, [rbp+30h+ServiceStatus.dwCurrentState]
0x180173687  mov     dword ptr [rsp+130h+var_E8], eax
0x18017368b  mov     eax, [rbp+30h+var_48.dwServiceSpecificExitCode]
0x18017368e  mov     dword ptr [rsp+130h+var_F0], eax
0x180173692  mov     eax, [rbp+30h+var_48.dwWin32ExitCode]
0x180173695  mov     dword ptr [rsp+130h+var_F8], eax
0x180173699  mov     eax, [rbp+30h+var_48.dwCurrentState]
0x18017369c  mov     dword ptr [rsp+130h+var_100], eax
0x1801736a0  mov     dword ptr [rsp+130h+var_108], r15d
0x1801736a5  mov     dword ptr [rsp+130h+var_110], r14d
0x1801736aa  mov     r9d, r12d
0x1801736ad  mov     r8d, esi
0x1801736b0  call    McTemplateU0ddddqddqdd_EventWriteTransfer
0x1801736b5  test    esi, esi
0x1801736b7  jg      short loc_1801736BD
0x1801736b9  mov     ebx, esi
0x1801736bb  jmp     short loc_1801736BF
0x1801736bd  or      ebx, edi
0x1801736bf  mov     eax, [rbp+30h+ServiceStatus.dwServiceSpecificExitCode]
0x1801736c2  mov     [rsp+130h+var_C0], eax
0x1801736c6  mov     eax, [rbp+30h+ServiceStatus.dwWin32ExitCode]
0x1801736c9  mov     [rsp+130h+var_B8], eax
0x1801736cd  mov     eax, [rbp+30h+ServiceStatus.dwCurrentState]
0x1801736d0  mov     [rbp+30h+var_B0], eax
0x1801736d3  mov     eax, [rbp+30h+var_48.dwServiceSpecificExitCode]
0x1801736d6  mov     [rbp+30h+var_A8], eax
0x1801736d9  mov     eax, [rbp+30h+var_48.dwWin32ExitCode]
0x1801736dc  mov     [rbp+30h+var_A0], eax
0x1801736df  mov     eax, [rbp+30h+var_48.dwCurrentState]
0x1801736e2  mov     [rbp+30h+var_98], eax
0x1801736e5  mov     [rbp+30h+var_90], r15d
0x1801736e9  mov     [rbp+30h+var_88], r14d
0x1801736ed  mov     [rbp+30h+var_80], r12d
0x1801736f1  mov     dword ptr [rbp+30h+var_78], esi
0x1801736f4  lea     rax, [rsp+130h+var_C0]
0x1801736f9  mov     [rsp+130h+var_C8], rax
0x1801736fe  lea     rax, [rsp+130h+var_B8]
0x180173703  mov     [rsp+130h+var_D0], rax
0x180173708  lea     rax, [rbp+30h+var_B0]
0x18017370c  mov     [rsp+130h+var_D8], rax
0x180173711  lea     rax, [rbp+30h+var_A8]
0x180173715  mov     [rsp+130h+var_E0], rax
0x18017371a  lea     rax, [rbp+30h+var_A0]
0x18017371e  mov     [rsp+130h+var_E8], rax
0x180173723  lea     rax, [rbp+30h+var_98]
0x180173727  mov     [rsp+130h+var_F0], rax
0x18017372c  lea     rax, [rbp+30h+var_90]
0x180173730  mov     [rsp+130h+var_F8], rax
0x180173735  lea     rax, [rbp+30h+var_88]
0x180173739  mov     [rsp+130h+var_100], rax
0x18017373e  lea     rax, [rbp+30h+var_80]
0x180173742  mov     [rsp+130h+var_108], rax
0x180173747  lea     rax, [rbp+30h+var_78]
0x18017374b  mov     [rsp+130h+var_110], rax
0x180173750  mov     r9d, 0Ah; unsigned int
0x180173756  lea     r8, TrustFirewallOpenHandleError; struct _EVENT_DESCRIPTOR *
0x18017375d  lea     rdx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID; struct _GUID *
0x180173764  mov     ecx, ebx; int
0x180173766  call    ?SetAppXErrorFromLogMessage@@YAJJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@KZZ; SetAppXErrorFromLogMessage(long,_GUID const &,_EVENT_DESCRIPTOR const &,ulong,...)
0x18017376b  call    ?Provider@AppXDEHTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDEHTelemetry::Provider(void)
0x180173770  mov     r8, rax
0x180173773  mov     ecx, [rax]
0x180173775  cmp     ecx, 5
0x180173778  jbe     loc_18017381F
0x18017377e  mov     ecx, [rbp+30h+ServiceStatus.dwServiceSpecificExitCode]
0x180173781  mov     dword ptr [rbp+30h+var_78], ecx
0x180173784  mov     ecx, [rbp+30h+ServiceStatus.dwWin32ExitCode]
0x180173787  mov     [rbp+30h+var_80], ecx
0x18017378a  mov     ecx, [rbp+30h+ServiceStatus.dwCurrentState]
0x18017378d  mov     [rbp+30h+var_88], ecx
0x180173790  mov     ecx, [rbp+30h+var_48.dwServiceSpecificExitCode]
0x180173793  mov     [rbp+30h+var_90], ecx
0x180173796  mov     ecx, [rbp+30h+var_48.dwWin32ExitCode]
0x180173799  mov     [rbp+30h+var_98], ecx
0x18017379c  mov     eax, [rbp+30h+var_48.dwCurrentState]
0x18017379f  mov     [rbp+30h+var_A0], eax
0x1801737a2  mov     [rbp+30h+var_A8], r15d
0x1801737a6  mov     [rbp+30h+var_B0], r14d
0x1801737aa  mov     [rsp+130h+var_B8], r12d
0x1801737af  mov     [rsp+130h+var_C0], esi
0x1801737b3  lea     rax, [rbp+30h+var_78]
0x1801737b7  mov     [rsp+130h+var_C8], rax
0x1801737bc  lea     rax, [rbp+30h+var_80]
0x1801737c0  mov     [rsp+130h+var_D0], rax
0x1801737c5  lea     rax, [rbp+30h+var_88]
0x1801737c9  mov     [rsp+130h+var_D8], rax
0x1801737ce  lea     rax, [rbp+30h+var_90]
0x1801737d2  mov     [rsp+130h+var_E0], rax
0x1801737d7  lea     rax, [rbp+30h+var_98]
0x1801737db  mov     [rsp+130h+var_E8], rax
0x1801737e0  lea     rax, [rbp+30h+var_A0]
0x1801737e4  mov     [rsp+130h+var_F0], rax
0x1801737e9  lea     rax, [rbp+30h+var_A8]
0x1801737ed  mov     [rsp+130h+var_F8], rax
0x1801737f2  lea     rax, [rbp+30h+var_B0]
0x1801737f6  mov     [rsp+130h+var_100], rax
0x1801737fb  lea     rax, [rsp+130h+var_B8]
0x180173800  mov     [rsp+130h+var_108], rax
0x180173805  lea     rax, [rsp+130h+var_C0]
0x18017380a  mov     [rsp+130h+var_110], rax
0x18017380f  lea     rdx, byte_1802B43C9
0x180173816  mov     rcx, r8
0x180173819  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18017381e  nop
0x18017381f  lea     rcx, [rbp+30h+var_70]
0x180173823  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180173828  mov     rcx, [rbp+30h+var_28]
0x18017382c  xor     rcx, rsp; StackCookie
0x18017382f  call    __security_check_cookie
0x180173834  lea     r11, [rsp+130h+var_20]
0x18017383c  mov     rbx, [r11+38h]
0x180173840  mov     rsi, [r11+40h]
0x180173844  mov     rsp, r11
0x180173847  pop     r15
0x180173849  pop     r14
0x18017384b  pop     r12
0x18017384d  pop     rdi
0x18017384e  pop     rbp
0x18017384f  retn
```
