# Print::Server::SharedService::Main(ulong,ushort * *)

- ea: `0x18002a9a0`
- end: `0x18002adfc`
- name: `?Main@SharedService@Server@Print@@QEAAXKPEAPEAG@Z`
- size: `1116`
- prototype: `void __fastcall(Print::Server::SharedService *this, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800326a0`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800193c4`
- `0x18002a9a0`
- `0x18002c8b4`
- `0x18002cf74`
- `0x18002d814`
- `0x18002e670`
- `0x18003744c`
- `0x180081f44`
- `0x1800821bc`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002aa7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002aa7e`
- `KERNEL32!CloseHandle` at `0x18002aad0`
- `KERNEL32!CloseHandle` at `0x18002ad63`
- `KERNEL32!CloseHandle` at `0x18002aad0`
- `KERNEL32!CloseHandle` at `0x18002ad63`
- `KERNEL32!GetModuleFileNameW` at `0x18002a9f0`
- `KERNEL32!GetModuleFileNameW` at `0x18002a9f0`
- `KERNEL32!CreateEventW` at `0x18002aab6`
- `KERNEL32!CreateEventW` at `0x18002aab6`
- `KERNEL32!CreateWaitableTimerW` at `0x18002ac6f`
- `KERNEL32!CreateWaitableTimerW` at `0x18002ac6f`
- `KERNEL32!WaitForMultipleObjects` at `0x18002acb0`
- `KERNEL32!WaitForMultipleObjects` at `0x18002acb0`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x18002aaf2`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x18002aaf2`
- `ole32!CoResumeClassObjects` at `0x18002ac3d`
- `ole32!CoResumeClassObjects` at `0x18002ac3d`
- `ole32!CoSuspendClassObjects` at `0x18002acdd`
- `ole32!CoSuspendClassObjects` at `0x18002acdd`
- `ole32!CoRegisterClassObject` at `0x18002ab7c`
- `ole32!CoRegisterClassObject` at `0x18002ab7c`
- `ole32!CoRevokeClassObject` at `0x18002ad13`
- `ole32!CoRevokeClassObject` at `0x18002ad13`
- `ole32!CoInitializeEx` at `0x18002abd1`
- `ole32!CoInitializeEx` at `0x18002abd1`
- `ole32!CoUninitialize` at `0x18002ad6e`
- `ole32!CoUninitialize` at `0x18002ad6e`

## string_xrefs

