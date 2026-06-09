# Print::Server::SharedService::Main(ulong,ushort * *)

- ea: `0x18002ba60`
- end: `0x18002bf11`
- name: `?Main@SharedService@Server@Print@@QEAAXKPEAPEAG@Z`
- size: `1201`
- prototype: `void __fastcall(Print::Server::SharedService *this, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800336a0`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180019ff0`
- `0x18002ba60`
- `0x18002dbc8`
- `0x18002e304`
- `0x18002ebb8`
- `0x18002f994`
- `0x1800388f4`
- `0x180084fec`
- `0x18008528c`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002bb44`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002bb44`
- `KERNEL32!CloseHandle` at `0x18002bba2`
- `KERNEL32!CloseHandle` at `0x18002be6b`
- `KERNEL32!CloseHandle` at `0x18002bba2`
- `KERNEL32!CloseHandle` at `0x18002be6b`
- `KERNEL32!GetModuleFileNameW` at `0x18002bab0`
- `KERNEL32!GetModuleFileNameW` at `0x18002bab0`
- `KERNEL32!CreateEventW` at `0x18002bb82`
- `KERNEL32!CreateEventW` at `0x18002bb82`
- `KERNEL32!CreateWaitableTimerW` at `0x18002bd5f`
- `KERNEL32!CreateWaitableTimerW` at `0x18002bd5f`
- `KERNEL32!WaitForMultipleObjects` at `0x18002bda6`
- `KERNEL32!WaitForMultipleObjects` at `0x18002bda6`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x18002bbca`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x18002bbca`
- `ole32!CoResumeClassObjects` at `0x18002bd27`
- `ole32!CoResumeClassObjects` at `0x18002bd27`
- `ole32!CoSuspendClassObjects` at `0x18002bdd9`
- `ole32!CoSuspendClassObjects` at `0x18002bdd9`
- `ole32!CoRegisterClassObject` at `0x18002bc5a`
- `ole32!CoRegisterClassObject` at `0x18002bc5a`
- `ole32!CoRevokeClassObject` at `0x18002be15`
- `ole32!CoRevokeClassObject` at `0x18002be15`
- `ole32!CoInitializeEx` at `0x18002bcb5`
- `ole32!CoInitializeEx` at `0x18002bcb5`
- `ole32!CoUninitialize` at `0x18002be7c`
- `ole32!CoUninitialize` at `0x18002be7c`

## string_xrefs

- `0x18002bee3`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002bb6a`: `Print::Server::SharedService::Main`
- `0x18002bca0`: `Print::Server::SharedService::Main`
- `0x18002bd4c`: `Print::Server::SharedService::Main`
- `0x18002be51`: `Print::Server::SharedService::Main`
- `0x18002bb63`: `Service executing but process is not SvcHost!`
- `0x18002bd45`: `Service is running and waiting for terminate.`
- `0x18002bc99`: `Service registered class objects.`
- `0x18002be4a`: `Service is stopped.`
- `0x18002baf2`: `Print::Server::SharedService::ProcessIs`
- `0x18002bb1d`: `Print::Server::SharedService::ProcessIs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Print::Server::SharedService::Main(
        Print::Server::SharedService *this,
        __int64 a2,
        unsigned __int16 **a3)
{
  const char *v3; // r9
  LPWSTR i; // rax
  const wchar_t *v5; // rbx
  size_t v6; // r8
  const wchar_t *v7; // rcx
  bool v8; // bl
  HANDLE EventW; // rbx
  Print::Server::SharedService *v10; // rcx
  HRESULT v11; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v12; // rsi
  Print::Server::SharedService *v13; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v14; // rdi
  int v15; // ebx
  HRESULT v16; // eax
  Print::Server::SharedService *v17; // rcx
  Print::Server::SharedService *v18; // rcx
  HRESULT v19; // eax
  Print::Server::SharedService *v20; // rcx
  char *WaitableTimerW; // rdi
  DWORD v22; // eax
  Print::Server::SharedService *v23; // rcx
  char v24; // si
  Print::Server::SharedService *v25; // rcx
  HRESULT v26; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v27; // rsi
  Print::Server::SharedService *v28; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v29; // rdx
  Print::Server::SharedService *v30; // rcx
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-19h] BYREF
  HANDLE Handles[4]; // [rsp+38h] [rbp-11h] BYREF
  LPWSTR lpFilename[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v34; // [rsp+68h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  Handles[2] = (HANDLE)-2LL;
  *(_OWORD *)lpFilename = 0;
  *(_QWORD *)&v34 = 0;
  std::vector<unsigned short>::resize((__int64 *)lpFilename, 0x104u);
  if ( !GetModuleFileNameW(0, lpFilename[0], 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19F,
      (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
      v3);
  for ( i = lpFilename[1]; lpFilename[0] < i; --i )
  {
    if ( *i == 92 )
    {
      v5 = i + 1;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Server::SharedService::ProcessIs",
        L"Current process is '%ws'.",
        i + 1);
      v6 = lpFilename[1] - v5;
      v7 = v5;
      goto LABEL_9;
    }
  }
  if ( lpFilename[1] == lpFilename[0]
    || (Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Server::SharedService::ProcessIs",
          L"Current process is '%ws'.",
          lpFilename[0]),
        v7 = lpFilename[0],
        (v6 = lpFilename[1] - lpFilename[0]) == 0) )
  {
    std::vector<unsigned short>::_Xrange();
  }
LABEL_9:
  v8 = _o__wcsnicmp(v7, L"SvcHost.exe", v6) == 0;
  std::vector<unsigned short>::~vector<unsigned short>((char **)lpFilename);
  if ( !v8 )
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Server::SharedService::Main",
      L"Service executing but process is not SvcHost!");
  EventW = CreateEventW(0, 1, 0, 0);
  if ( (char *)g_Server - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(g_Server);
  g_Server = EventW;
  hServiceStatus = RegisterServiceCtrlHandlerExW(
                     Print::Server::ServiceName,
                     (LPHANDLER_FUNCTION_EX)Print::Server::ServiceHandlerEx,
                     &g_Server);
  Print::Server::SharedService::UpdateStatus(v10, 2u);
  v11 = 1;
  v12 = off_180294F20;
  v13 = off_180294F28;
  while ( v12 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v13 )
  {
    if ( v11 < 0 )
      goto LABEL_54;
    v14 = *v12;
    if ( *v12 )
    {
      pUnk = 0;
      if ( *((_QWORD *)v14 + 2) )
      {
        v11 = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v14 + 2))(
                *((_QWORD *)v14 + 3),
                &GUID_00000000_0000_0000_c000_000000000046,
                &pUnk);
        if ( v11 >= 0 )
          v11 = CoRegisterClassObject(*(const IID *const *)v14, pUnk, 4u, 5u, (LPDWORD)v14 + 10);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        v13 = off_180294F28;
      }
      else
      {
        v11 = 0;
      }
    }
    ++v12;
  }
  if ( v11 < 0 )
  {
LABEL_54:
    hr_error::hr_error((hr_error *)lpFilename, v11);
    throw (hr_error *)lpFilename;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Main",
    L"Service registered class objects.");
  v15 = 0;
  LODWORD(pUnk) = 0;
  v16 = CoInitializeEx(0, 0);
  if ( v16 >= 0 )
  {
    v15 = 1;
    LODWORD(pUnk) = 1;
  }
  else if ( v16 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)lpFilename, v16);
    throw (hr_error *)lpFilename;
  }
  Print::Server::SharedService::UpdateStatus(v17, 2u);
  *(_OWORD *)lpFilename = 0;
  v34 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    lpFilename,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print",
    0x32u);
  Print::Driver::PrinterExtensionRegistrarService::Start(lpFilename);
  std::wstring::~wstring((char **)lpFilename);
  Print::Server::SharedService::UpdateStatus(v18, 2u);
  v19 = CoResumeClassObjects();
  if ( v19 < 0 )
  {
    hr_error::hr_error((hr_error *)lpFilename, v19);
    throw (hr_error *)lpFilename;
  }
  Print::Server::SharedService::UpdateStatus(v20, 4u);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Main",
    L"Service is running and waiting for terminate.");
  WaitableTimerW = (char *)CreateWaitableTimerW(0, 0, 0);
  Handles[3] = WaitableTimerW;
  Win32Adapters::Synchronization::SetWaitableTimerEx(
    (Win32Adapters::Synchronization *)WaitableTimerW,
    (void *const)0x927C0,
    60000,
    0x927C0u);
  Handles[0] = g_Server;
  Handles[1] = WaitableTimerW;
  while ( 1 )
  {
    v22 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !Print::Driver::PrintNotifyLock::m_locks )
      break;
    v24 = 0;
    if ( v22 - 1 > 0xFFFFFFFD )
      goto LABEL_36;
  }
  v24 = 1;
LABEL_36:
  Print::Server::SharedService::UpdateStatus(v23, 3u);
  if ( v24 )
    CoSuspendClassObjects();
  Print::Server::SharedService::UpdateStatus(v25, 3u);
  v26 = 0;
  v27 = off_180294F20;
  v28 = off_180294F28;
  while ( v27 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v28 && !v26 )
  {
    v29 = *v27;
    if ( *v27 && *((_DWORD *)v29 + 10) )
    {
      v26 = CoRevokeClassObject(*((_DWORD *)v29 + 10));
      v28 = off_180294F28;
    }
    ++v27;
  }
  Print::Server::SharedService::UpdateStatus(v28, 3u);
  Print::Driver::PrinterExtensionRegistrarService::Stop();
  Print::Server::SharedService::UpdateStatus(v30, 1u);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Main",
    L"Service is stopped.");
  if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(WaitableTimerW);
  if ( v15 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18002ba60  push    rbp
0x18002ba62  push    rbx
0x18002ba63  push    rsi
0x18002ba64  push    rdi
0x18002ba65  lea     rbp, [rsp-3Fh]
0x18002ba6a  sub     rsp, 88h
0x18002ba71  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x18002ba79  mov     rax, cs:__security_cookie
0x18002ba80  xor     rax, rsp
0x18002ba83  mov     [rbp+57h+var_28], rax
0x18002ba87  xorps   xmm0, xmm0
0x18002ba8a  movdqu  xmmword ptr [rbp+57h+lpFilename], xmm0
0x18002ba8f  mov     qword ptr [rbp+57h+var_38], 0
0x18002ba97  mov     ebx, 104h
0x18002ba9c  mov     edx, ebx
0x18002ba9e  lea     rcx, [rbp+57h+lpFilename]
0x18002baa2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002baa7  mov     r8d, ebx; nSize
0x18002baaa  mov     rdx, [rbp+57h+lpFilename]; lpFilename
0x18002baae  xor     ecx, ecx; hModule
0x18002bab0  call    cs:__imp_GetModuleFileNameW
0x18002bab7  nop     dword ptr [rax+rax+00h]
0x18002babc  test    eax, eax
0x18002babe  jz      loc_18002BEDF
0x18002bac4  mov     rcx, [rbp+57h+lpFilename+8]
0x18002bac8  mov     rax, rcx
0x18002bacb  mov     r8, [rbp+57h+lpFilename]
0x18002bacf  cmp     r8, rax
0x18002bad2  jnb     short loc_18002BB0D
0x18002bad4  mov     edx, 5Ch ; '\'
0x18002bad9  cmp     dx, [rax]
0x18002badc  jz      short loc_18002BAE4
0x18002bade  sub     rax, 2
0x18002bae2  jmp     short loc_18002BACF
0x18002bae4  lea     rbx, [rax+2]
0x18002bae8  mov     r8, rbx
0x18002baeb  lea     rdx, aCurrentProcess; "Current process is '%ws'."
0x18002baf2  lea     rcx, aPrintServerSha_3; "Print::Server::SharedService::ProcessIs"
0x18002baf9  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002bafe  mov     r8, [rbp+57h+lpFilename+8]
0x18002bb02  sub     r8, rbx
0x18002bb05  sar     r8, 1
0x18002bb08  mov     rcx, rbx
0x18002bb0b  jmp     short loc_18002BB3D
0x18002bb0d  cmp     rcx, r8
0x18002bb10  jz      loc_18002BED9
0x18002bb16  lea     rdx, aCurrentProcess; "Current process is '%ws'."
0x18002bb1d  lea     rcx, aPrintServerSha_3; "Print::Server::SharedService::ProcessIs"
0x18002bb24  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002bb29  mov     rcx, [rbp+57h+lpFilename]
0x18002bb2d  mov     r8, [rbp+57h+lpFilename+8]
0x18002bb31  sub     r8, rcx
0x18002bb34  sar     r8, 1
0x18002bb37  jz      loc_18002BED9
0x18002bb3d  lea     rdx, aSvchostExe; "SvcHost.exe"
0x18002bb44  call    cs:__imp__o__wcsnicmp
0x18002bb4b  nop     dword ptr [rax+rax+00h]
0x18002bb50  nop
0x18002bb51  test    eax, eax
0x18002bb53  setz    bl
0x18002bb56  lea     rcx, [rbp+57h+lpFilename]
0x18002bb5a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002bb5f  test    bl, bl
0x18002bb61  jnz     short loc_18002BB76
0x18002bb63  lea     rdx, aServiceExecuti; "Service executing but process is not Sv"...
0x18002bb6a  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002bb71  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002bb76  xor     r9d, r9d; lpName
0x18002bb79  xor     r8d, r8d; bInitialState
0x18002bb7c  lea     edx, [r9+1]; bManualReset
0x18002bb80  xor     ecx, ecx; lpEventAttributes
0x18002bb82  call    cs:__imp_CreateEventW
0x18002bb89  nop     dword ptr [rax+rax+00h]
0x18002bb8e  mov     rbx, rax
0x18002bb91  mov     rcx, cs:?g_Server@@3VSharedService@Server@Print@@A; hObject
0x18002bb98  lea     rdx, [rcx-1]
0x18002bb9c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002bba0  ja      short loc_18002BBAE
0x18002bba2  call    cs:__imp_CloseHandle
0x18002bba9  nop     dword ptr [rax+rax+00h]
0x18002bbae  mov     cs:?g_Server@@3VSharedService@Server@Print@@A, rbx; Print::Server::SharedService g_Server
0x18002bbb5  lea     r8, ?g_Server@@3VSharedService@Server@Print@@A; lpContext
0x18002bbbc  lea     rdx, ?ServiceHandlerEx@Server@Print@@YAKKKPEAX0@Z; lpHandlerProc
0x18002bbc3  lea     rcx, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002bbca  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002bbd1  nop     dword ptr [rax+rax+00h]
0x18002bbd6  mov     cs:hServiceStatus, rax
0x18002bbdd  mov     edx, 2; unsigned int
0x18002bbe2  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002bbe7  mov     ebx, 1
0x18002bbec  mov     rsi, cs:off_180294F20
0x18002bbf3  mov     rax, cs:off_180294F28
0x18002bbfa  jmp     loc_18002BC88
0x18002bbff  test    ebx, ebx
0x18002bc01  js      loc_18002BEF5
0x18002bc07  mov     rdi, [rsi]
0x18002bc0a  test    rdi, rdi
0x18002bc0d  jz      short loc_18002BC84
0x18002bc0f  mov     [rbp+57h+pUnk], 0
0x18002bc17  cmp     qword ptr [rdi+10h], 0
0x18002bc1c  jnz     short loc_18002BC22
0x18002bc1e  xor     ebx, ebx
0x18002bc20  jmp     short loc_18002BC84
0x18002bc22  lea     r8, [rbp+57h+pUnk]
0x18002bc26  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002bc2d  mov     rcx, [rdi+18h]
0x18002bc31  mov     rax, [rdi+10h]
0x18002bc35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc3a  mov     ebx, eax
0x18002bc3c  test    eax, eax
0x18002bc3e  js      short loc_18002BC68
0x18002bc40  lea     rax, [rdi+28h]
0x18002bc44  mov     qword ptr [rsp+0A0h+lpdwRegister], rax; unsigned int
0x18002bc49  mov     r9d, 5; flags
0x18002bc4f  lea     r8d, [r9-1]; dwClsContext
0x18002bc53  mov     rdx, [rbp+57h+pUnk]; pUnk
0x18002bc57  mov     rcx, [rdi]; rclsid
0x18002bc5a  call    cs:__imp_CoRegisterClassObject
0x18002bc61  nop     dword ptr [rax+rax+00h]
0x18002bc66  mov     ebx, eax
0x18002bc68  mov     rcx, [rbp+57h+pUnk]
0x18002bc6c  test    rcx, rcx
0x18002bc6f  jz      short loc_18002BC7D
0x18002bc71  mov     rax, [rcx]
0x18002bc74  mov     rax, [rax+10h]
0x18002bc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc7d  mov     rax, cs:off_180294F28
0x18002bc84  add     rsi, 8
0x18002bc88  cmp     rsi, rax
0x18002bc8b  jb      loc_18002BBFF
0x18002bc91  test    ebx, ebx
0x18002bc93  js      loc_18002BEF5
0x18002bc99  lea     rdx, aServiceRegiste; "Service registered class objects."
0x18002bca0  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002bca7  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002bcac  xor     ebx, ebx
0x18002bcae  mov     dword ptr [rbp+57h+pUnk], ebx
0x18002bcb1  xor     edx, edx; dwCoInit
0x18002bcb3  xor     ecx, ecx; pvReserved
0x18002bcb5  call    cs:__imp_CoInitializeEx
0x18002bcbc  nop     dword ptr [rax+rax+00h]
0x18002bcc1  test    eax, eax
0x18002bcc3  jns     short loc_18002BCD2
0x18002bcc5  cmp     eax, 80010106h
0x18002bcca  jnz     loc_18002BEBD
0x18002bcd0  jmp     short loc_18002BCDA
0x18002bcd2  mov     ebx, 1
0x18002bcd7  mov     dword ptr [rbp+57h+pUnk], ebx
0x18002bcda  mov     edx, 2; unsigned int
0x18002bcdf  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002bce4  xorps   xmm0, xmm0
0x18002bce7  movups  xmmword ptr [rbp+57h+lpFilename], xmm0
0x18002bceb  xorps   xmm1, xmm1
0x18002bcee  movdqu  [rbp+57h+var_38], xmm1
0x18002bcf3  mov     r8d, 32h ; '2'
0x18002bcf9  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002bd00  lea     rcx, [rbp+57h+lpFilename]
0x18002bd04  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002bd09  nop
0x18002bd0a  lea     rcx, [rbp+57h+lpFilename]
0x18002bd0e  call    ?Start@PrinterExtensionRegistrarService@Driver@Print@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Driver::PrinterExtensionRegistrarService::Start(std::wstring const &)
0x18002bd13  nop
0x18002bd14  lea     rcx, [rbp+57h+lpFilename]
0x18002bd18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bd1d  mov     edx, 2; unsigned int
0x18002bd22  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002bd27  call    cs:__imp_CoResumeClassObjects
0x18002bd2e  nop     dword ptr [rax+rax+00h]
0x18002bd33  test    eax, eax
0x18002bd35  js      loc_18002BEA1
0x18002bd3b  mov     edx, 4; unsigned int
0x18002bd40  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002bd45  lea     rdx, aServiceIsRunni; "Service is running and waiting for term"...
0x18002bd4c  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002bd53  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002bd58  xor     r8d, r8d; lpTimerName
0x18002bd5b  xor     edx, edx; bManualReset
0x18002bd5d  xor     ecx, ecx; lpTimerAttributes
0x18002bd5f  call    cs:__imp_CreateWaitableTimerW
0x18002bd66  nop     dword ptr [rax+rax+00h]
0x18002bd6b  mov     rdi, rax
0x18002bd6e  mov     [rbp+57h+var_50], rax
0x18002bd72  mov     edx, 927C0h; void *
0x18002bd77  mov     r9d, edx; unsigned int
0x18002bd7a  mov     r8d, 0EA60h; unsigned int
0x18002bd80  mov     rcx, rax; this
0x18002bd83  call    ?SetWaitableTimerEx@Synchronization@Win32Adapters@@YAXQEAXKKK@Z; Win32Adapters::Synchronization::SetWaitableTimerEx(void * const,ulong,ulong,ulong)
0x18002bd88  mov     rax, cs:?g_Server@@3VSharedService@Server@Print@@A; Print::Server::SharedService g_Server
0x18002bd8f  mov     [rbp+57h+Handles], rax
0x18002bd93  mov     [rbp+57h+var_60], rdi
0x18002bd97  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002bd9b  xor     r8d, r8d; bWaitAll
0x18002bd9e  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18002bda2  lea     ecx, [r8+2]; nCount
0x18002bda6  call    cs:__imp_WaitForMultipleObjects
0x18002bdad  nop     dword ptr [rax+rax+00h]
0x18002bdb2  cmp     cs:?m_locks@PrintNotifyLock@Driver@Print@@0KA, 0; ulong Print::Driver::PrintNotifyLock::m_locks
0x18002bdb9  jz      short loc_18002BDC7
0x18002bdbb  xor     sil, sil
0x18002bdbe  dec     eax
0x18002bdc0  cmp     eax, 0FFFFFFFDh
0x18002bdc3  jbe     short loc_18002BD97
0x18002bdc5  jmp     short loc_18002BDCA
0x18002bdc7  mov     sil, 1
0x18002bdca  mov     edx, 3; unsigned int
0x18002bdcf  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002bdd4  test    sil, sil
0x18002bdd7  jz      short loc_18002BDE5
0x18002bdd9  call    cs:__imp_CoSuspendClassObjects
0x18002bde0  nop     dword ptr [rax+rax+00h]
0x18002bde5  mov     edx, 3; unsigned int
0x18002bdea  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002bdef  xor     eax, eax
0x18002bdf1  mov     rsi, cs:off_180294F20
0x18002bdf8  mov     rcx, cs:off_180294F28
0x18002bdff  jmp     short loc_18002BE2C
0x18002be01  test    eax, eax
0x18002be03  jnz     short loc_18002BE31
0x18002be05  mov     rdx, [rsi]
0x18002be08  test    rdx, rdx
0x18002be0b  jz      short loc_18002BE28
0x18002be0d  cmp     [rdx+28h], eax
0x18002be10  jz      short loc_18002BE28
0x18002be12  mov     ecx, [rdx+28h]; dwRegister
0x18002be15  call    cs:__imp_CoRevokeClassObject
0x18002be1c  nop     dword ptr [rax+rax+00h]
0x18002be21  mov     rcx, cs:off_180294F28; this
0x18002be28  add     rsi, 8
0x18002be2c  cmp     rsi, rcx
0x18002be2f  jb      short loc_18002BE01
0x18002be31  mov     edx, 3; unsigned int
0x18002be36  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002be3b  call    ?Stop@PrinterExtensionRegistrarService@Driver@Print@@SAXXZ; Print::Driver::PrinterExtensionRegistrarService::Stop(void)
0x18002be40  mov     edx, 1; unsigned int
0x18002be45  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002be4a  lea     rdx, aServiceIsStopp; "Service is stopped."
0x18002be51  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002be58  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002be5d  nop
0x18002be5e  lea     rax, [rdi-1]
0x18002be62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002be66  ja      short loc_18002BE78
0x18002be68  mov     rcx, rdi; hObject
0x18002be6b  call    cs:__imp_CloseHandle
0x18002be72  nop     dword ptr [rax+rax+00h]
0x18002be77  nop
0x18002be78  test    ebx, ebx
0x18002be7a  jz      short loc_18002BE88
0x18002be7c  call    cs:__imp_CoUninitialize
0x18002be83  nop     dword ptr [rax+rax+00h]
0x18002be88  mov     rcx, [rbp+57h+var_28]
0x18002be8c  xor     rcx, rsp; StackCookie
0x18002be8f  call    __security_check_cookie
0x18002be94  add     rsp, 88h
0x18002be9b  pop     rdi
0x18002be9c  pop     rsi
0x18002be9d  pop     rbx
0x18002be9e  pop     rbp
0x18002be9f  retn
0x18002bea1  mov     edx, eax; int
0x18002bea3  lea     rcx, [rbp+57h+lpFilename]; this
0x18002bea7  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002beac  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002beb3  lea     rcx, [rbp+57h+lpFilename]; pExceptionObject
0x18002beb7  call    _CxxThrowException_0
0x18002bebd  mov     edx, eax; int
0x18002bebf  lea     rcx, [rbp+57h+lpFilename]; this
0x18002bec3  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002bec8  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002becf  lea     rcx, [rbp+57h+lpFilename]; pExceptionObject
0x18002bed3  call    _CxxThrowException_0
0x18002bed9  call    ?_Xrange@?$vector@GV?$allocator@G@std@@@std@@CAXXZ; std::vector<ushort>::_Xrange(void)
0x18002bedf  mov     rcx, [rbp+5Fh]; this
0x18002bee3  lea     r8, aPrintscanPrint_18; "printscan\\print\\drivers\\usermode\\dr"...
0x18002beea  mov     edx, 19Fh; void *
0x18002beef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002bef5  mov     edx, ebx; int
0x18002bef7  lea     rcx, [rbp+57h+lpFilename]; this
0x18002befb  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002bf00  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002bf07  lea     rcx, [rbp+57h+lpFilename]; pExceptionObject
0x18002bf0b  call    _CxxThrowException_0
```
