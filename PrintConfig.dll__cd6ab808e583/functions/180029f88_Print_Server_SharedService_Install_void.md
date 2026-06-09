# Print::Server::SharedService::Install(void)

- ea: `0x180029f88`
- end: `0x18002a7db`
- name: `?Install@SharedService@Server@Print@@SAXXZ`
- size: `2131`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031850`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800192c0`
- `0x1800193c4`
- `0x18001cdec`
- `0x18002028c`
- `0x180020650`
- `0x180020cec`
- `0x1800218fc`
- `0x180021cf0`
- `0x180024314`
- `0x180025420`
- `0x180026d34`
- `0x180029bb0`
- `0x180029f88`
- `0x18002c8b4`
- `0x18002d1c0`
- `0x1800361b8`
- `0x180036ad8`
- `0x180036c0c`
- `0x180036cc0`
- `0x1801adb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a1f9`
- `KERNEL32!GetLastError` at `0x18002a1f9`
- `ADVAPI32!RegCloseKey` at `0x18002a6ca`
- `ADVAPI32!RegCloseKey` at `0x18002a6e9`
- `ADVAPI32!RegCloseKey` at `0x18002a6fd`
- `ADVAPI32!RegCloseKey` at `0x18002a6ca`
- `ADVAPI32!RegCloseKey` at `0x18002a6e9`
- `ADVAPI32!RegCloseKey` at `0x18002a6fd`
- `ADVAPI32!CloseServiceHandle` at `0x18002a70f`
- `ADVAPI32!CloseServiceHandle` at `0x18002a75e`
- `ADVAPI32!CloseServiceHandle` at `0x18002a70f`
- `ADVAPI32!CloseServiceHandle` at `0x18002a75e`
- `ADVAPI32!OpenSCManagerW` at `0x180029fe0`
- `ADVAPI32!OpenSCManagerW` at `0x180029fe0`
- `ADVAPI32!CreateServiceW` at `0x18002a1e7`
- `ADVAPI32!CreateServiceW` at `0x18002a1e7`
- `ADVAPI32!ChangeServiceConfig2W` at `0x18002a249`
- `ADVAPI32!ChangeServiceConfig2W` at `0x18002a249`

## string_xrefs