- `0x18002adce`: `printscan\print\drivers\usermode\driverui\dll\printconfig\server.cpp`
- `0x18002aa9e`: `Print::Server::SharedService::Main`
- `0x18002abbc`: `Print::Server::SharedService::Main`
- `0x18002ac5c`: `Print::Server::SharedService::Main`
- `0x18002ad49`: `Print::Server::SharedService::Main`
- `0x18002aa97`: `Service executing but process is not SvcHost!`
- `0x18002ac55`: `Service is running and waiting for terminate.`
- `0x18002abb5`: `Service registered class objects.`
- `0x18002ad42`: `Service is stopped.`
- `0x18002aa2c`: `Print::Server::SharedService::ProcessIs`
- `0x18002aa57`: `Print::Server::SharedService::ProcessIs`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Print::Server::SharedService::Main(
        Print::Server::SharedService *this,
        __int64 a2,
        unsigned __int16 **a3)
{
  __int64 v3; // rdx
  const char *v4; // r9
  LPWSTR v5; // rcx
  LPWSTR v6; // rax
  __int64 v7; // r8
  WCHAR *v8; // rbx
  bool v9; // bl
  HANDLE EventW; // rbx
  Print::Server::SharedService *v11; // rcx
  HRESULT v12; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v13; // rsi
  Print::Server::SharedService *v14; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v15; // rdi
  int v16; // ebx
  HRESULT v17; // eax
  Print::Server::SharedService *v18; // rcx
  Print::Server::SharedService *v19; // rcx
  HRESULT v20; // eax
  Print::Server::SharedService *v21; // rcx
  char *WaitableTimerW; // rdi
  DWORD v23; // eax
  Print::Server::SharedService *v24; // rcx
  char v25; // si
  Print::Server::SharedService *v26; // rcx
  HRESULT v27; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v28; // rsi
  Print::Server::SharedService *v29; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v30; // rdx
  Print::Server::SharedService *v31; // rcx
  unsigned int lpdwRegister; // [rsp+20h] [rbp-29h]
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-19h] BYREF
  HANDLE Handles[4]; // [rsp+38h] [rbp-11h] BYREF
  LPWSTR lpFilename[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v36; // [rsp+68h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  Handles[2] = (HANDLE)-2LL;
  *(_OWORD *)lpFilename = 0;
  *(_QWORD *)&v36 = 0;
  std::vector<unsigned short>::resize(lpFilename, 260, a3);
  if ( !GetModuleFileNameW(0, lpFilename[0], 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19F,
      (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\server.cpp",
      v4);
  v5 = lpFilename[1];
  v6 = lpFilename[1];
  v7 = (__int64)lpFilename[0];
  while ( lpFilename[0] < v6 )
  {
    v3 = 92;
    if ( *v6 == 92 )
    {
      v8 = v6 + 1;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Server::SharedService::ProcessIs",
        L"Current process is '%ws'.",
        v6 + 1);
      v7 = lpFilename[1] - v8;
      v5 = v8;
      goto LABEL_9;
    }
    --v6;
  }
  if ( lpFilename[1] == lpFilename[0]
    || (Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Server::SharedService::ProcessIs",
          L"Current process is '%ws'.",
          lpFilename[0]),
        v5 = lpFilename[0],
        (v7 = lpFilename[1] - lpFilename[0]) == 0) )
  {
    std::vector<unsigned short>::_Xrange(v5, v3, v7);
  }
LABEL_9:
  v9 = (unsigned int)_o__wcsnicmp(v5, L"SvcHost.exe", v7) == 0;
  std::vector<unsigned short>::~vector<unsigned short>(lpFilename);
  if ( !v9 )
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Server::SharedService::Main",
      L"Service executing but process is not SvcHost!");
  EventW = CreateEventW(0, 1, 0, 0);
  if ( (char *)g_Server - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(g_Server);
  g_Server = EventW;
  hServiceStatus = RegisterServiceCtrlHandlerExW(Print::Server::ServiceName, Print::Server::ServiceHandlerEx, &g_Server);
  Print::Server::SharedService::UpdateStatus(v11, 2u);
  v12 = 1;
  v13 = off_18028DDA0;
  v14 = off_18028DDA8;
  while ( v13 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v14 )
  {
    if ( v12 < 0 )
      goto LABEL_54;
    v15 = *v13;
    if ( *v13 )
    {
      pUnk = 0;
      if ( *((_QWORD *)v15 + 2) )
      {
        v12 = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v15 + 2))(
                *((_QWORD *)v15 + 3),
                &GUID_00000000_0000_0000_c000_000000000046,
                &pUnk);
        if ( v12 >= 0 )
          v12 = CoRegisterClassObject(*(const IID *const *)v15, pUnk, 4u, 5u, (LPDWORD)v15 + 10);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        v14 = off_18028DDA8;
      }
      else
      {
        v12 = 0;
      }
    }
    ++v13;
  }
  if ( v12 < 0 )
  {
LABEL_54:
    hr_error::hr_error((hr_error *)lpFilename, v12);
    throw (hr_error *)lpFilename;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Main",
    L"Service registered class objects.");
  v16 = 0;
  LODWORD(pUnk) = 0;
  v17 = CoInitializeEx(0, 0);
  if ( v17 >= 0 )
  {
    v16 = 1;
    LODWORD(pUnk) = 1;
  }
  else if ( v17 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)lpFilename, v17);
    throw (hr_error *)lpFilename;
  }
  Print::Server::SharedService::UpdateStatus(v18, 2u);
  *(_OWORD *)lpFilename = 0;
  v36 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    lpFilename,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print");
  Print::Driver::PrinterExtensionRegistrarService::Start((__int64)lpFilename);
  std::wstring::~wstring(lpFilename);
  Print::Server::SharedService::UpdateStatus(v19, 2u);
  v20 = CoResumeClassObjects();
  if ( v20 < 0 )
  {
    hr_error::hr_error((hr_error *)lpFilename, v20);
    throw (hr_error *)lpFilename;
  }
  Print::Server::SharedService::UpdateStatus(v21, 4u);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Main",
    L"Service is running and waiting for terminate.");
  WaitableTimerW = (char *)CreateWaitableTimerW(0, 0, 0);
  Handles[3] = WaitableTimerW;
  Win32Adapters::Synchronization::SetWaitableTimerEx(
    (Win32Adapters::Synchronization *)WaitableTimerW,
    (void *const)0x927C0,
    0xEA60u,
    0x927C0u,
    lpdwRegister);
  Handles[0] = g_Server;
  Handles[1] = WaitableTimerW;
  while ( 1 )
  {
    v23 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !Print::Driver::PrintNotifyLock::m_locks )
      break;
    v25 = 0;
    if ( v23 - 1 > 0xFFFFFFFD )
      goto LABEL_36;
  }
  v25 = 1;
