# Print::Server::SharedService::Install(void)

- ea: `0x18002b010`
- end: `0x18002b89a`
- name: `?Install@SharedService@Server@Print@@SAXXZ`
- size: `2186`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800327e0`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180019ee8`
- `0x180019ff0`
- `0x18001db74`
- `0x180020cbc`
- `0x180021098`
- `0x18002174c`
- `0x180022344`
- `0x18002278c`
- `0x180024ea8`
- `0x1800260b4`
- `0x180027b74`
- `0x18002ac20`
- `0x18002b010`
- `0x18002dbc8`
- `0x18002e55c`
- `0x180037588`
- `0x180037f00`
- `0x18003803c`
- `0x1800380f4`
- `0x1801b56c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b28d`
- `KERNEL32!GetLastError` at `0x18002b28d`
- `ADVAPI32!RegCloseKey` at `0x18002b76a`
- `ADVAPI32!RegCloseKey` at `0x18002b78f`
- `ADVAPI32!RegCloseKey` at `0x18002b7a9`
- `ADVAPI32!RegCloseKey` at `0x18002b76a`
- `ADVAPI32!RegCloseKey` at `0x18002b78f`
- `ADVAPI32!RegCloseKey` at `0x18002b7a9`
- `ADVAPI32!CloseServiceHandle` at `0x18002b7c1`
- `ADVAPI32!CloseServiceHandle` at `0x18002b816`
- `ADVAPI32!CloseServiceHandle` at `0x18002b7c1`
- `ADVAPI32!CloseServiceHandle` at `0x18002b816`
- `ADVAPI32!OpenSCManagerW` at `0x18002b068`
- `ADVAPI32!OpenSCManagerW` at `0x18002b068`
- `ADVAPI32!CreateServiceW` at `0x18002b275`
- `ADVAPI32!CreateServiceW` at `0x18002b275`
- `ADVAPI32!ChangeServiceConfig2W` at `0x18002b2e3`
- `ADVAPI32!ChangeServiceConfig2W` at `0x18002b2e3`

## string_xrefs

