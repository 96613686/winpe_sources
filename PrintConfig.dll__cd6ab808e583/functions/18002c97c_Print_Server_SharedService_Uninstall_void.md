# Print::Server::SharedService::Uninstall(void)

- ea: `0x18002c97c`
- end: `0x18002cc23`
- name: `?Uninstall@SharedService@Server@Print@@SAXXZ`
- size: `679`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180031a80`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x18002c8b4`
- `0x18002c97c`
- `0x1800362f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c9ec`
- `KERNEL32!GetLastError` at `0x18002c9ec`
- `ADVAPI32!RegCloseKey` at `0x18002cb67`
- `ADVAPI32!RegCloseKey` at `0x18002cb67`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ca7a`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ca7a`
- `ADVAPI32!CloseServiceHandle` at `0x18002cb79`
- `ADVAPI32!CloseServiceHandle` at `0x18002cb83`
- `ADVAPI32!CloseServiceHandle` at `0x18002cb79`
- `ADVAPI32!CloseServiceHandle` at `0x18002cb83`
- `ADVAPI32!OpenSCManagerW` at `0x18002c9b1`
- `ADVAPI32!OpenSCManagerW` at `0x18002c9b1`
- `ADVAPI32!OpenServiceW` at `0x18002c9da`
- `ADVAPI32!OpenServiceW` at `0x18002c9da`
- `ADVAPI32!DeleteService` at `0x18002ca25`
- `ADVAPI32!DeleteService` at `0x18002ca25`
- `ADVAPI32!RegDeleteValueW` at `0x18002cad9`
- `ADVAPI32!RegDeleteValueW` at `0x18002cad9`

## string_xrefs

- `0x18002cbc3`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002cbf5`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002ca0d`: `Service did not exist but we were asked to uninstall.`
- `0x18002ca33`: `Service deleted.`
- `0x18002ca14`: `Print::Server::SharedService::Uninstall`
- `0x18002ca3a`: `Print::Server::SharedService::Uninstall`
- `0x18002cb51`: `Print::Server::SharedService::Uninstall`
- `0x18002cb4a`: `Service host group deleted.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void Print::Server::SharedService::Uninstall(void)
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbx
  signed int LastError; // eax
  bool v6; // sf
  const char *v7; // r9
  int Key; // eax
  bool v9; // sf
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r8
  const WCHAR *v12; // rdx
  int v13; // eax
  bool v14; // sf
  HKEY hKey[4]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+70h] [rbp-19h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+90h] [rbp+7h] BYREF
  __int128 v18; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v2 = v0;
  hKey[2] = (HKEY)v0;
  if ( !v0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x171,
      (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
      v1);
  v3 = OpenServiceW(v0, Print::Server::ServiceName, 0x10000000u);
  v4 = v3;
  hKey[3] = (HKEY)v3;
  if ( v3 )
  {
    if ( !DeleteService(v3) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17F,
        (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
        v7);
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Server::SharedService::Uninstall",
      L"Service deleted.");
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1060 )
    {
      v6 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = LastError < 0;
      }
      if ( v6 )
      {
        hr_error::hr_error((hr_error *)lpValueName, LastError);
        throw (hr_error *)lpValueName;
      }
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Print::Server::SharedService::Uninstall",
      L"Service did not exist but we were asked to uninstall.");
  }
  hKey[0] = 0;
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, Print::Server::ServiceHostKey, 0, 0, 0, 0xF003Fu, 0, hKey, 0);
  v9 = Key < 0;
  if ( Key )
  {
    if ( Key > 0 )
    {
      Key = (unsigned __int16)Key | 0x80070000;
      v9 = Key < 0;
    }
    if ( v9 )
    {
      hr_error::hr_error((hr_error *)lpValueName, Key);
      throw (hr_error *)lpValueName;
    }
  }
  *(_OWORD *)lpValueName = 0;
  v18 = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)&Print::Server::ServiceGroup + v11) );
  std::wstring::_Construct<1,unsigned short const *>((char **)lpValueName, &Print::Server::ServiceGroup, v11);
  v12 = (const WCHAR *)lpValueName;
  if ( *((_QWORD *)&v18 + 1) > 7u )
    v12 = lpValueName[0];
  v13 = RegDeleteValueW(hKey[0], v12);
  if ( (v13 & 0xFFFFFFFD) != 0 )
  {
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = v13 < 0;
    }
    if ( v14 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v13);
      throw (hr_error *)pExceptionObject;
    }
  }
  std::wstring::~wstring(lpValueName);
  *(_OWORD *)lpValueName = 0;
  v18 = 0;
  do
    ++v10;
  while ( *((_WORD *)&Print::Server::ServiceHostServiceGroupKey + v10) );
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)lpValueName,
    &Print::Server::ServiceHostServiceGroupKey,
    v10);
  Win32Adapters::Registry::RegDeleteKeyW(-2147483646, lpValueName);
  std::wstring::~wstring(lpValueName);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Uninstall",
    L"Service host group deleted.");
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  if ( v4 )
    CloseServiceHandle(v4);
  CloseServiceHandle(v2);
}

```

