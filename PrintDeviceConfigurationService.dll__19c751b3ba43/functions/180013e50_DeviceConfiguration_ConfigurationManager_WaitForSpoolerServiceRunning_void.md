# DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning(void)

- ea: `0x180013e50`
- end: `0x18001408c`
- name: `?_WaitForSpoolerServiceRunning@ConfigurationManager@DeviceConfiguration@@AEAAXXZ`
- size: `572`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180012df8`
- `0x180013600`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000b7f8`
- `0x18000b92c`
- `0x18000f9ec`
- `0x180011510`
- `0x180011b6c`
- `0x180013e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014033`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180013e7a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180013e7a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180013ebb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180013ebb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180013efe`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180013efe`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180013f44`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180013f44`
- `WINSPOOL!EnumPrintersW` at `0x180013fac`
- `WINSPOOL!EnumPrintersW` at `0x180013ff6`
- `WINSPOOL!EnumPrintersW` at `0x180013fac`
- `WINSPOOL!EnumPrintersW` at `0x180013ff6`

## string_xrefs

- `0x180013e9a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013edb`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013f1d`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013f64`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013e8b`: `OpenSCManager failed!`
- `0x180013ecc`: `OpenService failed!`
- `0x180013f0d`: `QueryServiceStatus failed!`
- `0x180013f54`: `Spooler service did not reach the running state!`
- `0x18001401c`: `DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning`
- `0x18001404f`: `DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning(
        DeviceConfiguration::ConfigurationManager *this)
{
  SC_HANDLE v1; // rbx
  BOOL v2; // eax
  int v3; // eax
  signed int LastError; // eax
  signed int v5; // eax
  const char *pcbNeeded; // [rsp+28h] [rbp-21h]
  const char *pcbNeededa; // [rsp+28h] [rbp-21h]
  DWORD cbBuf; // [rsp+40h] [rbp-9h] BYREF
  DWORD pcReturned; // [rsp+44h] [rbp-5h] BYREF
  SC_HANDLE v10; // [rsp+48h] [rbp-1h] BYREF
  SC_HANDLE v11; // [rsp+50h] [rbp+7h] BYREF
  LPBYTE pPrinterEnum[3]; // [rsp+58h] [rbp+Fh] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v11 = OpenSCManagerW(0, 0, 0xF003Fu);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    (int)retaddr,
    592,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (__int64)v11,
    (__int64)"OpenSCManager failed!");
  v1 = OpenServiceW(v11, L"Spooler", 0xF01FFu);
  v10 = v1;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    (int)retaddr,
    595,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (__int64)v1,
    (__int64)"OpenService failed!");
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = QueryServiceStatus(v1, &ServiceStatus);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x256,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)!v2,
    (bool)"QueryServiceStatus failed!",
    pcbNeeded);
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    v3 = WaitServiceState(v1, 8, 30000);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x259,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)(v3 != 4),
      (bool)"Spooler service did not reach the running state!",
      pcbNeededa);
  }
  cbBuf = 0;
  pcReturned = 0;
  if ( !EnumPrintersW(0xAu, 0, 2u, 0, 0, &cbBuf, &pcReturned) )
  {
    if ( GetLastError() == 122 )
    {
      std::vector<unsigned char>::vector<unsigned char>(pPrinterEnum, cbBuf);
      if ( !EnumPrintersW(0xAu, 0, 2u, pPrinterEnum[0], cbBuf, &cbBuf, &pcReturned) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        DeviceConfigurationTelemetry::WriteDbgTraceError(
          "DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning",
          L"EnumPrinters (with buffer) after Spooler start, failed! Hr: 0x%x",
          (unsigned int)LastError);
      }
      std::vector<unsigned char>::_Tidy((__int64)pPrinterEnum);
    }
    else
    {
      v5 = GetLastError();
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning",
        L"EnumPrinters (no buffer) after Spooler start, failed! Hr: 0x%x",
        (unsigned int)v5);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v11);
}

