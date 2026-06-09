# DeviceConfiguration::ConfigurationManager::_StopDependentServices(SC_HANDLE__ *,SC_HANDLE__ *)

- ea: `0x180013644`
- end: `0x1800138c3`
- name: `?_StopDependentServices@ConfigurationManager@DeviceConfiguration@@AEAAXPEAUSC_HANDLE__@@0@Z`
- size: `639`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, SC_HANDLE, SC_HANDLE)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18001260c`

## callees

- `0x1800020c0`
- `0x18000b7f8`
- `0x18000b92c`
- `0x18000f9ec`
- `0x180011510`
- `0x180011b6c`
- `0x180013644`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013832`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136ac`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001376e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001376e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800137b5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180013840`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800137b5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180013840`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800137f6`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800137f6`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18001369d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18001371e`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18001369d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18001371e`

## string_xrefs

- `0x1800136d2`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013784`: `OpenService failed!`
- `0x180013749`: `QueryServiceStatus failed!`
- `0x180013853`: `QueryServiceStatus failed!`
- `0x18001387b`: `QueryServiceStatus failed!`
- `0x180013809`: `ControlService (Service Stop) failed!`
- `0x1800136c2`: `EnumDependentServices failed!`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_StopDependentServices(
        DeviceConfiguration::ConfigurationManager *this,
        SC_HANDLE a2,
        SC_HANDLE a3)
{
  _BOOL8 v5; // r9
  LPENUM_SERVICE_STATUSW v6; // r15
  BOOL v7; // eax
  SC_HANDLE v8; // rbx
  BOOL v9; // eax
  BOOL v10; // eax
  unsigned int j; // esi
  BOOL v12; // eax
  __int64 i; // rdi
  const char *v14; // r9
  const char *lpServicesReturned; // [rsp+28h] [rbp-80h]
  const char *lpServicesReturnedb; // [rsp+28h] [rbp-80h]
  const char *lpServicesReturneda; // [rsp+28h] [rbp-80h]
  DWORD cbBufSize; // [rsp+30h] [rbp-78h] BYREF
  DWORD ServicesReturned; // [rsp+34h] [rbp-74h] BYREF
  SC_HANDLE v20; // [rsp+38h] [rbp-70h] BYREF
  LPENUM_SERVICE_STATUSW lpServices[3]; // [rsp+40h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  cbBufSize = 0;
  ServicesReturned = 0;
  if ( !EnumDependentServicesW(a3, 1u, 0, 0, &cbBufSize, &ServicesReturned) )
  {
    v5 = GetLastError() != 234;
    try
    {
      wil::details::in1diag3::Throw_GetLastErrorIfMsg(
        retaddr,
        (void *)0x2FB,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
        (const char *)v5,
        (bool)"EnumDependentServices failed!",
        lpServicesReturned);
      std::vector<unsigned char>::vector<unsigned char>(lpServices, cbBufSize);
      v6 = lpServices[0];
      v7 = EnumDependentServicesW(a3, 1u, lpServices[0], cbBufSize, &cbBufSize, &ServicesReturned);
      wil::details::in1diag3::Throw_GetLastErrorIfMsg(
        retaddr,
        (void *)0x2FF,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
        (const char *)!v7,
        (bool)"EnumDependentServices failed!",
        lpServicesReturnedb);
      for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
      {
        v8 = OpenServiceW(a2, v6[i].lpServiceName, 0x24u);
        v20 = v8;
        wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
          (int)retaddr,
          772,
          (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
          (__int64)v8,
          (__int64)"OpenService failed!");
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        v9 = QueryServiceStatus(v8, &ServiceStatus);
        wil::details::in1diag3::Throw_GetLastErrorIfMsg(
          retaddr,
          (void *)0x308,
          (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
          (const char *)!v9,
          (bool)"QueryServiceStatus failed!",
          lpServicesReturneda);
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          v10 = ControlService(v8, 1u, &ServiceStatus);
          wil::details::in1diag3::Throw_GetLastErrorIfMsg(
            retaddr,
            (void *)0x30B,
            (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
            (const char *)!v10,
            (bool)"ControlService (Service Stop) failed!",
            lpServicesReturneda);
          for ( j = 0; j < 5; ++j )
          {
            Sleep(0x3E8u);
            v12 = QueryServiceStatus(v8, &ServiceStatus);
            wil::details::in1diag3::Throw_GetLastErrorIfMsg(
              retaddr,
              (void *)0x30F,
              (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
              (const char *)!v12,
              (bool)"QueryServiceStatus failed!",
              lpServicesReturneda);
            if ( ServiceStatus.dwCurrentState == 1 )
              break;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
      }
      std::vector<unsigned char>::_Tidy(lpServices);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x319,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
        v14);
    }
  }
}

```

## disassembly

```asm
0x180013644  mov     r11, rsp
0x180013647  mov     [r11+8], rbx
0x18001364b  push    rsi
0x18001364c  push    rdi
0x18001364d  push    r13
0x18001364f  push    r14
0x180013651  push    r15
0x180013653  sub     rsp, 80h
0x18001365a  mov     rax, cs:__security_cookie
0x180013661  xor     rax, rsp
0x180013664  mov     [rsp+0A8h+var_30], rax
0x180013669  mov     rbx, r8
0x18001366c  mov     r14, rdx
0x18001366f  mov     [rsp+0A8h+cbBufSize], 0
0x180013677  mov     [rsp+0A8h+ServicesReturned], 0
0x18001367f  lea     rax, [r11-74h]
0x180013683  mov     [r11-80h], rax
0x180013687  lea     rax, [r11-78h]
0x18001368b  mov     [rsp+0A8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180013690  xor     r9d, r9d; cbBufSize
0x180013693  xor     r8d, r8d; lpServices
0x180013696  lea     edx, [r9+1]; dwServiceState
0x18001369a  mov     rcx, rbx; hService
0x18001369d  call    cs:__imp_EnumDependentServicesW
0x1800136a3  test    eax, eax
0x1800136a5  jz      short loc_1800136AC
0x1800136a7  jmp     loc_18001389E
0x1800136ac  call    cs:__imp_GetLastError
0x1800136b2  cmp     eax, 0EAh
0x1800136b7  setnz   al
0x1800136ba  mov     rcx, [rsp+0A8h]; this
0x1800136c2  lea     rdi, aEnumdependents_0; "EnumDependentServices failed!"
0x1800136c9  mov     [rsp+0A8h+pcbBytesNeeded], rdi; bool
0x1800136ce  movzx   r9d, al; char *
0x1800136d2  lea     r13, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800136d9  mov     r8, r13; unsigned int
0x1800136dc  mov     edx, 2FBh; void *
0x1800136e1  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800136e6  mov     edx, [rsp+0A8h+cbBufSize]
0x1800136ea  lea     rcx, [rsp+0A8h+lpServices]
0x1800136ef  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800136f4  nop
0x1800136f5  mov     r15, [rsp+0A8h+lpServices]
0x1800136fa  lea     rax, [rsp+0A8h+ServicesReturned]
0x1800136ff  mov     [rsp+0A8h+lpServicesReturned], rax; char *
0x180013704  lea     rax, [rsp+0A8h+cbBufSize]
0x180013709  mov     [rsp+0A8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001370e  mov     r9d, [rsp+0A8h+cbBufSize]; cbBufSize
0x180013713  mov     r8, r15; lpServices
0x180013716  mov     edx, 1; dwServiceState
0x18001371b  mov     rcx, rbx; hService
0x18001371e  call    cs:__imp_EnumDependentServicesW
0x180013724  test    eax, eax
0x180013726  setz    al
0x180013729  mov     rcx, [rsp+0A8h]; this
0x180013731  mov     [rsp+0A8h+pcbBytesNeeded], rdi; bool
0x180013736  movzx   r9d, al; char *
0x18001373a  mov     r8, r13; unsigned int
0x18001373d  mov     edx, 2FFh; void *
0x180013742  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180013747  xor     edi, edi
0x180013749  lea     rsi, aQueryservicest_0; "QueryServiceStatus failed!"
0x180013750  cmp     edi, [rsp+0A8h+ServicesReturned]
0x180013754  jnb     loc_180013893
0x18001375a  lea     rdx, [rdi+rdi*2]
0x18001375e  add     rdx, rdx
0x180013761  mov     r8d, 24h ; '$'; dwDesiredAccess
0x180013767  mov     rdx, [r15+rdx*8]; lpServiceName
0x18001376b  mov     rcx, r14; hSCManager
0x18001376e  call    cs:__imp_OpenServiceW
0x180013774  mov     rbx, rax
0x180013777  mov     [rsp+0A8h+var_70], rax
0x18001377c  mov     rcx, [rsp+0A8h]
0x180013784  lea     rax, aOpenserviceFai; "OpenService failed!"
0x18001378b  mov     [rsp+0A8h+pcbBytesNeeded], rax
0x180013790  mov     r9, rbx
0x180013793  mov     r8, r13
0x180013796  mov     edx, 304h
0x18001379b  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x1800137a0  xorps   xmm0, xmm0
0x1800137a3  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1800137a8  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800137ad  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800137b2  mov     rcx, rbx; hService
0x1800137b5  call    cs:__imp_QueryServiceStatus
0x1800137bb  test    eax, eax
0x1800137bd  setz    al
0x1800137c0  mov     rcx, [rsp+0A8h]; this
0x1800137c8  mov     [rsp+0A8h+pcbBytesNeeded], rsi; bool
0x1800137cd  movzx   r9d, al; char *
0x1800137d1  mov     r8, r13; unsigned int
0x1800137d4  mov     edx, 308h; void *
0x1800137d9  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800137de  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x1800137e3  jnz     loc_180013882
0x1800137e9  lea     r8, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800137ee  mov     edx, 1; dwControl
0x1800137f3  mov     rcx, rbx; hService
0x1800137f6  call    cs:__imp_ControlService
0x1800137fc  test    eax, eax
0x1800137fe  setz    al
0x180013801  mov     rcx, [rsp+0A8h]; this
0x180013809  lea     rdx, aControlservice_1; "ControlService (Service Stop) failed!"
0x180013810  mov     [rsp+0A8h+pcbBytesNeeded], rdx; bool
0x180013815  movzx   r9d, al; char *
0x180013819  mov     r8, r13; unsigned int
0x18001381c  mov     edx, 30Bh; void *
0x180013821  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180013826  xor     esi, esi
0x180013828  cmp     esi, 5
0x18001382b  jnb     short loc_18001387B
0x18001382d  mov     ecx, 3E8h; dwMilliseconds
0x180013832  call    cs:__imp_Sleep
0x180013838  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x18001383d  mov     rcx, rbx; hService
0x180013840  call    cs:__imp_QueryServiceStatus
0x180013846  test    eax, eax
0x180013848  setz    al
0x18001384b  mov     rcx, [rsp+0A8h]; this
0x180013853  lea     rdx, aQueryservicest_0; "QueryServiceStatus failed!"
0x18001385a  mov     [rsp+0A8h+pcbBytesNeeded], rdx; bool
0x18001385f  movzx   r9d, al; char *
0x180013863  mov     r8, r13; unsigned int
0x180013866  mov     edx, 30Fh; void *
0x18001386b  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180013870  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 1
0x180013875  jz      short loc_18001387B
0x180013877  inc     esi
0x180013879  jmp     short loc_180013828
0x18001387b  lea     rsi, aQueryservicest_0; "QueryServiceStatus failed!"
0x180013882  lea     rcx, [rsp+0A8h+var_70]
0x180013887  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18001388c  inc     edi
0x18001388e  jmp     loc_180013750
0x180013893  lea     rcx, [rsp+0A8h+lpServices]
0x180013898  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001389d  nop
0x18001389e  mov     rcx, [rsp+0A8h+var_30]
0x1800138a3  xor     rcx, rsp; StackCookie
0x1800138a6  call    __security_check_cookie
0x1800138ab  mov     rbx, [rsp+0A8h+arg_0]
0x1800138b3  add     rsp, 80h
0x1800138ba  pop     r15
0x1800138bc  pop     r14
0x1800138be  pop     r13
0x1800138c0  pop     rdi
0x1800138c1  pop     rsi
0x1800138c2  retn
```
