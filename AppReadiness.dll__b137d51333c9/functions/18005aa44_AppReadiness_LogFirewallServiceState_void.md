# AppReadiness::LogFirewallServiceState(void)

- ea: `0x18005aa44`
- end: `0x18005ac64`
- name: `?LogFirewallServiceState@AppReadiness@@YAXXZ`
- size: `544`
- prototype: `void __fastcall(AppReadiness *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025910`

## callees

- `0x180001cb4`
- `0x1800239d0`
- `0x180032e40`
- `0x18003e210`
- `0x18004bdc0`
- `0x18005aa44`
- `0x18005f0bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005aadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005aadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab4a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005aabc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005aaf4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005aabc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005aaf4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005aa93`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005aa93`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ab0e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ab0e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005aad1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005ab2d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005aad1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005ab2d`

## string_xrefs

- `0x18005aa6a`: `ServicesActive`

## pseudocode

```c
void __fastcall AppReadiness::LogFirewallServiceState(AppReadiness *this)
{
  DWORD v1; // esi
  DWORD LastError; // r14d
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  DWORD v5; // r15d
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbx
  SC_HANDLE v8; // rdi
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char v13[8]; // [rsp+70h] [rbp-59h] BYREF
  SC_HANDLE v14; // [rsp+78h] [rbp-51h] BYREF
  DWORD dwServiceSpecificExitCode; // [rsp+80h] [rbp-49h] BYREF
  DWORD dwWin32ExitCode; // [rsp+84h] [rbp-45h] BYREF
  DWORD dwCurrentState; // [rsp+88h] [rbp-41h] BYREF
  DWORD v18; // [rsp+8Ch] [rbp-3Dh] BYREF
  DWORD v19; // [rsp+90h] [rbp-39h] BYREF
  DWORD v20; // [rsp+94h] [rbp-35h] BYREF
  DWORD v21; // [rsp+98h] [rbp-31h] BYREF
  DWORD v22; // [rsp+9Ch] [rbp-2Dh] BYREF
  SC_HANDLE v23; // [rsp+A0h] [rbp-29h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+A8h] [rbp-21h] BYREF
  struct _SERVICE_STATUS v25; // [rsp+C8h] [rbp-1h] BYREF

  memset(&v25, 0, sizeof(v25));
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = 0;
  LastError = 0;
  v3 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v23 = v3;
  v4 = v3;
  if ( v3 )
  {
    v5 = 0;
    v6 = OpenServiceW(v3, L"mpssvc", 0x80000000);
    v7 = v6;
    if ( !v6 || !QueryServiceStatus(v6, &ServiceStatus) )
      LastError = GetLastError();
    v8 = OpenServiceW(v4, L"bfe", 0x80000000);
    if ( v7 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
      CloseServiceHandle(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
    }
    v14 = v8;
    if ( !v8 || !QueryServiceStatus(v8, &v25) )
      v1 = GetLastError();
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
  }
  else
  {
    v5 = GetLastError();
  }
  if ( (Microsoft_Windows_AppReadinessEnableBits & 0x200) != 0 )
    McTemplateU0tdddqddqdd_EventWriteTransfer(
      v25.dwServiceSpecificExitCode,
      v9,
      v11,
      v5,
      v1,
      LastError,
      v25.dwCurrentState,
      v25.dwWin32ExitCode,
      v25.dwServiceSpecificExitCode,
      ServiceStatus.dwCurrentState,
      ServiceStatus.dwWin32ExitCode,
      ServiceStatus.dwServiceSpecificExitCode);
  if ( (unsigned int)dword_1800A2208 > 5 )
  {
    dwServiceSpecificExitCode = ServiceStatus.dwServiceSpecificExitCode;
    dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
    dwCurrentState = ServiceStatus.dwCurrentState;
    v18 = v25.dwServiceSpecificExitCode;
    v19 = v25.dwWin32ExitCode;
    v20 = v25.dwCurrentState;
    v21 = LastError;
    v22 = v1;
    LODWORD(v14) = v5;
    v13[0] = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v10,
      (__int64)byte_180093269,
      v11,
      v12,
      (__int64)v13,
      (__int64)&v14,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&dwCurrentState,
      (__int64)&dwWin32ExitCode,
      (__int64)&dwServiceSpecificExitCode);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v23);
}

```