## disassembly

```asm
0x18002c97c  push    rbp
0x18002c97e  push    rbx
0x18002c97f  push    rsi
0x18002c980  push    rdi
0x18002c981  push    r14
0x18002c983  lea     rbp, [rsp-37h]
0x18002c988  sub     rsp, 0C0h
0x18002c98f  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18002c997  mov     rax, cs:__security_cookie
0x18002c99e  xor     rax, rsp
0x18002c9a1  mov     [rbp+57h+var_30], rax
0x18002c9a5  mov     esi, 0F003Fh
0x18002c9aa  mov     r8d, esi; dwDesiredAccess
0x18002c9ad  xor     edx, edx; lpDatabaseName
0x18002c9af  xor     ecx, ecx; lpMachineName
0x18002c9b1  call    cs:__imp_OpenSCManagerW
0x18002c9b7  mov     rdi, rax
0x18002c9ba  mov     [rbp+57h+var_80], rax
0x18002c9be  xor     r14d, r14d
0x18002c9c1  test    rax, rax
0x18002c9c4  jz      loc_18002CBBF
0x18002c9ca  mov     r8d, 10000000h; dwDesiredAccess
0x18002c9d0  lea     rdx, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002c9d7  mov     rcx, rax; hSCManager
0x18002c9da  call    cs:__imp_OpenServiceW
0x18002c9e0  mov     rbx, rax
0x18002c9e3  mov     [rbp+57h+var_78], rax
0x18002c9e7  test    rax, rax
0x18002c9ea  jnz     short loc_18002CA22
0x18002c9ec  call    cs:__imp_GetLastError
0x18002c9f2  cmp     eax, 424h
0x18002c9f7  jz      short loc_18002CA0D
0x18002c9f9  test    eax, eax
0x18002c9fb  jle     short loc_18002CA07
0x18002c9fd  movzx   eax, ax
0x18002ca00  or      eax, 80070000h
0x18002ca05  test    eax, eax
0x18002ca07  js      loc_18002CBD5
0x18002ca0d  lea     rdx, aServiceDidNotE; "Service did not exist but we were asked"...
0x18002ca14  lea     rcx, aPrintServerSha_4; "Print::Server::SharedService::Uninstall"
0x18002ca1b  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002ca20  jmp     short loc_18002CA46
0x18002ca22  mov     rcx, rbx; hService
0x18002ca25  call    cs:__imp_DeleteService
0x18002ca2b  test    eax, eax
0x18002ca2d  jz      loc_18002CBF1
0x18002ca33  lea     rdx, aServiceDeleted; "Service deleted."
0x18002ca3a  lea     rcx, aPrintServerSha_4; "Print::Server::SharedService::Uninstall"
0x18002ca41  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002ca46  mov     [rbp+57h+hKey], r14
0x18002ca4a  mov     [rsp+0E0h+lpdwDisposition], r14; lpdwDisposition
0x18002ca4f  lea     rax, [rbp+57h+hKey]
0x18002ca53  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002ca58  mov     [rsp+0E0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002ca5d  mov     [rsp+0E0h+samDesired], esi; samDesired
0x18002ca61  mov     [rsp+0E0h+dwOptions], r14d; dwOptions
0x18002ca66  xor     r9d, r9d; lpClass
0x18002ca69  xor     r8d, r8d; Reserved
0x18002ca6c  lea     rdx, ?ServiceHostKey@Server@Print@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002ca73  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ca7a  call    cs:__imp_RegCreateKeyExW
0x18002ca80  test    eax, eax
0x18002ca82  jz      short loc_18002CA96
0x18002ca84  jle     short loc_18002CA90
0x18002ca86  movzx   eax, ax
0x18002ca89  or      eax, 80070000h
0x18002ca8e  test    eax, eax
0x18002ca90  js      loc_18002CC07
0x18002ca96  xorps   xmm0, xmm0
0x18002ca99  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18002ca9d  xorps   xmm1, xmm1
0x18002caa0  movdqu  [rbp+57h+var_40], xmm1
0x18002caa5  lea     rdx, ?ServiceGroup@Server@Print@@3PAGA; "print"
0x18002caac  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002cab0  mov     r8, rsi
0x18002cab3  inc     r8
0x18002cab6  cmp     [rdx+r8*2], r14w
0x18002cabb  jnz     short loc_18002CAB3
0x18002cabd  lea     rcx, [rbp+57h+lpValueName]
0x18002cac1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cac6  nop
0x18002cac7  lea     rdx, [rbp+57h+lpValueName]
0x18002cacb  cmp     qword ptr [rbp+57h+var_40+8], 7
0x18002cad0  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x18002cad5  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cad9  call    cs:__imp_RegDeleteValueW
0x18002cadf  test    eax, 0FFFFFFFDh
0x18002cae4  jz      short loc_18002CAFA
0x18002cae6  test    eax, eax
0x18002cae8  jle     short loc_18002CAF4
0x18002caea  movzx   eax, ax
0x18002caed  or      eax, 80070000h
0x18002caf2  test    eax, eax
0x18002caf4  js      loc_18002CBA3
0x18002cafa  lea     rcx, [rbp+57h+lpValueName]
0x18002cafe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cb03  xorps   xmm0, xmm0
0x18002cb06  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18002cb0a  xorps   xmm1, xmm1
0x18002cb0d  movdqu  [rbp+57h+var_40], xmm1
0x18002cb12  lea     rdx, ?ServiceHostServiceGroupKey@Server@Print@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002cb19  inc     rsi
0x18002cb1c  cmp     [rdx+rsi*2], r14w
0x18002cb21  jnz     short loc_18002CB19
0x18002cb23  mov     r8, rsi
0x18002cb26  lea     rcx, [rbp+57h+lpValueName]
0x18002cb2a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cb2f  nop
0x18002cb30  lea     rdx, [rbp+57h+lpValueName]
0x18002cb34  mov     rcx, 0FFFFFFFF80000002h
0x18002cb3b  call    ?RegDeleteKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Registry::RegDeleteKeyW(HKEY__ *,std::wstring const &)
0x18002cb40  nop
0x18002cb41  lea     rcx, [rbp+57h+lpValueName]
0x18002cb45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cb4a  lea     rdx, aServiceHostGro_0; "Service host group deleted."
0x18002cb51  lea     rcx, aPrintServerSha_4; "Print::Server::SharedService::Uninstall"
0x18002cb58  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002cb5d  nop
0x18002cb5e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cb62  test    rcx, rcx
0x18002cb65  jz      short loc_18002CB71
0x18002cb67  call    cs:__imp_RegCloseKey
0x18002cb6d  mov     [rbp+57h+hKey], r14
0x18002cb71  test    rbx, rbx
0x18002cb74  jz      short loc_18002CB80
0x18002cb76  mov     rcx, rbx; hSCObject
0x18002cb79  call    cs:__imp_CloseServiceHandle
0x18002cb7f  nop
0x18002cb80  mov     rcx, rdi; hSCObject
0x18002cb83  call    cs:__imp_CloseServiceHandle
0x18002cb89  mov     rcx, [rbp+57h+var_30]
0x18002cb8d  xor     rcx, rsp; StackCookie
0x18002cb90  call    __security_check_cookie
0x18002cb95  add     rsp, 0C0h
0x18002cb9c  pop     r14
0x18002cb9e  pop     rdi
0x18002cb9f  pop     rsi
0x18002cba0  pop     rbx
0x18002cba1  pop     rbp
0x18002cba2  retn
0x18002cba3  mov     edx, eax; int
0x18002cba5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002cba9  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002cbae  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002cbb5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002cbb9  call    _CxxThrowException_0
0x18002cbbf  mov     rcx, [rbp+5Fh]; this
0x18002cbc3  lea     r8, aPrintscanPrint_18; "printscan\\print\\drivers\\usermode\\dr"...
0x18002cbca  mov     edx, 171h; void *
0x18002cbcf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002cbd5  mov     edx, eax; int
0x18002cbd7  lea     rcx, [rbp+57h+lpValueName]; this
0x18002cbdb  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002cbe0  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002cbe7  lea     rcx, [rbp+57h+lpValueName]; pExceptionObject
0x18002cbeb  call    _CxxThrowException_0
0x18002cbf1  mov     rcx, [rbp+5Fh]; this
0x18002cbf5  lea     r8, aPrintscanPrint_18; "printscan\\print\\drivers\\usermode\\dr"...
0x18002cbfc  mov     edx, 17Fh; void *
0x18002cc01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002cc07  mov     edx, eax; int
0x18002cc09  lea     rcx, [rbp+57h+lpValueName]; this
0x18002cc0d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002cc12  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002cc19  lea     rcx, [rbp+57h+lpValueName]; pExceptionObject
0x18002cc1d  call    _CxxThrowException_0
```