- `0x18002b84d`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002b888`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002b04f`: `Print::Server::SharedService::Install`
- `0x18002b2a0`: `Service already installed`
- `0x18002b1ff`: `Installing Service - Name: %ws, BinPath: %ws`
- `0x18002b386`: `ServiceDll`
- `0x18002b2f7`: `Service created.`
- `0x18002b47d`: `Service entry registered %ws,%ws.`
- `0x18002b418`: `ServiceMain`
- `0x18002b5e9`: `Service host group created print`
- `0x18002b663`: `CoInitializeSecurityParam`
- `0x18002b718`: `ImpersonationLevel`
- `0x18002b6ee`: `Service host registered with ImpersonationLevel of RPC_C_IMP_LEVEL_IDENTIFY`
- `0x18002b750`: `Service host group settings complete.`
- `0x18002b3d9`: `ServiceMain`
- `0x18002b31f`: `SYSTEM\CurrentControlSet\Services\PrintNotify\Parameters`
- `0x18002b1ee`: `%SystemRoot%\system32\svchost.exe -k print`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void Print::Server::SharedService::Install(void)
{
  SC_HANDLE v0; // rbx
  const char *v1; // r9
  __int64 v2; // rax
  __int128 *v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // r8
  WCHAR *v7; // rdx
  __int64 v8; // rax
  __int128 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  const WCHAR *v13; // r8
  SC_HANDLE ServiceW; // rdi
  signed int LastError; // eax
  bool v16; // sf
  char **v17; // rax
  const char *v18; // r9
  unsigned __int64 v19; // r14
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r8
  __int128 *v22; // r8
  unsigned __int64 v23; // r8
  char *v24; // rsi
  unsigned __int64 v25; // r8
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v27; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  char **Info; // [rsp+88h] [rbp-78h] BYREF
  void *v30[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  SC_HANDLE v33; // [rsp+B0h] [rbp-50h]
  SC_HANDLE v34; // [rsp+B8h] [rbp-48h]
  _BYTE v35[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v37[112]; // [rsp+D8h] [rbp-28h] BYREF
  int v38; // [rsp+148h] [rbp+48h]
  _QWORD v39[13]; // [rsp+158h] [rbp+58h] BYREF
  __int128 pExceptionObject; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v41; // [rsp+1D0h] [rbp+D0h]
  WCHAR SubKey[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v43; // [rsp+1F0h] [rbp+F0h]
  __int128 v44; // [rsp+200h] [rbp+100h] BYREF
  __m128i si128; // [rsp+210h] [rbp+110h]
  char *v46[4]; // [rsp+220h] [rbp+120h] BYREF
  LPCWSTR lpDisplayName[4]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v32 = -2;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo("Print::Server::SharedService::Install", L"Enter");
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v33 = v0;
  if ( !v0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF2,
      (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
      v1);
  v44 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v44) = 0;
  Print::Server::SharedService::GetExecutingModulePath((__int64)&v44);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v35);
  v2 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v36, (__int64)L"@");
  v3 = &v44;
  if ( si128.m128i_i64[1] > 7uLL )
    v3 = (__int128 *)v44;
  v4 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
         v2,
         (__int64)v3,
         si128.m128i_u64[0]);
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v4, (__int64)L",-");
  std::basic_ostream<unsigned short>::operator<<(v5);
  std::basic_stringbuf<unsigned short>::str((__int64)v37, (__int64)lpDisplayName, v6);
  *(_OWORD *)SubKey = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(SubKey, &Filename, 0);
  std::basic_stringbuf<unsigned short>::_Tidy((__int64)v37);
  v7 = SubKey;
  if ( *((_QWORD *)&v43 + 1) > 7u )
    v7 = *(WCHAR **)SubKey;
  std::basic_stringbuf<unsigned short>::_Init((__int64)v37, v7, v43, v38);
  std::wstring::~wstring((char **)SubKey);
  v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v36, (__int64)L"@");
  v9 = &v44;
  if ( si128.m128i_i64[1] > 7uLL )
    v9 = (__int128 *)v44;
  v10 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
          v8,
          (__int64)v9,
          si128.m128i_u64[0]);
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, (__int64)L",-");
  std::basic_ostream<unsigned short>::operator<<(v11);
  std::basic_stringbuf<unsigned short>::str((__int64)v37, (__int64)v46, v12);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Installing Service - Name: %ws, BinPath: %ws",
    Print::Server::ServiceName,
    Print::Server::ServiceBinaryPath);
  v13 = (const WCHAR *)lpDisplayName;
  if ( lpDisplayName[3] > (LPCWSTR)7 )
    v13 = lpDisplayName[0];
  ServiceW = CreateServiceW(
               v0,
               Print::Server::ServiceName,
               v13,
               0x10000000u,
               0x120u,
               3u,
               1u,
               Print::Server::ServiceBinaryPath,
               0,
               0,
               Print::Server::ServiceDependencies,
               Print::Server::ServiceAccount,
               0);
  v34 = ServiceW;
  if ( ServiceW )
  {
    v17 = v46;
    if ( v46[3] > (char *)7 )
      v17 = (char **)v46[0];
    Info = v17;
    if ( !ChangeServiceConfig2W(ServiceW, 1u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x121,
        (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
        v18);
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Server::SharedService::Install",
      L"Service created.");
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 1073 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Server::SharedService::Install",
        L"Service already installed");
    }
    else
    {
      v16 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError < 0;
      }
      if ( v16 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, LastError);
        throw (hr_error *)&pExceptionObject;
      }
    }
  }
  phkResult = 0;
  *(_OWORD *)SubKey = 0;
  v43 = 0;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( *((_WORD *)&Print::Server::ServiceParametersKey + v20) );
  std::wstring::_Construct<1,unsigned short const *>(SubKey, &Print::Server::ServiceParametersKey, v20);
  Win32Adapters::Registry::RegCreateKeyW(HKEY_LOCAL_MACHINE, SubKey, &phkResult);
  std::wstring::~wstring((char **)SubKey);
  *(_OWORD *)SubKey = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(SubKey, L"ServiceDll", 0xAu);
  Win32Adapters::Registry::RegSetValueW(&phkResult, SubKey, (__int64 *)&v44, 2u);
  std::wstring::~wstring((char **)SubKey);
  pExceptionObject = 0;
  v41 = 0;
  v21 = -1;
  do
    ++v21;
  while ( *((_WORD *)&Print::Server::ServiceExportFunction + v21) );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, &Print::Server::ServiceExportFunction, v21);
  *(_OWORD *)SubKey = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(SubKey, L"ServiceMain", 0xBu);
  Win32Adapters::Registry::RegSetValueW(&phkResult, SubKey, (__int64 *)&pExceptionObject, 1u);
  std::wstring::~wstring((char **)SubKey);
  std::wstring::~wstring((char **)&pExceptionObject);
  v22 = &v44;
  if ( si128.m128i_i64[1] > 7uLL )
    v22 = (__int128 *)v44;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service entry registered %ws,%ws.",
    v22,
    &Print::Server::ServiceExportFunction);
  v27 = 0;
  pExceptionObject = 0;
  v41 = 0;
  v23 = -1;
  do
    ++v23;
  while ( Print::Server::ServiceHostKey[v23] );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, Print::Server::ServiceHostKey, v23);
  Win32Adapters::Registry::RegCreateKeyW(HKEY_LOCAL_MACHINE, (const WCHAR *)&pExceptionObject, &v27);
  std::wstring::~wstring((char **)&pExceptionObject);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  std::vector<unsigned short>::_Buy_nonzero(v30, 0xDu);
  v24 = (char *)v30[0];
  memmove_0(v30[0], &Print::Server::ServiceGroupMembers, 0x1Au);
  v30[1] = v24 + 26;
  Info = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&Info);
  pExceptionObject = 0;
  v41 = 0;
  v25 = -1;
  do
    ++v25;
  while ( *((_WORD *)&Print::Server::ServiceGroup + v25) );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, &Print::Server::ServiceGroup, v25);
  Win32Adapters::Registry::RegSetValueW(&v27, (const WCHAR *)&pExceptionObject, (__int64)v30);
  std::wstring::~wstring((char **)&pExceptionObject);
  hKey = 0;
  pExceptionObject = 0;
  v41 = 0;
  do
    ++v19;
  while ( *((_WORD *)&Print::Server::ServiceGroup + v19) );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, &Print::Server::ServiceGroup, v19);
  Win32Adapters::Registry::RegCreateKeyW(v27, (const WCHAR *)&pExceptionObject, &hKey);
  std::wstring::~wstring((char **)&pExceptionObject);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service host group created print");
  pExceptionObject = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"AuthenticationCapabilities", 0x1Au);
  Win32Adapters::Registry::RegSetValueW(&hKey, (const WCHAR *)&pExceptionObject, 12320);
  std::wstring::~wstring((char **)&pExceptionObject);
  pExceptionObject = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"CoInitializeSecurityParam", 0x19u);
  Win32Adapters::Registry::RegSetValueW(&hKey, (const WCHAR *)&pExceptionObject, 1);
  std::wstring::~wstring((char **)&pExceptionObject);
  pExceptionObject = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"AuthenticationLevel", 0x13u);
  Win32Adapters::Registry::RegSetValueW(&hKey, (const WCHAR *)&pExceptionObject, 5);
  std::wstring::~wstring((char **)&pExceptionObject);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service host registered with ImpersonationLevel of RPC_C_IMP_LEVEL_IDENTIFY");
  pExceptionObject = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"ImpersonationLevel", 0x12u);
  Win32Adapters::Registry::RegSetValueW(&hKey, (const WCHAR *)&pExceptionObject, 2);
  std::wstring::~wstring((char **)&pExceptionObject);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service host group settings complete.");
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  if ( v27 )
  {
    RegCloseKey(v27);
    v27 = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( ServiceW )
    CloseServiceHandle(ServiceW);
  std::wstring::~wstring(v46);
  std::wstring::~wstring((char **)lpDisplayName);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v39);
  v39[0] = &std::basic_ios<unsigned short>::`vftable';
  std::ios_base::~ios_base((std::ios_base *)v39);
  std::wstring::~wstring((char **)&v44);
  CloseServiceHandle(v0);
}

```

