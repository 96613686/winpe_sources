# StopNgcCtnrSvc(void)

- ea: `0x18003cccc`
- end: `0x18003cdf4`
- name: `?StopNgcCtnrSvc@@YAJXZ`
- size: `296`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003cbf0`

## callees

- `0x180022e68`
- `0x18002c640`
- `0x18003b650`
- `0x18003cba4`
- `0x18003cccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cda0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003cd2a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003cd2a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003cce9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003cce9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18003cd7c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18003cd7c`

## string_xrefs

- `0x18003cd04`: `onecore\ds\security\ngc\ctnrsvc\service\ngcisowatchdog.cpp`
- `0x18003cd45`: `onecore\ds\security\ngc\ctnrsvc\service\ngcisowatchdog.cpp`
- `0x18003cd91`: `onecore\ds\security\ngc\ctnrsvc\service\ngcisowatchdog.cpp`

## pseudocode

```c
__int64 StopNgcCtnrSvc(void)
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  signed int LastError; // eax
  SC_HANDLE v8; // [rsp+20h] [rbp-48h] BYREF
  SC_HANDLE v9; // [rsp+28h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 1u);
  v9 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"NgcCtnrSvc", 0x24u);
    v8 = v3;
    if ( v3 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(v3, 1u, &ServiceStatus)
        || (wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x45,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\ngcisowatchdog.cpp",
              v5),
            LastError = GetLastError(),
            v2 = LastError,
            (unsigned int)(LastError - 1061) <= 1) )
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v8);
        v2 = 0;
        goto LABEL_11;
      }
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v2 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x42,
             (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\ngcisowatchdog.cpp",
             v4);
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v8);
  }
  else
  {
    v2 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x3F,
           (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\ngcisowatchdog.cpp",
           v1);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v9);
  return v2;
}

```

## disassembly

```asm
0x18003cccc  push    rbx
0x18003ccce  sub     rsp, 60h
0x18003ccd2  mov     rax, cs:__security_cookie
0x18003ccd9  xor     rax, rsp
0x18003ccdc  mov     [rsp+68h+var_18], rax
0x18003cce1  xor     edx, edx; lpDatabaseName
0x18003cce3  xor     ecx, ecx; lpMachineName
0x18003cce5  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003cce9  call    cs:__imp_OpenSCManagerW
0x18003ccf0  nop     dword ptr [rax+rax+00h]
0x18003ccf5  mov     [rsp+68h+var_40], rax
0x18003ccfa  test    rax, rax
0x18003ccfd  jnz     short loc_18003CD1A
0x18003ccff  mov     rcx, [rsp+68h]; this
0x18003cd04  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003cd0b  lea     edx, [rax+3Fh]; void *
0x18003cd0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003cd13  mov     ebx, eax
0x18003cd15  jmp     loc_18003CDD4
0x18003cd1a  mov     r8d, 24h ; '$'; dwDesiredAccess
0x18003cd20  lea     rdx, aNgcctnrsvc; "NgcCtnrSvc"
0x18003cd27  mov     rcx, rax; hSCManager
0x18003cd2a  call    cs:__imp_OpenServiceW
0x18003cd31  nop     dword ptr [rax+rax+00h]
0x18003cd36  mov     [rsp+68h+var_48], rax
0x18003cd3b  test    rax, rax
0x18003cd3e  jnz     short loc_18003CD62
0x18003cd40  mov     rcx, [rsp+68h]; this
0x18003cd45  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003cd4c  lea     edx, [rax+42h]; void *
0x18003cd4f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003cd54  mov     ebx, eax
0x18003cd56  lea     rcx, [rsp+68h+var_48]
0x18003cd5b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003cd60  jmp     short loc_18003CDD4
0x18003cd62  xorps   xmm0, xmm0
0x18003cd65  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18003cd6a  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18003cd6f  mov     edx, 1; dwControl
0x18003cd74  mov     rcx, rax; hService
0x18003cd77  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003cd7c  call    cs:__imp_ControlService
0x18003cd83  nop     dword ptr [rax+rax+00h]
0x18003cd88  test    eax, eax
0x18003cd8a  jnz     short loc_18003CDC8
0x18003cd8c  mov     rcx, [rsp+68h]; this
0x18003cd91  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003cd98  lea     edx, [rax+45h]; void *
0x18003cd9b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003cda0  call    cs:__imp_GetLastError
0x18003cda7  nop     dword ptr [rax+rax+00h]
0x18003cdac  mov     ebx, eax
0x18003cdae  lea     ecx, [rax-425h]
0x18003cdb4  cmp     ecx, 1
0x18003cdb7  jbe     short loc_18003CDC8
0x18003cdb9  test    eax, eax
0x18003cdbb  jle     short loc_18003CD56
0x18003cdbd  movzx   ebx, ax
0x18003cdc0  or      ebx, 80070000h
0x18003cdc6  jmp     short loc_18003CD56
0x18003cdc8  lea     rcx, [rsp+68h+var_48]
0x18003cdcd  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003cdd2  xor     ebx, ebx
0x18003cdd4  lea     rcx, [rsp+68h+var_40]
0x18003cdd9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18003cdde  mov     eax, ebx
0x18003cde0  mov     rcx, [rsp+68h+var_18]
0x18003cde5  xor     rcx, rsp; StackCookie
0x18003cde8  call    __security_check_cookie
0x18003cded  add     rsp, 60h
0x18003cdf1  pop     rbx
0x18003cdf2  retn
```
