# SvcOpen

- ea: `0x14001e32c`
- end: `0x14001e55e`
- name: `SvcOpen`
- size: `562`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000d12c`
- `0x14000d420`
- `0x14000d5c8`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x14001e17c`
- `0x14001e32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e490`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14001e47d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14001e47d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14001e3d6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14001e3d6`

## string_xrefs

- `0x14001e34c`: `TrustedInstaller`
- `0x14001e377`: `No service handle result specified`
- `0x14001e3ff`: `Failed to connect to service control manager.`
- `0x14001e4a8`: `Failed to open service: {}`

## pseudocode

```c
__int64 __fastcall SvcOpen(__int64 a1, DWORD a2, SC_HANDLE *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  SC_HANDLE v7; // rax
  signed int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  SC_HANDLE v11; // rax
  __int64 v12; // rdx
  signed int LastError; // ebx
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-40h]
  unsigned int v19[2]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-28h] BYREF
  SC_HANDLE v21; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpServiceName; // [rsp+48h] [rbp-18h] BYREF
  int v23; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  lpServiceName = L"TrustedInstaller";
  if ( a3 )
  {
    v7 = OpenSCManagerW(0, 0, 1u);
    v21 = v7;
    if ( v7 )
    {
      v11 = OpenServiceW(v7, lpServiceName, a2);
      *(_QWORD *)v19 = v11;
      if ( v11 )
      {
        *(_QWORD *)v19 = 0;
        *a3 = v11;
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            v12,
            v14,
            (__int64)"Failed to open service: {}",
            (__int64)&lpServiceName);
          if ( LastError > 0 )
            v16 = (unsigned __int16)LastError | 0x80070000;
          else
            v16 = LastError;
          v23 = v16;
          *(_QWORD *)v20 = &v23;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v15,
            3,
            (__int64)": {0}",
            (__int64)v20);
        }
        if ( LastError )
        {
          v5 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0xD,
                 (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
                 (const char *)(unsigned int)LastError,
                 v18);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)v19);
          goto LABEL_24;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)v19);
    }
    else
    {
      v8 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to connect to service control manager.");
        if ( v8 > 0 )
          v10 = (unsigned __int16)v8 | 0x80070000;
        else
          v10 = v8;
        v23 = v10;
        *(_QWORD *)v19 = &v23;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v9,
          3,
          (__int64)": {0}",
          (__int64)v19);
      }
      if ( v8 )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xA,
               (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
               (const char *)(unsigned int)v8,
               v18);
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v21);
        return v5;
      }
    }
    v5 = 0;
    goto LABEL_24;
  }
  v5 = -2147467261;
  v23 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No service handle result specified");
    *(_QWORD *)v19 = &v23;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v6,
      3,
      (__int64)": {}",
      (__int64)v19);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)7,
    (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
    (const char *)0x80004003LL,
    v18);
  return v5;
}