- `0x18002a78e`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002a7c9`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x180029fc7`: `Print::Server::SharedService::Install`
- `0x18002a206`: `Service already installed`
- `0x18002a171`: `Installing Service - Name: %ws, BinPath: %ws`
- `0x18002a2e6`: `ServiceDll`
- `0x18002a257`: `Service created.`
- `0x18002a3dd`: `Service entry registered %ws,%ws.`
- `0x18002a378`: `ServiceMain`
- `0x18002a549`: `Service host group created print`
- `0x18002a5c3`: `CoInitializeSecurityParam`
- `0x18002a678`: `ImpersonationLevel`
- `0x18002a64e`: `Service host registered with ImpersonationLevel of RPC_C_IMP_LEVEL_IDENTIFY`
- `0x18002a6b0`: `Service host group settings complete.`
- `0x18002a339`: `ServiceMain`
- `0x18002a27f`: `SYSTEM\CurrentControlSet\Services\PrintNotify\Parameters`
- `0x18002a160`: `%SystemRoot%\system32\svchost.exe -k print`

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
  WCHAR *v6; // rdx
  __int64 v7; // rax
  __int128 *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // r8
  SC_HANDLE ServiceW; // rdi
  signed int LastError; // eax
  bool v14; // sf
  _QWORD *v15; // rax
  const char *v16; // r9
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r8
  __int128 *v20; // r8
  unsigned __int64 v21; // r8
  char *v22; // rsi
  unsigned __int64 v23; // r8
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v25; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *Info; // [rsp+88h] [rbp-78h] BYREF
  void *v28[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  SC_HANDLE v31; // [rsp+B0h] [rbp-50h]
  SC_HANDLE v32; // [rsp+B8h] [rbp-48h]
  _BYTE v33[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v34[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v35[112]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v36; // [rsp+148h] [rbp+48h]
  _QWORD v37[13]; // [rsp+158h] [rbp+58h] BYREF
  __int128 pExceptionObject; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v39; // [rsp+1D0h] [rbp+D0h]
  WCHAR SubKey[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v41; // [rsp+1F0h] [rbp+F0h]
  __int128 v42; // [rsp+200h] [rbp+100h] BYREF
  __m128i si128; // [rsp+210h] [rbp+110h]
  _QWORD v44[4]; // [rsp+220h] [rbp+120h] BYREF
  LPCWSTR lpDisplayName[4]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v30 = -2;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo("Print::Server::SharedService::Install", L"Enter");
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v31 = v0;
  if ( !v0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF2,
      (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
      v1);
  v42 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v42) = 0;
  Print::Server::SharedService::GetExecutingModulePath(&v42);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v33);
  v2 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L"@");
  v3 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v3 = (__int128 *)v42;
  v4 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v2, v3, si128.m128i_i64[0]);
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v4, L",-");
  std::basic_ostream<unsigned short>::operator<<(v5, 1);
  std::basic_stringbuf<unsigned short>::str(v35, lpDisplayName);
  *(_OWORD *)SubKey = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)SubKey, &Filename, 0);
  std::basic_stringbuf<unsigned short>::_Tidy(v35);
  v6 = SubKey;
  if ( *((_QWORD *)&v41 + 1) > 7u )
    v6 = *(WCHAR **)SubKey;
  std::basic_stringbuf<unsigned short>::_Init(v35, v6, v41, v36);
  std::wstring::~wstring(SubKey);
  v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L"@");
  v8 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = (__int128 *)v42;
  v9 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v7, v8, si128.m128i_i64[0]);
  v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, L",-");
  std::basic_ostream<unsigned short>::operator<<(v10, 2);
  std::basic_stringbuf<unsigned short>::str(v35, v44);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Installing Service - Name: %ws, BinPath: %ws",
    Print::Server::ServiceName,
    Print::Server::ServiceBinaryPath);
  v11 = (const WCHAR *)lpDisplayName;
  if ( lpDisplayName[3] > (LPCWSTR)7 )
    v11 = lpDisplayName[0];
  ServiceW = CreateServiceW(
               v0,
               Print::Server::ServiceName,
               v11,
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
  v32 = ServiceW;
  if ( ServiceW )
  {
    v15 = v44;
    if ( v44[3] > 7u )
      v15 = (_QWORD *)v44[0];
    Info = v15;
    if ( !ChangeServiceConfig2W(ServiceW, 1u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x121,
        (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
        v16);
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
      v14 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v14 = LastError < 0;
      }
      if ( v14 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, LastError);
        throw (hr_error *)&pExceptionObject;
      }
    }
  }
  phkResult = 0;
  *(_OWORD *)SubKey = 0;
  v41 = 0;
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)&Print::Server::ServiceParametersKey + v18) );
  std::wstring::_Construct<1,unsigned short const *>((char **)SubKey, &Print::Server::ServiceParametersKey, v18);
  Win32Adapters::Registry::RegCreateKeyW(HKEY_LOCAL_MACHINE, SubKey, &phkResult);
  std::wstring::~wstring(SubKey);
  *(_OWORD *)SubKey = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)SubKey, L"ServiceDll", 0xAu);
  Win32Adapters::Registry::RegSetValueW(&phkResult, SubKey, &v42, 2);
  std::wstring::~wstring(SubKey);
  pExceptionObject = 0;
  v39 = 0;
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)&Print::Server::ServiceExportFunction + v19) );
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&pExceptionObject,
    &Print::Server::ServiceExportFunction,
    v19);
  *(_OWORD *)SubKey = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)SubKey, L"ServiceMain", 0xBu);
  Win32Adapters::Registry::RegSetValueW(&phkResult, SubKey, &pExceptionObject, 1);
  std::wstring::~wstring(SubKey);
  std::wstring::~wstring(&pExceptionObject);
  v20 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v20 = (__int128 *)v42;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service entry registered %ws,%ws.",
    v20,
    &Print::Server::ServiceExportFunction);
  v25 = 0;
  pExceptionObject = 0;
  v39 = 0;
  v21 = -1;
  do
    ++v21;
  while ( Print::Server::ServiceHostKey[v21] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, Print::Server::ServiceHostKey, v21);
  Win32Adapters::Registry::RegCreateKeyW(HKEY_LOCAL_MACHINE, (LPCWSTR)&pExceptionObject, &v25);
  std::wstring::~wstring(&pExceptionObject);
  *(_OWORD *)v28 = 0;
  v29 = 0;
  std::vector<unsigned short>::_Buy_nonzero(v28, 13);
  v22 = (char *)v28[0];
  memmove_0(v28[0], &Print::Server::ServiceGroupMembers, 0x1Au);
  v28[1] = v22 + 26;
  Info = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&Info);
  pExceptionObject = 0;
  v39 = 0;
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)&Print::Server::ServiceGroup + v23) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, &Print::Server::ServiceGroup, v23);
  Win32Adapters::Registry::RegSetValueW(&v25, &pExceptionObject, v28);
  std::wstring::~wstring(&pExceptionObject);
  hKey = 0;
  pExceptionObject = 0;
  v39 = 0;
  do
    ++v17;
  while ( *((_WORD *)&Print::Server::ServiceGroup + v17) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, &Print::Server::ServiceGroup, v17);
  Win32Adapters::Registry::RegCreateKeyW(v25, (LPCWSTR)&pExceptionObject, &hKey);
  std::wstring::~wstring(&pExceptionObject);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service host group created print");
  pExceptionObject = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, L"AuthenticationCapabilities", 0x1Au);
  Win32Adapters::Registry::RegSetValueW(&hKey, &pExceptionObject, 12320);
  std::wstring::~wstring(&pExceptionObject);
  pExceptionObject = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, L"CoInitializeSecurityParam", 0x19u);
  Win32Adapters::Registry::RegSetValueW(&hKey, &pExceptionObject, 1);
  std::wstring::~wstring(&pExceptionObject);
  pExceptionObject = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, L"AuthenticationLevel", 0x13u);
  Win32Adapters::Registry::RegSetValueW(&hKey, &pExceptionObject, 5);
  std::wstring::~wstring(&pExceptionObject);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service host registered with ImpersonationLevel of RPC_C_IMP_LEVEL_IDENTIFY");
  pExceptionObject = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject, L"ImpersonationLevel", 0x12u);
  Win32Adapters::Registry::RegSetValueW(&hKey, &pExceptionObject, 2);
  std::wstring::~wstring(&pExceptionObject);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Install",
    L"Service host group settings complete.");
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  std::vector<unsigned short>::~vector<unsigned short>(v28);
  if ( v25 )
  {
    RegCloseKey(v25);
    v25 = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( ServiceW )
    CloseServiceHandle(ServiceW);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(lpDisplayName);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v37);
  v37[0] = &std::basic_ios<unsigned short>::`vftable';
  std::ios_base::~ios_base((std::ios_base *)v37);
  std::wstring::~wstring(&v42);
  CloseServiceHandle(v0);
}

```

