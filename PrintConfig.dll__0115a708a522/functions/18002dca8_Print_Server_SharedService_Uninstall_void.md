# Print::Server::SharedService::Uninstall(void)

- ea: `0x18002dca8`
- end: `0x18002df86`
- name: `?Uninstall@SharedService@Server@Print@@SAXXZ`
- size: `734`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180032a10`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x18002dbc8`
- `0x18002dca8`
- `0x1800376d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002dd24`
- `KERNEL32!GetLastError` at `0x18002dd24`
- `ADVAPI32!RegCloseKey` at `0x18002deb7`
- `ADVAPI32!RegCloseKey` at `0x18002deb7`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ddbe`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ddbe`
- `ADVAPI32!CloseServiceHandle` at `0x18002decf`
- `ADVAPI32!CloseServiceHandle` at `0x18002dedf`
- `ADVAPI32!CloseServiceHandle` at `0x18002decf`
- `ADVAPI32!CloseServiceHandle` at `0x18002dedf`
- `ADVAPI32!OpenSCManagerW` at `0x18002dcdd`
- `ADVAPI32!OpenSCManagerW` at `0x18002dcdd`
- `ADVAPI32!OpenServiceW` at `0x18002dd0c`
- `ADVAPI32!OpenServiceW` at `0x18002dd0c`
- `ADVAPI32!DeleteService` at `0x18002dd63`
- `ADVAPI32!DeleteService` at `0x18002dd63`
- `ADVAPI32!RegDeleteValueW` at `0x18002de23`
- `ADVAPI32!RegDeleteValueW` at `0x18002de23`

## string_xrefs