```

## disassembly

```asm
0x14001e32c  mov     [rsp-8+arg_0], rbx
0x14001e331  mov     [rsp-8+arg_18], rdi
0x14001e336  push    rbp
0x14001e337  mov     rbp, rsp
0x14001e33a  sub     rsp, 60h
0x14001e33e  mov     rax, cs:__security_cookie
0x14001e345  xor     rax, rsp
0x14001e348  mov     [rbp+var_8], rax
0x14001e34c  lea     rax, ServiceName; "TrustedInstaller"
0x14001e353  mov     rbx, r8
0x14001e356  mov     [rbp+lpServiceName], rax
0x14001e35a  mov     edi, edx
0x14001e35c  test    r8, r8
0x14001e35f  jnz     short loc_14001E3CE
0x14001e361  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e368  mov     ebx, 80004003h
0x14001e36d  mov     [rbp+var_10], ebx
0x14001e370  test    rcx, rcx
0x14001e373  jz      short loc_14001E3B1
0x14001e375  xor     edx, edx
0x14001e377  lea     r9, aNoServiceHandl; "No service handle result specified"
0x14001e37e  lea     r8d, [rdx+3]
0x14001e382  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e387  lea     rcx, [rbp+var_30]
0x14001e38b  mov     r8d, 3
0x14001e391  mov     qword ptr [rsp+60h+var_40], rcx; int
0x14001e396  lea     rax, [rbp+var_10]
0x14001e39a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e3a1  lea     r9, asc_1400353E8; ": {}"
0x14001e3a8  mov     qword ptr [rbp+var_30], rax
0x14001e3ac  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e3b1  mov     rcx, [rbp+8]; this
0x14001e3b5  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e3bc  mov     r9d, ebx; char *
0x14001e3bf  mov     edx, 7; void *
0x14001e3c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e3c9  jmp     loc_14001E53E
0x14001e3ce  xor     edx, edx; lpDatabaseName
0x14001e3d0  xor     ecx, ecx; lpMachineName
0x14001e3d2  lea     r8d, [rdx+1]; dwDesiredAccess
0x14001e3d6  call    cs:__imp_OpenSCManagerW
0x14001e3dc  mov     [rbp+var_20], rax
0x14001e3e0  test    rax, rax
0x14001e3e3  jnz     loc_14001E473
0x14001e3e9  call    cs:__imp_GetLastError
0x14001e3ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e3f6  mov     ebx, eax
0x14001e3f8  test    rcx, rcx
0x14001e3fb  jz      short loc_14001E44C
0x14001e3fd  xor     edx, edx
0x14001e3ff  lea     r9, aFailedToConnec; "Failed to connect to service control ma"...
0x14001e406  lea     r8d, [rdx+3]
0x14001e40a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e40f  test    ebx, ebx
0x14001e411  jg      short loc_14001E417
0x14001e413  mov     eax, ebx
0x14001e415  jmp     short loc_14001E41F
0x14001e417  movzx   eax, bx
0x14001e41a  or      eax, 80070000h
0x14001e41f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e426  lea     r9, a0; ": {0}"
0x14001e42d  mov     [rbp+var_10], eax
0x14001e430  mov     r8d, 3
0x14001e436  lea     rax, [rbp+var_10]
0x14001e43a  mov     qword ptr [rbp+var_30], rax
0x14001e43e  lea     rax, [rbp+var_30]
0x14001e442  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x14001e447  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e44c  test    ebx, ebx
0x14001e44e  jz      loc_14001E533
0x14001e454  mov     rcx, [rbp+8]; this
0x14001e458  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e45f  mov     r9d, ebx; char *
0x14001e462  mov     edx, 0Ah; void *
0x14001e467  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001e46c  mov     ebx, eax
0x14001e46e  jmp     loc_14001E535
0x14001e473  mov     rdx, [rbp+lpServiceName]; lpServiceName
0x14001e477  mov     r8d, edi; dwDesiredAccess
0x14001e47a  mov     rcx, rax; hSCManager
0x14001e47d  call    cs:__imp_OpenServiceW
0x14001e483  mov     qword ptr [rbp+var_30], rax
0x14001e487  test    rax, rax
0x14001e48a  jnz     loc_14001E51F
0x14001e490  call    cs:__imp_GetLastError
0x14001e496  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e49d  mov     ebx, eax
0x14001e49f  test    rcx, rcx
0x14001e4a2  jz      short loc_14001E4F6
0x14001e4a4  lea     rax, [rbp+lpServiceName]
0x14001e4a8  lea     r9, aFailedToOpenSe_0; "Failed to open service: {}"
0x14001e4af  mov     qword ptr [rsp+60h+var_40], rax
0x14001e4b4  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001e4b9  test    ebx, ebx
0x14001e4bb  jg      short loc_14001E4C1
0x14001e4bd  mov     eax, ebx
0x14001e4bf  jmp     short loc_14001E4C9
0x14001e4c1  movzx   eax, bx
0x14001e4c4  or      eax, 80070000h
0x14001e4c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e4d0  lea     r9, a0; ": {0}"
0x14001e4d7  mov     [rbp+var_10], eax
0x14001e4da  mov     r8d, 3
0x14001e4e0  lea     rax, [rbp+var_10]
0x14001e4e4  mov     qword ptr [rbp+var_28], rax
0x14001e4e8  lea     rax, [rbp+var_28]
0x14001e4ec  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x14001e4f1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e4f6  test    ebx, ebx
0x14001e4f8  jz      short loc_14001E52A
0x14001e4fa  mov     rcx, [rbp+8]; this
0x14001e4fe  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e505  mov     r9d, ebx; char *
0x14001e508  mov     edx, 0Dh; void *
0x14001e50d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001e512  lea     rcx, [rbp+var_30]
0x14001e516  mov     ebx, eax
0x14001e518  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14001e51d  jmp     short loc_14001E535
0x14001e51f  mov     qword ptr [rbp+var_30], 0
0x14001e527  mov     [rbx], rax
0x14001e52a  lea     rcx, [rbp+var_30]
0x14001e52e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14001e533  xor     ebx, ebx
0x14001e535  lea     rcx, [rbp+var_20]
0x14001e539  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x14001e53e  mov     eax, ebx
0x14001e540  mov     rcx, [rbp+var_8]
0x14001e544  xor     rcx, rsp; StackCookie
0x14001e547  call    __security_check_cookie
0x14001e54c  lea     r11, [rsp+60h+var_s0]
0x14001e551  mov     rbx, [r11+10h]
0x14001e555  mov     rdi, [r11+28h]
0x14001e559  mov     rsp, r11
0x14001e55c  pop     rbp
0x14001e55d  retn
```
