# FSServiceControlAction::OpenTargetServiceHandle(void)

- ea: `0x1800a83b8`
- end: `0x1800a8493`
- name: `?OpenTargetServiceHandle@FSServiceControlAction@@AEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a8560`

## callees

- `0x180009404`
- `0x180009aa0`
- `0x18000cc6c`
- `0x18009fcf4`
- `0x1800a83b8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a83cb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a83cb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800a8403`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800a8403`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a845c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a845c`

## string_xrefs

- `0x1800a83e0`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicecontrolaction.cpp`
- `0x1800a841b`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicecontrolaction.cpp`

## pseudocode

```c
__int64 __fastcall FSServiceControlAction::OpenTargetServiceHandle(LPCWSTR *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  unsigned int LastError; // ebx
  const char *v5; // r9
  const WCHAR *v6; // rsi
  SC_HANDLE v7; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SC_HANDLE v10; // [rsp+48h] [rbp+10h] BYREF
  char v11; // [rsp+50h] [rbp+18h] BYREF
  SC_HANDLE v12; // [rsp+58h] [rbp+20h] BYREF

  v2 = OpenSCManagerW(0, 0, 1u);
  v12 = v2;
  if ( v2 )
  {
    v10 = OpenServiceW(v2, this[8], 0x36u);
    v6 = (const WCHAR *)v10;
    if ( v10 )
    {
      v7 = (SC_HANDLE)this[19];
      v10 = 0;
      if ( v7 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        CloseServiceHandle(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      this[19] = v6;
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x80,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
                    v5);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x77,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
                  v3);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
  return LastError;
}

```

## disassembly

```asm
0x1800a83b8  push    rbx
0x1800a83ba  push    rsi
0x1800a83bb  push    rdi
0x1800a83bc  sub     rsp, 20h
0x1800a83c0  xor     edx, edx; lpDatabaseName
0x1800a83c2  mov     rbx, rcx
0x1800a83c5  xor     ecx, ecx; lpMachineName
0x1800a83c7  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800a83cb  call    cs:__imp_OpenSCManagerW
0x1800a83d1  mov     [rsp+38h+arg_18], rax
0x1800a83d6  test    rax, rax
0x1800a83d9  jnz     short loc_1800A83F6
0x1800a83db  mov     rcx, [rsp+38h]; this
0x1800a83e0  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\flightsetting"...
0x1800a83e7  lea     edx, [rax+77h]; void *
0x1800a83ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a83ef  mov     ebx, eax
0x1800a83f1  jmp     loc_1800A847F
0x1800a83f6  mov     rdx, [rbx+40h]; lpServiceName
0x1800a83fa  mov     r8d, 36h ; '6'; dwDesiredAccess
0x1800a8400  mov     rcx, rax; hSCManager
0x1800a8403  call    cs:__imp_OpenServiceW
0x1800a8409  mov     [rsp+38h+arg_8], rax
0x1800a840e  mov     rsi, rax
0x1800a8411  test    rax, rax
0x1800a8414  jnz     short loc_1800A843A
0x1800a8416  mov     rcx, [rsp+38h]; this
0x1800a841b  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\flightsetting"...
0x1800a8422  mov     edx, 80h; void *
0x1800a8427  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a842c  lea     rcx, [rsp+38h+arg_8]
0x1800a8431  mov     ebx, eax
0x1800a8433  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800a8438  jmp     short loc_1800A847F
0x1800a843a  mov     rdi, [rbx+98h]
0x1800a8441  mov     [rsp+38h+arg_8], 0
0x1800a844a  test    rdi, rdi
0x1800a844d  jz      short loc_1800A846C
0x1800a844f  lea     rcx, [rsp+38h+arg_10]; this
0x1800a8454  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a8459  mov     rcx, rdi; hSCObject
0x1800a845c  call    cs:__imp_CloseServiceHandle
0x1800a8462  lea     rcx, [rsp+38h+arg_10]; this
0x1800a8467  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a846c  lea     rcx, [rsp+38h+arg_8]
0x1800a8471  mov     [rbx+98h], rsi
0x1800a8478  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800a847d  xor     ebx, ebx
0x1800a847f  lea     rcx, [rsp+38h+arg_18]
0x1800a8484  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800a8489  mov     eax, ebx
0x1800a848b  add     rsp, 20h
0x1800a848f  pop     rdi
0x1800a8490  pop     rsi
0x1800a8491  pop     rbx
0x1800a8492  retn
```