LABEL_36:
  Print::Server::SharedService::UpdateStatus(v24, 3u);
  if ( v25 )
    CoSuspendClassObjects();
  Print::Server::SharedService::UpdateStatus(v26, 3u);
  v27 = 0;
  v28 = off_18028DDA0;
  v29 = off_18028DDA8;
  while ( v28 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v29 && !v27 )
  {
    v30 = *v28;
    if ( *v28 && *((_DWORD *)v30 + 10) )
    {
      v27 = CoRevokeClassObject(*((_DWORD *)v30 + 10));
      v29 = off_18028DDA8;
    }
    ++v28;
  }
  Print::Server::SharedService::UpdateStatus(v29, 3u);
  Print::Driver::PrinterExtensionRegistrarService::Stop();
  Print::Server::SharedService::UpdateStatus(v31, 1u);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Server::SharedService::Main",
    L"Service is stopped.");
  if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(WaitableTimerW);
  if ( v16 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18002a9a0  push    rbp
0x18002a9a2  push    rbx
0x18002a9a3  push    rsi
0x18002a9a4  push    rdi
0x18002a9a5  lea     rbp, [rsp-3Fh]
0x18002a9aa  sub     rsp, 88h
0x18002a9b1  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x18002a9b9  mov     rax, cs:__security_cookie
0x18002a9c0  xor     rax, rsp
0x18002a9c3  mov     [rbp+57h+var_28], rax
0x18002a9c7  xorps   xmm0, xmm0
0x18002a9ca  movdqu  xmmword ptr [rbp+57h+lpFilename], xmm0
0x18002a9cf  mov     qword ptr [rbp+57h+var_38], 0
0x18002a9d7  mov     ebx, 104h
0x18002a9dc  mov     edx, ebx
0x18002a9de  lea     rcx, [rbp+57h+lpFilename]
0x18002a9e2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002a9e7  mov     r8d, ebx; nSize
0x18002a9ea  mov     rdx, [rbp+57h+lpFilename]; lpFilename
0x18002a9ee  xor     ecx, ecx; hModule
0x18002a9f0  call    cs:__imp_GetModuleFileNameW
0x18002a9f6  test    eax, eax
0x18002a9f8  jz      loc_18002ADCA
0x18002a9fe  mov     rcx, [rbp+57h+lpFilename+8]
0x18002aa02  mov     rax, rcx
0x18002aa05  mov     r8, [rbp+57h+lpFilename]
0x18002aa09  cmp     r8, rax
0x18002aa0c  jnb     short loc_18002AA47
0x18002aa0e  mov     edx, 5Ch ; '\'
0x18002aa13  cmp     dx, [rax]
0x18002aa16  jz      short loc_18002AA1E
0x18002aa18  sub     rax, 2
0x18002aa1c  jmp     short loc_18002AA09
0x18002aa1e  lea     rbx, [rax+2]
0x18002aa22  mov     r8, rbx
0x18002aa25  lea     rdx, aCurrentProcess; "Current process is '%ws'."
0x18002aa2c  lea     rcx, aPrintServerSha_3; "Print::Server::SharedService::ProcessIs"
0x18002aa33  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002aa38  mov     r8, [rbp+57h+lpFilename+8]
0x18002aa3c  sub     r8, rbx
0x18002aa3f  sar     r8, 1
0x18002aa42  mov     rcx, rbx
0x18002aa45  jmp     short loc_18002AA77
0x18002aa47  cmp     rcx, r8
0x18002aa4a  jz      loc_18002ADC4
0x18002aa50  lea     rdx, aCurrentProcess; "Current process is '%ws'."
0x18002aa57  lea     rcx, aPrintServerSha_3; "Print::Server::SharedService::ProcessIs"
0x18002aa5e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002aa63  mov     rcx, [rbp+57h+lpFilename]
0x18002aa67  mov     r8, [rbp+57h+lpFilename+8]
0x18002aa6b  sub     r8, rcx
0x18002aa6e  sar     r8, 1
0x18002aa71  jz      loc_18002ADC4
0x18002aa77  lea     rdx, aSvchostExe; "SvcHost.exe"
0x18002aa7e  call    cs:__imp__o__wcsnicmp
0x18002aa84  nop
0x18002aa85  test    eax, eax
0x18002aa87  setz    bl
0x18002aa8a  lea     rcx, [rbp+57h+lpFilename]
0x18002aa8e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002aa93  test    bl, bl
0x18002aa95  jnz     short loc_18002AAAA
0x18002aa97  lea     rdx, aServiceExecuti; "Service executing but process is not Sv"...
0x18002aa9e  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002aaa5  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002aaaa  xor     r9d, r9d; lpName
0x18002aaad  xor     r8d, r8d; bInitialState
0x18002aab0  lea     edx, [r9+1]; bManualReset
0x18002aab4  xor     ecx, ecx; lpEventAttributes
0x18002aab6  call    cs:__imp_CreateEventW
0x18002aabc  mov     rbx, rax
0x18002aabf  mov     rcx, cs:?g_Server@@3VSharedService@Server@Print@@A; hObject
0x18002aac6  lea     rdx, [rcx-1]
0x18002aaca  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002aace  ja      short loc_18002AAD6
0x18002aad0  call    cs:__imp_CloseHandle
0x18002aad6  mov     cs:?g_Server@@3VSharedService@Server@Print@@A, rbx; Print::Server::SharedService g_Server
0x18002aadd  lea     r8, ?g_Server@@3VSharedService@Server@Print@@A; lpContext
0x18002aae4  lea     rdx, ?ServiceHandlerEx@Server@Print@@YAKKKPEAX0@Z; lpHandlerProc
0x18002aaeb  lea     rcx, ?ServiceName@Server@Print@@3PAGA; "PrintNotify"
0x18002aaf2  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002aaf8  mov     cs:hServiceStatus, rax
0x18002aaff  mov     edx, 2; unsigned int
0x18002ab04  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002ab09  mov     ebx, 1
0x18002ab0e  mov     rsi, cs:off_18028DDA0
0x18002ab15  mov     rax, cs:off_18028DDA8
0x18002ab1c  jmp     loc_18002ABA4
0x18002ab21  test    ebx, ebx
0x18002ab23  js      loc_18002ADE0
0x18002ab29  mov     rdi, [rsi]
0x18002ab2c  test    rdi, rdi
0x18002ab2f  jz      short loc_18002ABA0
0x18002ab31  mov     [rbp+57h+pUnk], 0
0x18002ab39  cmp     qword ptr [rdi+10h], 0
0x18002ab3e  jnz     short loc_18002AB44
0x18002ab40  xor     ebx, ebx
0x18002ab42  jmp     short loc_18002ABA0
0x18002ab44  lea     r8, [rbp+57h+pUnk]
0x18002ab48  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002ab4f  mov     rcx, [rdi+18h]
0x18002ab53  mov     rax, [rdi+10h]
0x18002ab57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab5c  mov     ebx, eax
0x18002ab5e  test    eax, eax
0x18002ab60  js      short loc_18002AB84
0x18002ab62  lea     rax, [rdi+28h]
0x18002ab66  mov     qword ptr [rsp+0A0h+lpdwRegister], rax; unsigned int
0x18002ab6b  mov     r9d, 5; flags
0x18002ab71  lea     r8d, [r9-1]; dwClsContext
0x18002ab75  mov     rdx, [rbp+57h+pUnk]; pUnk
0x18002ab79  mov     rcx, [rdi]; rclsid
0x18002ab7c  call    cs:__imp_CoRegisterClassObject
0x18002ab82  mov     ebx, eax
0x18002ab84  mov     rcx, [rbp+57h+pUnk]
0x18002ab88  test    rcx, rcx
0x18002ab8b  jz      short loc_18002AB99
0x18002ab8d  mov     rax, [rcx]
0x18002ab90  mov     rax, [rax+10h]
0x18002ab94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab99  mov     rax, cs:off_18028DDA8
0x18002aba0  add     rsi, 8
0x18002aba4  cmp     rsi, rax
0x18002aba7  jb      loc_18002AB21
0x18002abad  test    ebx, ebx
0x18002abaf  js      loc_18002ADE0
0x18002abb5  lea     rdx, aServiceRegiste; "Service registered class objects."
0x18002abbc  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002abc3  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002abc8  xor     ebx, ebx
0x18002abca  mov     dword ptr [rbp+57h+pUnk], ebx
0x18002abcd  xor     edx, edx; dwCoInit
0x18002abcf  xor     ecx, ecx; pvReserved
0x18002abd1  call    cs:__imp_CoInitializeEx
0x18002abd7  test    eax, eax
0x18002abd9  jns     short loc_18002ABE8
0x18002abdb  cmp     eax, 80010106h
0x18002abe0  jnz     loc_18002ADA8
0x18002abe6  jmp     short loc_18002ABF0
0x18002abe8  mov     ebx, 1
0x18002abed  mov     dword ptr [rbp+57h+pUnk], ebx
0x18002abf0  mov     edx, 2; unsigned int
0x18002abf5  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002abfa  xorps   xmm0, xmm0
0x18002abfd  movups  xmmword ptr [rbp+57h+lpFilename], xmm0
0x18002ac01  xorps   xmm1, xmm1
0x18002ac04  movdqu  [rbp+57h+var_38], xmm1
0x18002ac09  mov     r8d, 32h ; '2'
0x18002ac0f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002ac16  lea     rcx, [rbp+57h+lpFilename]
0x18002ac1a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ac1f  nop
0x18002ac20  lea     rcx, [rbp+57h+lpFilename]
0x18002ac24  call    ?Start@PrinterExtensionRegistrarService@Driver@Print@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Driver::PrinterExtensionRegistrarService::Start(std::wstring const &)
0x18002ac29  nop
0x18002ac2a  lea     rcx, [rbp+57h+lpFilename]
0x18002ac2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ac33  mov     edx, 2; unsigned int
0x18002ac38  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002ac3d  call    cs:__imp_CoResumeClassObjects
0x18002ac43  test    eax, eax
0x18002ac45  js      loc_18002AD8C
0x18002ac4b  mov     edx, 4; unsigned int
0x18002ac50  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002ac55  lea     rdx, aServiceIsRunni; "Service is running and waiting for term"...
0x18002ac5c  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002ac63  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002ac68  xor     r8d, r8d; lpTimerName
0x18002ac6b  xor     edx, edx; bManualReset
0x18002ac6d  xor     ecx, ecx; lpTimerAttributes
0x18002ac6f  call    cs:__imp_CreateWaitableTimerW
0x18002ac75  mov     rdi, rax
0x18002ac78  mov     [rbp+57h+var_50], rax
0x18002ac7c  mov     edx, 927C0h; void *
0x18002ac81  mov     r9d, edx; unsigned int
0x18002ac84  mov     r8d, 0EA60h; unsigned int
0x18002ac8a  mov     rcx, rax; this
0x18002ac8d  call    ?SetWaitableTimerEx@Synchronization@Win32Adapters@@YAXQEAXKKK@Z; Win32Adapters::Synchronization::SetWaitableTimerEx(void * const,ulong,ulong,ulong)
0x18002ac92  mov     rax, cs:?g_Server@@3VSharedService@Server@Print@@A; Print::Server::SharedService g_Server
0x18002ac99  mov     [rbp+57h+Handles], rax
0x18002ac9d  mov     [rbp+57h+var_60], rdi
0x18002aca1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002aca5  xor     r8d, r8d; bWaitAll
0x18002aca8  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18002acac  lea     ecx, [r8+2]; nCount
0x18002acb0  call    cs:__imp_WaitForMultipleObjects
0x18002acb6  cmp     cs:?m_locks@PrintNotifyLock@Driver@Print@@0KA, 0; ulong Print::Driver::PrintNotifyLock::m_locks
0x18002acbd  jz      short loc_18002ACCB
0x18002acbf  xor     sil, sil
0x18002acc2  dec     eax
0x18002acc4  cmp     eax, 0FFFFFFFDh
0x18002acc7  jbe     short loc_18002ACA1
0x18002acc9  jmp     short loc_18002ACCE
0x18002accb  mov     sil, 1
0x18002acce  mov     edx, 3; unsigned int
0x18002acd3  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002acd8  test    sil, sil
0x18002acdb  jz      short loc_18002ACE3
0x18002acdd  call    cs:__imp_CoSuspendClassObjects
0x18002ace3  mov     edx, 3; unsigned int
0x18002ace8  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002aced  xor     eax, eax
0x18002acef  mov     rsi, cs:off_18028DDA0
0x18002acf6  mov     rcx, cs:off_18028DDA8
0x18002acfd  jmp     short loc_18002AD24
0x18002acff  test    eax, eax
0x18002ad01  jnz     short loc_18002AD29
0x18002ad03  mov     rdx, [rsi]
0x18002ad06  test    rdx, rdx
0x18002ad09  jz      short loc_18002AD20
0x18002ad0b  cmp     [rdx+28h], eax
0x18002ad0e  jz      short loc_18002AD20
0x18002ad10  mov     ecx, [rdx+28h]; dwRegister
0x18002ad13  call    cs:__imp_CoRevokeClassObject
0x18002ad19  mov     rcx, cs:off_18028DDA8; this
0x18002ad20  add     rsi, 8
0x18002ad24  cmp     rsi, rcx
0x18002ad27  jb      short loc_18002ACFF
0x18002ad29  mov     edx, 3; unsigned int
0x18002ad2e  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002ad33  call    ?Stop@PrinterExtensionRegistrarService@Driver@Print@@SAXXZ; Print::Driver::PrinterExtensionRegistrarService::Stop(void)
0x18002ad38  mov     edx, 1; unsigned int
0x18002ad3d  call    ?UpdateStatus@SharedService@Server@Print@@QEAAXK@Z; Print::Server::SharedService::UpdateStatus(ulong)
0x18002ad42  lea     rdx, aServiceIsStopp; "Service is stopped."
0x18002ad49  lea     rcx, aPrintServerSha_5; "Print::Server::SharedService::Main"
0x18002ad50  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002ad55  nop
0x18002ad56  lea     rax, [rdi-1]
0x18002ad5a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ad5e  ja      short loc_18002AD6A
0x18002ad60  mov     rcx, rdi; hObject
0x18002ad63  call    cs:__imp_CloseHandle
0x18002ad69  nop
0x18002ad6a  test    ebx, ebx
0x18002ad6c  jz      short loc_18002AD74
0x18002ad6e  call    cs:__imp_CoUninitialize
0x18002ad74  mov     rcx, [rbp+57h+var_28]
0x18002ad78  xor     rcx, rsp; StackCookie
0x18002ad7b  call    __security_check_cookie
0x18002ad80  add     rsp, 88h
0x18002ad87  pop     rdi
0x18002ad88  pop     rsi
0x18002ad89  pop     rbx
0x18002ad8a  pop     rbp
0x18002ad8b  retn
0x18002ad8c  mov     edx, eax; int
0x18002ad8e  lea     rcx, [rbp+57h+lpFilename]; this
0x18002ad92  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002ad97  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002ad9e  lea     rcx, [rbp+57h+lpFilename]; pExceptionObject
0x18002ada2  call    _CxxThrowException_0
0x18002ada8  mov     edx, eax; int
0x18002adaa  lea     rcx, [rbp+57h+lpFilename]; this
0x18002adae  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002adb3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002adba  lea     rcx, [rbp+57h+lpFilename]; pExceptionObject
0x18002adbe  call    _CxxThrowException_0
0x18002adc4  call    ?_Xrange@?$vector@GV?$allocator@G@std@@@std@@CAXXZ; std::vector<ushort>::_Xrange(void)
0x18002adca  mov     rcx, [rbp+5Fh]; this
0x18002adce  lea     r8, aPrintscanPrint_18; "printscan\\print\\drivers\\usermode\\dr"...
0x18002add5  mov     edx, 19Fh; void *
0x18002adda  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002ade0  mov     edx, ebx; int
0x18002ade2  lea     rcx, [rbp+57h+lpFilename]; this
0x18002ade6  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18002adeb  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18002adf2  lea     rcx, [rbp+57h+lpFilename]; pExceptionObject
0x18002adf6  call    _CxxThrowException_0
```