## disassembly

```asm
0x180029f88  push    rbp
0x180029f8a  push    rbx
0x180029f8b  push    rsi
0x180029f8c  push    rdi
0x180029f8d  push    r12
0x180029f8f  push    r13
0x180029f91  push    r14
0x180029f93  push    r15
0x180029f95  lea     rbp, [rsp-178h]
0x180029f9d  sub     rsp, 278h
0x180029fa4  mov     [rbp+1B0h+var_208], 0FFFFFFFFFFFFFFFEh
0x180029fac  mov     rax, cs:__security_cookie
0x180029fb3  xor     rax, rsp
0x180029fb6  mov     [rbp+1B0h+var_50], rax
0x180029fbd  xor     r15d, r15d
0x180029fc0  lea     rdx, aEnter_0; "Enter"
0x180029fc7  lea     r12, aPrintServerSha_6; "Print::Server::SharedService::Install"
0x180029fce  mov     rcx, r12; char *
0x180029fd1  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180029fd6  xor     edx, edx; lpDatabaseName
0x180029fd8  xor     ecx, ecx; lpMachineName
0x180029fda  mov     r8d, 0F003Fh; dwDesiredAccess
0x180029fe0  call    cs:__imp_OpenSCManagerW
0x180029fe6  mov     rbx, rax
0x180029fe9  mov     [rbp+1B0h+var_200], rax
0x180029fed  test    rax, rax
0x180029ff0  jz      loc_18002A7C2
0x180029ff6  xorps   xmm0, xmm0
0x180029ff9  movups  [rbp+1B0h+var_B0], xmm0
0x18002a000  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002a008  movdqu  [rbp+1B0h+var_A0], xmm1
0x18002a010  mov     word ptr [rbp+1B0h+var_B0], r15w
0x18002a018  lea     rcx, [rbp+1B0h+var_B0]
0x18002a01f  call    ?GetExecutingModulePath@SharedService@Server@Print@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Server::SharedService::GetExecutingModulePath(std::wstring &)
0x18002a024  lea     rcx, [rbp+1B0h+var_1F0]
0x18002a028  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18002a02d  nop
0x18002a02e  lea     rdx, asc_1801E2638; "@"
0x18002a035  lea     rcx, [rbp+1B0h+var_1E0]
0x18002a039  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002a03e  lea     rdx, [rbp+1B0h+var_B0]
0x18002a045  cmp     qword ptr [rbp+1B0h+var_A0+8], 7
0x18002a04d  cmova   rdx, qword ptr [rbp+1B0h+var_B0]
0x18002a055  mov     r8, qword ptr [rbp+1B0h+var_A0]
0x18002a05c  mov     rcx, rax
0x18002a05f  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002a064  lea     rdx, asc_1801E263C; ",-"
0x18002a06b  mov     rcx, rax
0x18002a06e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002a073  lea     esi, [r15+1]
0x18002a077  mov     edx, esi
0x18002a079  mov     rcx, rax
0x18002a07c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18002a081  lea     rdx, [rbp+1B0h+lpDisplayName]
0x18002a088  lea     rcx, [rbp+1B0h+var_1D8]
0x18002a08c  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002a091  nop
0x18002a092  xorps   xmm0, xmm0
0x18002a095  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002a09c  xorps   xmm1, xmm1
0x18002a09f  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002a0a7  xor     r8d, r8d
0x18002a0aa  lea     rdx, Filename
0x18002a0b1  lea     rcx, [rbp+1B0h+SubKey]
0x18002a0b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a0bd  nop
0x18002a0be  lea     rcx, [rbp+1B0h+var_1D8]
0x18002a0c2  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18002a0c7  lea     rdx, [rbp+1B0h+SubKey]
0x18002a0ce  cmp     qword ptr [rbp+1B0h+var_C0+8], 7
0x18002a0d6  cmova   rdx, qword ptr [rbp+1B0h+SubKey]
0x18002a0de  mov     r9d, [rbp+1B0h+var_168]
0x18002a0e2  mov     r8, qword ptr [rbp+1B0h+var_C0]
0x18002a0e9  lea     rcx, [rbp+1B0h+var_1D8]
0x18002a0ed  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18002a0f2  nop
0x18002a0f3  lea     rcx, [rbp+1B0h+SubKey]
0x18002a0fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a0ff  lea     rdx, asc_1801E2638; "@"
0x18002a106  lea     rcx, [rbp+1B0h+var_1E0]
0x18002a10a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002a10f  lea     rdx, [rbp+1B0h+var_B0]
0x18002a116  cmp     qword ptr [rbp+1B0h+var_A0+8], 7
0x18002a11e  cmova   rdx, qword ptr [rbp+1B0h+var_B0]
0x18002a126  mov     r8, qword ptr [rbp+1B0h+var_A0]
0x18002a12d  mov     rcx, rax
0x18002a130  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002a135  lea     rdx, asc_1801E263C; ",-"
0x18002a13c  mov     rcx, rax
0x18002a13f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002a144  lea     edx, [rsi+1]
0x18002a147  mov     rcx, rax
0x18002a14a  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18002a14f  lea     rdx, [rbp+1B0h+var_90]
0x18002a156  lea     rcx, [rbp+1B0h+var_1D8]
0x18002a15a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002a15f  nop
0x18002a160  lea     rdi, ?ServiceBinaryPath@Server@Print@@3PAGA; "%SystemRoot%\\system32\\svchost.exe -k "...
0x18002a167  mov     r9, rdi
0x18002a16a  lea     r8, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002a171  lea     rdx, aInstallingServ; "Installing Service - Name: %ws, BinPath"...
0x18002a178  mov     rcx, r12; char *
0x18002a17b  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a180  lea     r8, [rbp+1B0h+lpDisplayName]
0x18002a187  cmp     [rbp+1B0h+var_58], 7
0x18002a18f  cmova   r8, [rbp+1B0h+lpDisplayName]; lpDisplayName
0x18002a197  mov     [rsp+2B0h+lpPassword], r15; lpPassword
0x18002a19c  lea     rax, ?ServiceAccount@Server@Print@@3PAGA; "LocalSystem"
0x18002a1a3  mov     [rsp+2B0h+lpServiceStartName], rax; lpServiceStartName
0x18002a1a8  lea     rax, ?ServiceDependencies@Server@Print@@3PAGA; "RpcSs"
0x18002a1af  mov     [rsp+2B0h+lpDependencies], rax; lpDependencies
0x18002a1b4  mov     [rsp+2B0h+lpdwTagId], r15; lpdwTagId
0x18002a1b9  mov     [rsp+2B0h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x18002a1be  mov     [rsp+2B0h+lpBinaryPathName], rdi; lpBinaryPathName
0x18002a1c3  mov     [rsp+2B0h+dwErrorControl], esi; dwErrorControl
0x18002a1c7  mov     [rsp+2B0h+dwStartType], 3; dwStartType
0x18002a1cf  mov     [rsp+2B0h+dwServiceType], 120h; dwServiceType
0x18002a1d7  mov     r9d, 10000000h; dwDesiredAccess
0x18002a1dd  lea     rdx, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002a1e4  mov     rcx, rbx; hSCManager
0x18002a1e7  call    cs:__imp_CreateServiceW
0x18002a1ed  mov     rdi, rax
0x18002a1f0  mov     [rbp+1B0h+var_1F8], rax
0x18002a1f4  test    rax, rax
0x18002a1f7  jnz     short loc_18002A225
0x18002a1f9  call    cs:__imp_GetLastError
0x18002a1ff  cmp     eax, 431h
0x18002a204  jnz     short loc_18002A20F
0x18002a206  lea     rdx, aServiceAlready; "Service already installed"
0x18002a20d  jmp     short loc_18002A25E
0x18002a20f  test    eax, eax
0x18002a211  jle     short loc_18002A21D
0x18002a213  movzx   eax, ax
0x18002a216  or      eax, 80070000h
0x18002a21b  test    eax, eax
0x18002a21d  js      loc_18002A7A0
0x18002a223  jmp     short loc_18002A266
0x18002a225  lea     rax, [rbp+1B0h+var_90]
0x18002a22c  cmp     [rbp+1B0h+var_78], 7
0x18002a234  cmova   rax, [rbp+1B0h+var_90]
0x18002a23c  mov     [rbp+1B0h+Info], rax
0x18002a240  lea     r8, [rbp+1B0h+Info]; lpInfo
0x18002a244  mov     edx, esi; dwInfoLevel
0x18002a246  mov     rcx, rdi; hService
0x18002a249  call    cs:__imp_ChangeServiceConfig2W
0x18002a24f  test    eax, eax
0x18002a251  jz      loc_18002A787
0x18002a257  lea     rdx, aServiceCreated; "Service created."
0x18002a25e  mov     rcx, r12; char *
0x18002a261  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a266  mov     [rbp+1B0h+phkResult], r15
0x18002a26a  xorps   xmm0, xmm0
0x18002a26d  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002a274  xorps   xmm1, xmm1
0x18002a277  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002a27f  lea     rdx, ?ServiceParametersKey@Server@Print@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Pr"...
0x18002a286  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002a28a  mov     r8, r14
0x18002a28d  inc     r8
0x18002a290  cmp     [rdx+r8*2], r15w
0x18002a295  jnz     short loc_18002A28D
0x18002a297  lea     rcx, [rbp+1B0h+SubKey]
0x18002a29e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a2a3  nop
0x18002a2a4  lea     r8, [rbp+1B0h+phkResult]; phkResult
0x18002a2a8  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18002a2af  mov     r13, 0FFFFFFFF80000002h
0x18002a2b6  mov     rcx, r13; hKey
0x18002a2b9  call    ?RegCreateKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegCreateKeyW(HKEY__ *,std::wstring const &,RegistryHandleRAII &)
0x18002a2be  nop
0x18002a2bf  lea     rcx, [rbp+1B0h+SubKey]
0x18002a2c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a2cb  xorps   xmm0, xmm0
0x18002a2ce  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002a2d5  xorps   xmm1, xmm1
0x18002a2d8  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002a2e0  mov     r8d, 0Ah
0x18002a2e6  lea     rdx, aServicedll; "ServiceDll"
0x18002a2ed  lea     rcx, [rbp+1B0h+SubKey]
0x18002a2f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a2f9  nop
0x18002a2fa  mov     r9d, 2
0x18002a300  lea     r8, [rbp+1B0h+var_B0]
0x18002a307  lea     rdx, [rbp+1B0h+SubKey]
0x18002a30e  lea     rcx, [rbp+1B0h+phkResult]
0x18002a312  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::wstring const &,ulong)
0x18002a317  nop
0x18002a318  lea     rcx, [rbp+1B0h+SubKey]
0x18002a31f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a324  xorps   xmm0, xmm0
0x18002a327  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002a32e  xorps   xmm1, xmm1
0x18002a331  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002a339  lea     rsi, ?ServiceExportFunction@Server@Print@@3PAGA; "ServiceMain"
0x18002a340  mov     r8, r14
0x18002a343  inc     r8
0x18002a346  cmp     [rsi+r8*2], r15w
0x18002a34b  jnz     short loc_18002A343
0x18002a34d  mov     rdx, rsi
0x18002a350  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a357  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a35c  nop
0x18002a35d  xorps   xmm0, xmm0
0x18002a360  movups  xmmword ptr [rbp+1B0h+SubKey], xmm0
0x18002a367  xorps   xmm1, xmm1
0x18002a36a  movdqu  [rbp+1B0h+var_C0], xmm1
0x18002a372  mov     r8d, 0Bh
0x18002a378  lea     rdx, aServicemain_1; "ServiceMain"
0x18002a37f  lea     rcx, [rbp+1B0h+SubKey]
0x18002a386  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a38b  nop
0x18002a38c  mov     r9d, 1
0x18002a392  lea     r8, [rbp+1B0h+pExceptionObject]
0x18002a399  lea     rdx, [rbp+1B0h+SubKey]
0x18002a3a0  lea     rcx, [rbp+1B0h+phkResult]
0x18002a3a4  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::wstring const &,ulong)
0x18002a3a9  nop
0x18002a3aa  lea     rcx, [rbp+1B0h+SubKey]
0x18002a3b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a3b6  nop
0x18002a3b7  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a3be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a3c3  lea     r8, [rbp+1B0h+var_B0]
0x18002a3ca  cmp     qword ptr [rbp+1B0h+var_A0+8], 7
0x18002a3d2  cmova   r8, qword ptr [rbp+1B0h+var_B0]
0x18002a3da  mov     r9, rsi
0x18002a3dd  lea     rdx, aServiceEntryRe; "Service entry registered %ws,%ws."
0x18002a3e4  mov     rcx, r12; char *
0x18002a3e7  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a3ec  mov     [rsp+2B0h+var_238], r15
0x18002a3f1  xorps   xmm0, xmm0
0x18002a3f4  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002a3fb  xorps   xmm1, xmm1
0x18002a3fe  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002a406  lea     rdx, ?ServiceHostKey@Server@Print@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002a40d  mov     r8, r14
0x18002a410  inc     r8
0x18002a413  cmp     [rdx+r8*2], r15w
0x18002a418  jnz     short loc_18002A410
0x18002a41a  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a421  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a426  nop
0x18002a427  lea     r8, [rsp+2B0h+var_238]; phkResult
0x18002a42c  lea     rdx, [rbp+1B0h+pExceptionObject]; lpSubKey
0x18002a433  mov     rcx, r13; hKey
0x18002a436  call    ?RegCreateKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegCreateKeyW(HKEY__ *,std::wstring const &,RegistryHandleRAII &)
0x18002a43b  nop
0x18002a43c  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a443  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a448  xorps   xmm0, xmm0
0x18002a44b  movdqu  xmmword ptr [rbp+1B0h+var_220], xmm0
0x18002a450  mov     [rbp+1B0h+var_210], r15
0x18002a454  mov     edx, 0Dh
0x18002a459  lea     rcx, [rbp+1B0h+var_220]
0x18002a45d  call    ?_Buy_nonzero@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Buy_nonzero(unsigned __int64)
0x18002a462  mov     rsi, [rbp+1B0h+var_220]
0x18002a466  mov     r13d, 1Ah
0x18002a46c  mov     r8d, r13d; Size
0x18002a46f  lea     rdx, ?ServiceGroupMembers@Server@Print@@3PAGA; "PrintNotify"
0x18002a476  mov     rcx, rsi; void *
0x18002a479  call    memmove_0
0x18002a47e  lea     rax, [rsi+1Ah]
0x18002a482  mov     [rbp+1B0h+var_220+8], rax
0x18002a486  mov     [rbp+1B0h+Info], r15
0x18002a48a  lea     rcx, [rbp+1B0h+Info]
0x18002a48e  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x18002a493  nop
0x18002a494  xorps   xmm0, xmm0
0x18002a497  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002a49e  xorps   xmm1, xmm1
0x18002a4a1  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002a4a9  lea     rsi, ?ServiceGroup@Server@Print@@3PAGA; "print"
0x18002a4b0  mov     r8, r14
0x18002a4b3  inc     r8
0x18002a4b6  cmp     [rsi+r8*2], r15w
0x18002a4bb  jnz     short loc_18002A4B3
0x18002a4bd  mov     rdx, rsi
0x18002a4c0  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a4c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a4cc  nop
0x18002a4cd  lea     r8, [rbp+1B0h+var_220]
0x18002a4d1  lea     rdx, [rbp+1B0h+pExceptionObject]
0x18002a4d8  lea     rcx, [rsp+2B0h+var_238]
0x18002a4dd  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@GV?$allocator@G@std@@@5@K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::vector<ushort> const &,ulong)
0x18002a4e2  nop
0x18002a4e3  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a4ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a4ef  mov     [rsp+2B0h+hKey], r15
0x18002a4f4  xorps   xmm0, xmm0
0x18002a4f7  movups  [rbp+1B0h+pExceptionObject], xmm0
0x18002a4fe  xorps   xmm1, xmm1
0x18002a501  movdqu  [rbp+1B0h+var_E0], xmm1
0x18002a509  inc     r14
0x18002a50c  cmp     [rsi+r14*2], r15w
0x18002a511  jnz     short loc_18002A509
0x18002a513  mov     r8, r14
0x18002a516  mov     rdx, rsi
0x18002a519  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18002a520  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a525  nop
  ... truncated ...
```