## disassembly

```asm
0x18005aa44  push    rbp
0x18005aa46  push    rbx
0x18005aa47  push    rsi
0x18005aa48  push    rdi
0x18005aa49  push    r14
0x18005aa4b  push    r15
0x18005aa4d  lea     rbp, [rsp-2Fh]
0x18005aa52  sub     rsp, 0F8h
0x18005aa59  mov     rax, cs:__security_cookie
0x18005aa60  xor     rax, rsp
0x18005aa63  mov     [rbp+57h+var_38], rax
0x18005aa67  xorps   xmm0, xmm0
0x18005aa6a  lea     rdx, DatabaseName; "ServicesActive"
0x18005aa71  xorps   xmm1, xmm1
0x18005aa74  xor     eax, eax
0x18005aa76  movups  xmmword ptr [rbp+57h+var_58.dwServiceType], xmm0
0x18005aa7a  mov     r8d, 80000000h; dwDesiredAccess
0x18005aa80  xor     ecx, ecx; lpMachineName
0x18005aa82  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm1
0x18005aa86  xor     esi, esi
0x18005aa88  xor     r14d, r14d
0x18005aa8b  movups  xmmword ptr [rbp+57h+var_58.dwWin32ExitCode], xmm0
0x18005aa8f  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm1
0x18005aa93  call    cs:__imp_OpenSCManagerW
0x18005aa99  mov     [rbp+57h+var_80], rax
0x18005aa9d  mov     rdi, rax
0x18005aaa0  test    rax, rax
0x18005aaa3  jz      loc_18005AB4A
0x18005aaa9  mov     r8d, 80000000h; dwDesiredAccess
0x18005aaaf  lea     rdx, ServiceName; "mpssvc"
0x18005aab6  mov     rcx, rax; hSCManager
0x18005aab9  xor     r15d, r15d
0x18005aabc  call    cs:__imp_OpenServiceW
0x18005aac2  mov     rbx, rax
0x18005aac5  test    rax, rax
0x18005aac8  jz      short loc_18005AADB
0x18005aaca  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18005aace  mov     rcx, rax; hService
0x18005aad1  call    cs:__imp_QueryServiceStatus
0x18005aad7  test    eax, eax
0x18005aad9  jnz     short loc_18005AAE4
0x18005aadb  call    cs:__imp_GetLastError
0x18005aae1  mov     r14d, eax
0x18005aae4  mov     r8d, 80000000h; dwDesiredAccess
0x18005aaea  lea     rdx, aBfe; "bfe"
0x18005aaf1  mov     rcx, rdi; hSCManager
0x18005aaf4  call    cs:__imp_OpenServiceW
0x18005aafa  mov     rdi, rax
0x18005aafd  test    rbx, rbx
0x18005ab00  jz      short loc_18005AB1D
0x18005ab02  lea     rcx, [rbp+57h+var_A8]; this
0x18005ab06  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005ab0b  mov     rcx, rbx; hSCObject
0x18005ab0e  call    cs:__imp_CloseServiceHandle
0x18005ab14  lea     rcx, [rbp+57h+var_A8]; this
0x18005ab18  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005ab1d  mov     [rbp+57h+var_A8], rdi
0x18005ab21  test    rdi, rdi
0x18005ab24  jz      short loc_18005AB37
0x18005ab26  lea     rdx, [rbp+57h+var_58]; lpServiceStatus
0x18005ab2a  mov     rcx, rdi; hService
0x18005ab2d  call    cs:__imp_QueryServiceStatus
0x18005ab33  test    eax, eax
0x18005ab35  jnz     short loc_18005AB3F
0x18005ab37  call    cs:__imp_GetLastError
0x18005ab3d  mov     esi, eax
0x18005ab3f  lea     rcx, [rbp+57h+var_A8]
0x18005ab43  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18005ab48  jmp     short loc_18005AB53
0x18005ab4a  call    cs:__imp_GetLastError
0x18005ab50  mov     r15d, eax
0x18005ab53  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 2
0x18005ab5a  jz      short loc_18005AB97
0x18005ab5c  mov     ecx, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x18005ab5f  mov     r9d, r15d
0x18005ab62  mov     eax, [rbp+57h+var_58.dwWin32ExitCode]
0x18005ab65  mov     dword ptr [rsp+120h+var_C8], ecx
0x18005ab69  mov     ecx, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18005ab6c  mov     dword ptr [rsp+120h+var_D0], ecx
0x18005ab70  mov     ecx, [rbp+57h+ServiceStatus.dwCurrentState]
0x18005ab73  mov     dword ptr [rsp+120h+var_D8], ecx
0x18005ab77  mov     ecx, [rbp+57h+var_58.dwServiceSpecificExitCode]
0x18005ab7a  mov     dword ptr [rsp+120h+var_E0], ecx
0x18005ab7e  mov     dword ptr [rsp+120h+var_E8], eax
0x18005ab82  mov     eax, [rbp+57h+var_58.dwCurrentState]
0x18005ab85  mov     dword ptr [rsp+120h+var_F0], eax
0x18005ab89  mov     dword ptr [rsp+120h+var_F8], r14d
0x18005ab8e  mov     dword ptr [rsp+120h+var_100], esi
0x18005ab92  call    McTemplateU0tdddqddqdd_EventWriteTransfer
0x18005ab97  mov     eax, cs:dword_1800A2208
0x18005ab9d  cmp     eax, 5
0x18005aba0  jbe     loc_18005AC3F
0x18005aba6  mov     eax, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x18005aba9  lea     rdx, byte_180093269
0x18005abb0  mov     [rbp+57h+var_A0], eax
0x18005abb3  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18005abb6  mov     [rbp+57h+var_9C], eax
0x18005abb9  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x18005abbc  mov     [rbp+57h+var_98], eax
0x18005abbf  mov     eax, [rbp+57h+var_58.dwServiceSpecificExitCode]
0x18005abc2  mov     [rbp+57h+var_94], eax
0x18005abc5  mov     eax, [rbp+57h+var_58.dwWin32ExitCode]
0x18005abc8  mov     [rbp+57h+var_90], eax
0x18005abcb  mov     eax, [rbp+57h+var_58.dwCurrentState]
0x18005abce  mov     [rbp+57h+var_8C], eax
0x18005abd1  lea     rax, [rbp+57h+var_A0]
0x18005abd5  mov     [rsp+120h+var_B8], rax
0x18005abda  lea     rax, [rbp+57h+var_9C]
0x18005abde  mov     [rsp+120h+var_C0], rax
0x18005abe3  lea     rax, [rbp+57h+var_98]
0x18005abe7  mov     [rsp+120h+var_C8], rax
0x18005abec  lea     rax, [rbp+57h+var_94]
0x18005abf0  mov     [rsp+120h+var_D0], rax
0x18005abf5  lea     rax, [rbp+57h+var_90]
0x18005abf9  mov     [rsp+120h+var_D8], rax
0x18005abfe  lea     rax, [rbp+57h+var_8C]
0x18005ac02  mov     [rsp+120h+var_E0], rax
0x18005ac07  lea     rax, [rbp+57h+var_88]
0x18005ac0b  mov     [rsp+120h+var_E8], rax
0x18005ac10  lea     rax, [rbp+57h+var_84]
0x18005ac14  mov     [rsp+120h+var_F0], rax
0x18005ac19  lea     rax, [rbp+57h+var_A8]
0x18005ac1d  mov     [rsp+120h+var_F8], rax
0x18005ac22  lea     rax, [rbp+57h+var_B0]
0x18005ac26  mov     [rsp+120h+var_100], rax
0x18005ac2b  mov     [rbp+57h+var_88], r14d
0x18005ac2f  mov     [rbp+57h+var_84], esi
0x18005ac32  mov     dword ptr [rbp+57h+var_A8], r15d
0x18005ac36  mov     [rbp+57h+var_B0], 1
0x18005ac3a  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@44444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005ac3f  lea     rcx, [rbp+57h+var_80]
0x18005ac43  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18005ac48  mov     rcx, [rbp+57h+var_38]
0x18005ac4c  xor     rcx, rsp; StackCookie
0x18005ac4f  call    __security_check_cookie
0x18005ac54  add     rsp, 0F8h
0x18005ac5b  pop     r15
0x18005ac5d  pop     r14
0x18005ac5f  pop     rdi
0x18005ac60  pop     rsi
0x18005ac61  pop     rbx
0x18005ac62  pop     rbp
0x18005ac63  retn
```