```

## disassembly

```asm
0x180013e50  mov     [rsp-8+arg_0], rbx
0x180013e55  push    rbp
0x180013e56  lea     rbp, [rsp-57h]
0x180013e5b  sub     rsp, 0A0h
0x180013e62  mov     rax, cs:__security_cookie
0x180013e69  xor     rax, rsp
0x180013e6c  mov     [rbp+57h+var_10], rax
0x180013e70  xor     edx, edx; lpDatabaseName
0x180013e72  mov     r8d, 0F003Fh; dwDesiredAccess
0x180013e78  xor     ecx, ecx; lpMachineName
0x180013e7a  call    cs:__imp_OpenSCManagerW
0x180013e80  mov     rbx, rax
0x180013e83  mov     [rbp+57h+var_50], rax
0x180013e87  mov     rcx, [rbp+5Fh]
0x180013e8b  lea     rax, aOpenscmanagerF; "OpenSCManager failed!"
0x180013e92  mov     qword ptr [rsp+0A0h+cbBuf], rax
0x180013e97  mov     r9, rbx
0x180013e9a  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013ea1  mov     edx, 250h
0x180013ea6  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x180013eab  mov     r8d, 0F01FFh; dwDesiredAccess
0x180013eb1  lea     rdx, aSpooler; "Spooler"
0x180013eb8  mov     rcx, rbx; hSCManager
0x180013ebb  call    cs:__imp_OpenServiceW
0x180013ec1  mov     rbx, rax
0x180013ec4  mov     [rbp+57h+var_58], rax
0x180013ec8  mov     rcx, [rbp+5Fh]
0x180013ecc  lea     rax, aOpenserviceFai; "OpenService failed!"
0x180013ed3  mov     qword ptr [rsp+0A0h+cbBuf], rax
0x180013ed8  mov     r9, rbx
0x180013edb  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013ee2  mov     edx, 253h
0x180013ee7  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x180013eec  xorps   xmm0, xmm0
0x180013eef  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180013ef3  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180013ef7  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180013efb  mov     rcx, rbx; hService
0x180013efe  call    cs:__imp_QueryServiceStatus
0x180013f04  test    eax, eax
0x180013f06  setz    al
0x180013f09  mov     rcx, [rbp+5Fh]; this
0x180013f0d  lea     rdx, aQueryservicest_0; "QueryServiceStatus failed!"
0x180013f14  mov     qword ptr [rsp+0A0h+cbBuf], rdx; bool
0x180013f19  movzx   r9d, al; char *
0x180013f1d  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013f24  mov     edx, 256h; void *
0x180013f29  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180013f2e  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x180013f32  jz      short loc_180013F75
0x180013f34  xor     r9d, r9d
0x180013f37  lea     edx, [r9+8]
0x180013f3b  mov     r8d, 7530h
0x180013f41  mov     rcx, rbx
0x180013f44  call    cs:__imp_WaitServiceState
0x180013f4a  cmp     eax, 4
0x180013f4d  setnz   al
0x180013f50  mov     rcx, [rbp+5Fh]; this
0x180013f54  lea     rdx, aSpoolerService; "Spooler service did not reach the runni"...
0x180013f5b  mov     qword ptr [rsp+0A0h+cbBuf], rdx; bool
0x180013f60  movzx   r9d, al; char *
0x180013f64  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013f6b  mov     edx, 259h; void *
0x180013f70  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180013f75  mov     [rbp+57h+var_60], 0
0x180013f7c  mov     [rbp+57h+var_5C], 0
0x180013f83  lea     rax, [rbp+57h+var_5C]
0x180013f87  mov     [rsp+0A0h+pcReturned], rax; pcReturned
0x180013f8c  lea     rax, [rbp+57h+var_60]
0x180013f90  mov     [rsp+0A0h+pcbNeeded], rax; pcbNeeded
0x180013f95  mov     [rsp+0A0h+cbBuf], 0; cbBuf
0x180013f9d  xor     r9d, r9d; pPrinterEnum
0x180013fa0  lea     ebx, [r9+2]
0x180013fa4  mov     r8d, ebx; Level
0x180013fa7  xor     edx, edx; Name
0x180013fa9  lea     ecx, [rbx+8]; Flags
0x180013fac  call    cs:__imp_EnumPrintersW
0x180013fb2  test    eax, eax
0x180013fb4  jnz     loc_18001405C
0x180013fba  call    cs:__imp_GetLastError
0x180013fc0  cmp     eax, 7Ah ; 'z'
0x180013fc3  jnz     short loc_180014033
0x180013fc5  mov     edx, [rbp+57h+var_60]
0x180013fc8  lea     rcx, [rbp+57h+pPrinterEnum]
0x180013fcc  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180013fd1  mov     eax, [rbp+57h+var_60]
0x180013fd4  lea     rdx, [rbp+57h+var_5C]
0x180013fd8  mov     [rsp+0A0h+pcReturned], rdx; pcReturned
0x180013fdd  lea     rdx, [rbp+57h+var_60]
0x180013fe1  mov     [rsp+0A0h+pcbNeeded], rdx; pcbNeeded
0x180013fe6  mov     [rsp+0A0h+cbBuf], eax; cbBuf
0x180013fea  mov     r9, [rbp+57h+pPrinterEnum]; pPrinterEnum
0x180013fee  mov     r8d, ebx; Level
0x180013ff1  xor     edx, edx; Name
0x180013ff3  lea     ecx, [rbx+8]; Flags
0x180013ff6  call    cs:__imp_EnumPrintersW
0x180013ffc  test    eax, eax
0x180013ffe  jnz     short loc_180014028
0x180014000  call    cs:__imp_GetLastError
0x180014006  test    eax, eax
0x180014008  jle     short loc_180014012
0x18001400a  movzx   eax, ax
0x18001400d  or      eax, 80070000h
0x180014012  mov     r8d, eax
0x180014015  lea     rdx, aEnumprintersWi; "EnumPrinters (with buffer) after Spoole"...
0x18001401c  lea     rcx, aDeviceconfigur_7; "DeviceConfiguration::ConfigurationManag"...
0x180014023  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180014028  lea     rcx, [rbp+57h+pPrinterEnum]
0x18001402c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014031  jmp     short loc_18001405C
0x180014033  call    cs:__imp_GetLastError
0x180014039  test    eax, eax
0x18001403b  jle     short loc_180014045
0x18001403d  movzx   eax, ax
0x180014040  or      eax, 80070000h
0x180014045  mov     r8d, eax
0x180014048  lea     rdx, aEnumprintersNo_0; "EnumPrinters (no buffer) after Spooler "...
0x18001404f  lea     rcx, aDeviceconfigur_7; "DeviceConfiguration::ConfigurationManag"...
0x180014056  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001405b  nop
0x18001405c  lea     rcx, [rbp+57h+var_58]
0x180014060  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180014065  nop
0x180014066  lea     rcx, [rbp+57h+var_50]
0x18001406a  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18001406f  mov     rcx, [rbp+57h+var_10]
0x180014073  xor     rcx, rsp; StackCookie
0x180014076  call    __security_check_cookie
0x18001407b  mov     rbx, [rsp+0A0h+arg_0]
0x180014083  add     rsp, 0A0h
0x18001408a  pop     rbp
0x18001408b  retn
```