- `0x18002df26`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002df58`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002dd4b`: `Service did not exist but we were asked to uninstall.`
- `0x18002dd77`: `Service deleted.`
- `0x18002dd52`: `Print::Server::SharedService::Uninstall`
- `0x18002dd7e`: `Print::Server::SharedService::Uninstall`
- `0x18002dea1`: `Print::Server::SharedService::Uninstall`
- `0x18002de9a`: `Service host group deleted.`

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
      (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
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
        (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
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
  std::wstring::_Construct<1,unsigned short const *>(lpValueName, &Print::Server::ServiceGroup, v11);
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
  std::wstring::~wstring((char **)lpValueName);
  *(_OWORD *)lpValueName = 0;
  v18 = 0;
  do
    ++v10;
  while ( *((_WORD *)&Print::Server::ServiceHostServiceGroupKey + v10) );
  std::wstring::_Construct<1,unsigned short const *>(lpValueName, &Print::Server::ServiceHostServiceGroupKey, v10);
  Win32Adapters::Registry::RegDeleteKeyW(HKEY_LOCAL_MACHINE, (const WCHAR *)lpValueName);
  std::wstring::~wstring((char **)lpValueName);
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
0x18002dca8  push    rbp
0x18002dcaa  push    rbx
0x18002dcab  push    rsi
0x18002dcac  push    rdi
0x18002dcad  push    r14
0x18002dcaf  lea     rbp, [rsp-37h]
0x18002dcb4  sub     rsp, 0C0h
0x18002dcbb  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18002dcc3  mov     rax, cs:__security_cookie
0x18002dcca  xor     rax, rsp
0x18002dccd  mov     [rbp+57h+var_30], rax
0x18002dcd1  mov     esi, 0F003Fh
0x18002dcd6  mov     r8d, esi; dwDesiredAccess
0x18002dcd9  xor     edx, edx; lpDatabaseName
0x18002dcdb  xor     ecx, ecx; lpMachineName
0x18002dcdd  call    cs:__imp_OpenSCManagerW
0x18002dce4  nop     dword ptr [rax+rax+00h]
0x18002dce9  mov     rdi, rax
0x18002dcec  mov     [rbp+57h+var_80], rax
0x18002dcf0  xor     r14d, r14d
0x18002dcf3  test    rax, rax
0x18002dcf6  jz      loc_18002DF22
0x18002dcfc  mov     r8d, 10000000h; dwDesiredAccess
0x18002dd02  lea     rdx, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002dd09  mov     rcx, rax; hSCManager
0x18002dd0c  call    cs:__imp_OpenServiceW
0x18002dd13  nop     dword ptr [rax+rax+00h]
0x18002dd18  mov     rbx, rax
0x18002dd1b  mov     [rbp+57h+var_78], rax
0x18002dd1f  test    rax, rax
0x18002dd22  jnz     short loc_18002DD60
0x18002dd24  call    cs:__imp_GetLastError
0x18002dd2b  nop     dword ptr [rax+rax+00h]
0x18002dd30  cmp     eax, 424h
0x18002dd35  jz      short loc_18002DD4B
0x18002dd37  test    eax, eax
0x18002dd39  jle     short loc_18002DD45
0x18002dd3b  movzx   eax, ax
0x18002dd3e  or      eax, 80070000h
0x18002dd43  test    eax, eax
0x18002dd45  js      loc_18002DF38
0x18002dd4b  lea     rdx, aServiceDidNotE; "Service did not exist but we were asked"...
0x18002dd52  lea     rcx, aPrintServerSha_4; "Print::Server::SharedService::Uninstall"
0x18002dd59  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002dd5e  jmp     short loc_18002DD8A
0x18002dd60  mov     rcx, rbx; hService
0x18002dd63  call    cs:__imp_DeleteService
0x18002dd6a  nop     dword ptr [rax+rax+00h]
0x18002dd6f  test    eax, eax
0x18002dd71  jz      loc_18002DF54
0x18002dd77  lea     rdx, aServiceDeleted; "Service deleted."
0x18002dd7e  lea     rcx, aPrintServerSha_4; "Print::Server::SharedService::Uninstall"
0x18002dd85  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002dd8a  mov     [rbp+57h+hKey], r14
0x18002dd8e  mov     [rsp+0E0h+lpdwDisposition], r14; lpdwDisposition
0x18002dd93  lea     rax, [rbp+57h+hKey]
0x18002dd97  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002dd9c  mov     [rsp+0E0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002dda1  mov     [rsp+0E0h+samDesired], esi; samDesired
0x18002dda5  mov     [rsp+0E0h+dwOptions], r14d; dwOptions
0x18002ddaa  xor     r9d, r9d; lpClass
0x18002ddad  xor     r8d, r8d; Reserved
0x18002ddb0  lea     rdx, ?ServiceHostKey@Server@Print@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002ddb7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ddbe  call    cs:__imp_RegCreateKeyExW
0x18002ddc5  nop     dword ptr [rax+rax+00h]
0x18002ddca  test    eax, eax
0x18002ddcc  jz      short loc_18002DDE0
0x18002ddce  jle     short loc_18002DDDA
0x18002ddd0  movzx   eax, ax
0x18002ddd3  or      eax, 80070000h
0x18002ddd8  test    eax, eax
0x18002ddda  js      loc_18002DF6A
0x18002dde0  xorps   xmm0, xmm0
0x18002dde3  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18002dde7  xorps   xmm1, xmm1
0x18002ddea  movdqu  [rbp+57h+var_40], xmm1
0x18002ddef  lea     rdx, ?ServiceGroup@Server@Print@@3PAGA; "print"
0x18002ddf6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ddfa  mov     r8, rsi
0x18002ddfd  inc     r8
0x18002de00  cmp     [rdx+r8*2], r14w
0x18002de05  jnz     short loc_18002DDFD
0x18002de07  lea     rcx, [rbp+57h+lpValueName]
0x18002de0b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002de10  nop
0x18002de11  lea     rdx, [rbp+57h+lpValueName]
0x18002de15  cmp     qword ptr [rbp+57h+var_40+8], 7
0x18002de1a  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x18002de1f  mov     rcx, [rbp+57h+hKey]; hKey
0x18002de23  call    cs:__imp_RegDeleteValueW
0x18002de2a  nop     dword ptr [rax+rax+00h]
0x18002de2f  test    eax, 0FFFFFFFDh
0x18002de34  jz      short loc_18002DE4A
0x18002de36  test    eax, eax
0x18002de38  jle     short loc_18002DE44
0x18002de3a  movzx   eax, ax
0x18002de3d  or      eax, 80070000h
0x18002de42  test    eax, eax
0x18002de44  js      loc_18002DF06
0x18002de4a  lea     rcx, [rbp+57h+lpValueName]
0x18002de4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002de53  xorps   xmm0, xmm0
0x18002de56  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18002de5a  xorps   xmm1, xmm1
0x18002de5d  movdqu  [rbp+57h+var_40], xmm1
0x18002de62  lea     rdx, ?ServiceHostServiceGroupKey@Server@Print@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002de69  inc     rsi
0x18002de6c  cmp     [rdx+rsi*2], r14w
0x18002de71  jnz     short loc_18002DE69
0x18002de73  mov     r8, rsi
0x18002de76  lea     rcx, [rbp+57h+lpValueName]
0x18002de7a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002de7f  nop
0x18002de80  lea     rdx, [rbp+57h+lpValueName]
0x18002de84  mov     rcx, 0FFFFFFFF80000002h
0x18002de8b  call    ?RegDeleteKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Registry::RegDeleteKeyW(HKEY__ *,std::wstring const &)
0x18002de90  nop
0x18002de91  lea     rcx, [rbp+57h+lpValueName]
0x18002de95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002de9a  lea     rdx, aServiceHostGro_0; "Service host group deleted."
0x18002dea1  lea     rcx, aPrintServerSha_4; "Print::Server::SharedService::Uninstall"
0x18002dea8  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002dead  nop
0x18002deae  mov     rcx, [rbp+57h+hKey]; hKey
0x18002deb2  test    rcx, rcx
0x18002deb5  jz      short loc_18002DEC7
0x18002deb7  call    cs:__imp_RegCloseKey
0x18002debe  nop     dword ptr [rax+rax+00h]
0x18002dec3  mov     [rbp+57h+hKey], r14
0x18002dec7  test    rbx, rbx
0x18002deca  jz      short loc_18002DEDC
0x18002decc  mov     rcx, rbx; hSCObject
0x18002decf  call    cs:__imp_CloseServiceHandle
0x18002ded6  nop     dword ptr [rax+rax+00h]
0x18002dedb  nop
0x18002dedc  mov     rcx, rdi; hSCObject
0x18002dedf  call    cs:__imp_CloseServiceHandle
0x18002dee6  nop     dword ptr [rax+rax+00h]
0x18002deeb  mov     rcx, [rbp+57h+var_30]
0x18002deef  xor     rcx, rsp; StackCookie
0x18002def2  call    __security_check_cookie
0x18002def7  add     rsp, 0C0h
0x18002defe  pop     r14
0x18002df00  pop     rdi
0x18002df01  pop     rsi
0x18002df02  pop     rbx
0x18002df03  pop     rbp
0x18002df04  retn
0x18002df06  mov     edx, eax; int
0x18002df08  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002df0c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002df11  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002df18  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002df1c  call    _CxxThrowException_0
0x18002df22  mov     rcx, [rbp+5Fh]; this
0x18002df26  lea     r8, aPrintscanPrint_18; "printscan\\print\\drivers\\usermode\\dr"...
0x18002df2d  mov     edx, 171h; void *
0x18002df32  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002df38  mov     edx, eax; int
0x18002df3a  lea     rcx, [rbp+57h+lpValueName]; this
0x18002df3e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002df43  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002df4a  lea     rcx, [rbp+57h+lpValueName]; pExceptionObject
0x18002df4e  call    _CxxThrowException_0
0x18002df54  mov     rcx, [rbp+5Fh]; this
0x18002df58  lea     r8, aPrintscanPrint_18; "printscan\\print\\drivers\\usermode\\dr"...
0x18002df5f  mov     edx, 17Fh; void *
0x18002df64  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002df6a  mov     edx, eax; int
0x18002df6c  lea     rcx, [rbp+57h+lpValueName]; this
0x18002df70  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002df75  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002df7c  lea     rcx, [rbp+57h+lpValueName]; pExceptionObject
0x18002df80  call    _CxxThrowException_0
```