## disassembly

```asm
0x18002b010  push    rbp
0x18002b012  push    rbx
0x18002b013  push    rsi
0x18002b014  push    rdi
0x18002b015  push    r12
0x18002b017  push    r13
0x18002b019  push    r14
0x18002b01b  push    r15
0x18002b01d  lea     rbp, [rsp-178h]
0x18002b025  sub     rsp, 278h
0x18002b02c  mov     [rbp+1B0h+var_208], 0FFFFFFFFFFFFFFFEh
0x18002b034  mov     rax, cs:__security_cookie
0x18002b03b  xor     rax, rsp
0x18002b03e  mov     [rbp+1B0h+var_50], rax
0x18002b045  xor     r15d, r15d
0x18002b048  lea     rdx, aEnter_0; "Enter"
0x18002b04f  lea     r12, aPrintServerSha_6; "Print::Server::SharedService::Install"
0x18002b056  mov     rcx, r12; char *
0x18002b059  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b05e  xor     edx, edx; lpDatabaseName
0x18002b060  xor     ecx, ecx; lpMachineName
0x18002b062  mov     r8d, 0F003Fh; dwDesiredAccess
0x18002b068  call    cs:__imp_OpenSCManagerW
0x18002b06f  nop     dword ptr [rax+rax+00h]
0x18002b074  mov     rbx, rax
0x18002b077  mov     [rbp+1B0h+var_200], rax
0x18002b07b  test    rax, rax
0x18002b07e  jz      loc_18002B881
0x18002b084  xorps   xmm0, xmm0
0x18002b087  movups  [rbp+1B0h+var_B0], xmm0
0x18002b08e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002b096  movdqu  [rbp+1B0h+var_A0], xmm1
0x18002b09e  mov     word ptr [rbp+1B0h+var_B0], r15w
0x18002b0a6  lea     rcx, [rbp+1B0h+var_B0]
0x18002b0ad  call    ?GetExecutingModulePath@SharedService@Server@Print@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Server::SharedService::GetExecutingModulePath(std::wstring &)
0x18002b0b2  lea     rcx, [rbp+1B0h+var_1F0]
0x18002b0b6  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18002b0bb  nop
0x18002b0bc  lea     rdx, asc_1801EA3C8; "@"
0x18002b0c3  lea     rcx, [rbp+1B0h+var_1E0]
0x18002b0c7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002b0cc  lea     rdx, [rbp+1B0h+var_B0]
0x18002b0d3  cmp     qword ptr [rbp+1B0h+var_A0+8], 7
0x18002b0db  cmova   rdx, qword ptr [rbp+1B0h+var_B0]
0x18002b0e3  mov     r8, qword ptr [rbp+1B0h+var_A0]
0x18002b0ea  mov     rcx, rax
0x18002b0ed  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002b0f2  lea     rdx, asc_1801EA3CC; ",-"
0x18002b0f9  mov     rcx, rax
0x18002b0fc  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002b101  lea     esi, [r15+1]
0x18002b105  mov     edx, esi
0x18002b107  mov     rcx, rax
0x18002b10a  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18002b10f  lea     rdx, [rbp+1B0h+lpDisplayName]
0x18002b116  lea     rcx, [rbp+1B0h+var_1D8]
0x18002b11a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002b11f  nop
0x18002b120  xorps   xmm0, xmm0
0x18002b123  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002b12a  xorps   xmm1, xmm1
0x18002b12d  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002b135  xor     r8d, r8d
0x18002b138  lea     rdx, Filename
0x18002b13f  lea     rcx, [rbp+1B0h+SubKey]
0x18002b146  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b14b  nop
0x18002b14c  lea     rcx, [rbp+1B0h+var_1D8]
0x18002b150  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18002b155  lea     rdx, [rbp+1B0h+SubKey]
0x18002b15c  cmp     qword ptr [rbp+1B0h+var_C0+8], 7
0x18002b164  cmova   rdx, qword ptr [rbp+1B0h+SubKey]
0x18002b16c  mov     r9d, [rbp+1B0h+var_168]
0x18002b170  mov     r8, qword ptr [rbp+1B0h+var_C0]
0x18002b177  lea     rcx, [rbp+1B0h+var_1D8]
0x18002b17b  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18002b180  nop
0x18002b181  lea     rcx, [rbp+1B0h+SubKey]
0x18002b188  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b18d  lea     rdx, asc_1801EA3C8; "@"
0x18002b194  lea     rcx, [rbp+1B0h+var_1E0]
0x18002b198  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002b19d  lea     rdx, [rbp+1B0h+var_B0]
0x18002b1a4  cmp     qword ptr [rbp+1B0h+var_A0+8], 7
0x18002b1ac  cmova   rdx, qword ptr [rbp+1B0h+var_B0]
0x18002b1b4  mov     r8, qword ptr [rbp+1B0h+var_A0]
0x18002b1bb  mov     rcx, rax
0x18002b1be  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002b1c3  lea     rdx, asc_1801EA3CC; ",-"
0x18002b1ca  mov     rcx, rax
0x18002b1cd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002b1d2  lea     edx, [rsi+1]
0x18002b1d5  mov     rcx, rax
0x18002b1d8  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18002b1dd  lea     rdx, [rbp+1B0h+var_90]
0x18002b1e4  lea     rcx, [rbp+1B0h+var_1D8]
0x18002b1e8  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002b1ed  nop
0x18002b1ee  lea     rdi, ?ServiceBinaryPath@Server@Print@@3PAGA; "%SystemRoot%\\system32\\svchost.exe -k "...
0x18002b1f5  mov     r9, rdi
0x18002b1f8  lea     r8, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002b1ff  lea     rdx, aInstallingServ; "Installing Service - Name: %ws, BinPath"...
0x18002b206  mov     rcx, r12; char *
0x18002b209  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b20e  lea     r8, [rbp+1B0h+lpDisplayName]
0x18002b215  cmp     [rbp+1B0h+var_58], 7
0x18002b21d  cmova   r8, [rbp+1B0h+lpDisplayName]; lpDisplayName
0x18002b225  mov     [rsp+2B0h+lpPassword], r15; lpPassword
0x18002b22a  lea     rax, ?ServiceAccount@Server@Print@@3PAGA; "LocalSystem"
0x18002b231  mov     [rsp+2B0h+lpServiceStartName], rax; lpServiceStartName
0x18002b236  lea     rax, ?ServiceDependencies@Server@Print@@3PAGA; "RpcSs"
0x18002b23d  mov     [rsp+2B0h+lpDependencies], rax; lpDependencies
0x18002b242  mov     [rsp+2B0h+lpdwTagId], r15; lpdwTagId
0x18002b247  mov     [rsp+2B0h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x18002b24c  mov     [rsp+2B0h+lpBinaryPathName], rdi; lpBinaryPathName
0x18002b251  mov     dword ptr [rsp+2B0h+dwErrorControl], esi; dwErrorControl
0x18002b255  mov     dword ptr [rsp+2B0h+dwStartType], 3; dwStartType
0x18002b25d  mov     dword ptr [rsp+2B0h+dwServiceType], 120h; dwServiceType
0x18002b265  mov     r9d, 10000000h; dwDesiredAccess
0x18002b26b  lea     rdx, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002b272  mov     rcx, rbx; hSCManager
0x18002b275  call    cs:__imp_CreateServiceW
0x18002b27c  nop     dword ptr [rax+rax+00h]
0x18002b281  mov     rdi, rax
0x18002b284  mov     [rbp+1B0h+var_1F8], rax
0x18002b288  test    rax, rax
0x18002b28b  jnz     short loc_18002B2BF
0x18002b28d  call    cs:__imp_GetLastError
0x18002b294  nop     dword ptr [rax+rax+00h]
0x18002b299  cmp     eax, 431h
0x18002b29e  jnz     short loc_18002B2A9
0x18002b2a0  lea     rdx, aServiceAlready; "Service already installed"
0x18002b2a7  jmp     short loc_18002B2FE
0x18002b2a9  test    eax, eax
0x18002b2ab  jle     short loc_18002B2B7
0x18002b2ad  movzx   eax, ax
0x18002b2b0  or      eax, 80070000h
0x18002b2b5  test    eax, eax
0x18002b2b7  js      loc_18002B85F
0x18002b2bd  jmp     short loc_18002B306
0x18002b2bf  lea     rax, [rbp+1B0h+var_90]
0x18002b2c6  cmp     [rbp+1B0h+var_78], 7
0x18002b2ce  cmova   rax, [rbp+1B0h+var_90]
0x18002b2d6  mov     [rbp+1B0h+Info], rax
0x18002b2da  lea     r8, [rbp+1B0h+Info]; lpInfo
0x18002b2de  mov     edx, esi; dwInfoLevel
0x18002b2e0  mov     rcx, rdi; hService
0x18002b2e3  call    cs:__imp_ChangeServiceConfig2W
0x18002b2ea  nop     dword ptr [rax+rax+00h]
0x18002b2ef  test    eax, eax
0x18002b2f1  jz      loc_18002B846
0x18002b2f7  lea     rdx, aServiceCreated; "Service created."
0x18002b2fe  mov     rcx, r12; char *
0x18002b301  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b306  mov     [rbp+1B0h+phkResult], r15
0x18002b30a  xorps   xmm0, xmm0
0x18002b30d  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002b314  xorps   xmm1, xmm1
0x18002b317  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002b31f  lea     rdx, ?ServiceParametersKey@Server@Print@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Pr"...
0x18002b326  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002b32a  mov     r8, r14
0x18002b32d  inc     r8
0x18002b330  cmp     [rdx+r8*2], r15w
0x18002b335  jnz     short loc_18002B32D
0x18002b337  lea     rcx, [rbp+1B0h+SubKey]
0x18002b33e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b343  nop
0x18002b344  lea     r8, [rbp+1B0h+phkResult]; phkResult
0x18002b348  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18002b34f  mov     r13, 0FFFFFFFF80000002h
0x18002b356  mov     rcx, r13; hKey
0x18002b359  call    ?RegCreateKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegCreateKeyW(HKEY__ *,std::wstring const &,RegistryHandleRAII &)
0x18002b35e  nop
0x18002b35f  lea     rcx, [rbp+1B0h+SubKey]
0x18002b366  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b36b  xorps   xmm0, xmm0
0x18002b36e  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002b375  xorps   xmm1, xmm1
0x18002b378  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002b380  mov     r8d, 0Ah
0x18002b386  lea     rdx, aServicedll; "ServiceDll"
0x18002b38d  lea     rcx, [rbp+1B0h+SubKey]
0x18002b394  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b399  nop
0x18002b39a  mov     r9d, 2
0x18002b3a0  lea     r8, [rbp+1B0h+var_B0]
0x18002b3a7  lea     rdx, [rbp+1B0h+SubKey]
0x18002b3ae  lea     rcx, [rbp+1B0h+phkResult]
0x18002b3b2  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::wstring const &,ulong)
0x18002b3b7  nop
0x18002b3b8  lea     rcx, [rbp+1B0h+SubKey]
0x18002b3bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b3c4  xorps   xmm0, xmm0
0x18002b3c7  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002b3ce  xorps   xmm1, xmm1
0x18002b3d1  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002b3d9  lea     rsi, ?ServiceExportFunction@Server@Print@@3PAGA; "ServiceMain"
0x18002b3e0  mov     r8, r14
0x18002b3e3  inc     r8
0x18002b3e6  cmp     [rsi+r8*2], r15w
0x18002b3eb  jnz     short loc_18002B3E3
0x18002b3ed  mov     rdx, rsi
0x18002b3f0  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002b3f7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b3fc  nop
0x18002b3fd  xorps   xmm0, xmm0
0x18002b400  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002b407  xorps   xmm1, xmm1
0x18002b40a  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002b412  mov     r8d, 0Bh
0x18002b418  lea     rdx, aServicemain_1; "ServiceMain"
0x18002b41f  lea     rcx, [rbp+1B0h+SubKey]
0x18002b426  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b42b  nop
0x18002b42c  mov     r9d, 1
0x18002b432  lea     r8, [rbp+1B0h+pExceptionObject]
0x18002b439  lea     rdx, [rbp+1B0h+SubKey]
0x18002b440  lea     rcx, [rbp+1B0h+phkResult]
0x18002b444  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::wstring const &,ulong)
0x18002b449  nop
0x18002b44a  lea     rcx, [rbp+1B0h+SubKey]
0x18002b451  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b456  nop
0x18002b457  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002b45e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b463  lea     r8, [rbp+1B0h+var_B0]
0x18002b46a  cmp     qword ptr [rbp+1B0h+var_A0+8], 7
0x18002b472  cmova   r8, qword ptr [rbp+1B0h+var_B0]
0x18002b47a  mov     r9, rsi
0x18002b47d  lea     rdx, aServiceEntryRe; "Service entry registered %ws,%ws."
0x18002b484  mov     rcx, r12; char *
0x18002b487  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b48c  mov     [rsp+2B0h+var_238], r15
0x18002b491  xorps   xmm0, xmm0
0x18002b494  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002b49b  xorps   xmm1, xmm1
0x18002b49e  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002b4a6  lea     rdx, ?ServiceHostKey@Server@Print@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b4ad  mov     r8, r14
0x18002b4b0  inc     r8
0x18002b4b3  cmp     [rdx+r8*2], r15w
0x18002b4b8  jnz     short loc_18002B4B0
0x18002b4ba  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002b4c1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b4c6  nop
0x18002b4c7  lea     r8, [rsp+2B0h+var_238]; phkResult
0x18002b4cc  lea     rdx, [rbp+1B0h+pExceptionObject]; lpSubKey
0x18002b4d3  mov     rcx, r13; hKey
0x18002b4d6  call    ?RegCreateKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegCreateKeyW(HKEY__ *,std::wstring const &,RegistryHandleRAII &)
0x18002b4db  nop
0x18002b4dc  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002b4e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b4e8  xorps   xmm0, xmm0
0x18002b4eb  movdqu  xmmword ptr [rbp+1B0h+var_220], xmm0
0x18002b4f0  mov     [rbp+1B0h+var_210], r15
0x18002b4f4  mov     edx, 0Dh
0x18002b4f9  lea     rcx, [rbp+1B0h+var_220]
0x18002b4fd  call    ?_Buy_nonzero@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Buy_nonzero(unsigned __int64)
0x18002b502  mov     rsi, [rbp+1B0h+var_220]
0x18002b506  mov     r13d, 1Ah
0x18002b50c  mov     r8d, r13d; Size
0x18002b50f  lea     rdx, ?ServiceGroupMembers@Server@Print@@3PAGA; "PrintNotify"
0x18002b516  mov     rcx, rsi; void *
0x18002b519  call    memmove_0
0x18002b51e  lea     rax, [rsi+1Ah]
0x18002b522  mov     [rbp+1B0h+var_220+8], rax
0x18002b526  mov     [rbp+1B0h+Info], r15
0x18002b52a  lea     rcx, [rbp+1B0h+Info]
0x18002b52e  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x18002b533  nop
0x18002b534  xorps   xmm0, xmm0
0x18002b537  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002b53e  xorps   xmm1, xmm1
0x18002b541  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002b549  lea     rsi, ?ServiceGroup@Server@Print@@3PAGA; "print"
0x18002b550  mov     r8, r14
0x18002b553  inc     r8
0x18002b556  cmp     [rsi+r8*2], r15w
0x18002b55b  jnz     short loc_18002B553
0x18002b55d  mov     rdx, rsi
0x18002b560  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002b567  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b56c  nop
0x18002b56d  lea     r8, [rbp+1B0h+var_220]
0x18002b571  lea     rdx, [rbp+1B0h+pExceptionObject]
0x18002b578  lea     rcx, [rsp+2B0h+var_238]
0x18002b57d  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@GV?$allocator@G@std@@@5@K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::vector<ushort> const &,ulong)
0x18002b582  nop
0x18002b583  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002b58a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b58f  mov     [rsp+2B0h+hKey], r15
0x18002b594  xorps   xmm0, xmm0
0x18002b597  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002b59e  xorps   xmm1, xmm1
0x18002b5a1  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002b5a9  inc     r14
0x18002b5ac  cmp     [rsi+r14*2], r15w
0x18002b5b1  jnz     short loc_18002B5A9
0x18002b5b3  mov     r8, r14
  ... truncated ...
```
