# TiMain(ulong,wchar_t * * const)

- ea: `0x140009650`
- end: `0x140009b23`
- name: `?TiMain@@YAXKQEAPEA_W@Z`
- size: `1235`
- prototype: `void __fastcall(unsigned int, wchar_t **const)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000b79c`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x140007b40`
- `0x140009334`
- `0x140009438`
- `0x140009650`
- `0x140009b2c`
- `0x14000bc20`
- `0x14000c3e0`
- `0x14000c830`
- `0x140017658`
- `0x140017ecc`
- `0x140018630`
- `0x1400198d4`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140009948`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140009948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000986e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000986e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009952`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000989e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140009aee`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000989e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140009aee`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400098ce`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400098ce`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140009928`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140009928`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009a60`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009a60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000999b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000999b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14000985c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14000985c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140009ae2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140009ae2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140009716`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140009716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000975f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400097cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000975f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400097cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000979e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000979e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140009a74`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140009a74`

## string_xrefs

- `0x1400096c5`: `TI: --- Initializing Trusted Installer ---`
- `0x1400096eb`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\TiRunning`
- `0x140009a66`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\TiRunning`
- `0x140009734`: `Unable to create TiRunning key.`
- `0x140009772`: `Unable to mark CbsTemp content for deletion.`
- `0x140009794`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\RebootInProgress`
- `0x1400097fa`: `TrustedInstaller terminated with pending operations.`
- `0x14000983d`: `TrustedInstaller`
- `0x14000988b`: `Failed to register Trusted Installer with service control manager, Trusted Installer service will shutdown now.`
- `0x1400098dd`: `Failed to initialize COM.`
- `0x140009934`: `Failed to initialize COM security.`
- `0x1400099a7`: `Failed to access COM GlobalOptions object`
- `0x1400099d0`: `Failed to set COM GlobalOptions, exception handling still in place.`
- `0x140009a04`: `Failed to set COM unmarshaling policy to strong`
- `0x140009a1b`: `Failed to initialize Trusted Installer.`
- `0x140009a8c`: `Unable to delete TiRunning key`

## pseudocode

```c
void __fastcall TiMain(unsigned int a1, wchar_t **const a2)
{
  int ServicingStackDirectory; // eax
  wchar_t *v5; // rsi
  int v6; // eax
  bool v7; // sf
  int v8; // eax
  int *v9; // rdx
  RebootMark *v10; // rcx
  int IsRebootPending; // eax
  signed int LastError; // eax
  UINT v13; // ebx
  __int64 v14; // rdx
  int v15; // eax
  HRESULT v16; // eax
  unsigned __int16 v17; // bx
  int v18; // edi
  HRESULT v19; // eax
  signed int v20; // eax
  bool v21; // sf
  HRESULT v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned __int64 v26; // rdx
  int v27; // eax
  bool v28; // sf
  wchar_t *v29; // [rsp+50h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  HKEY v32; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-10h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v32 = 0;
  ppv = 0;
  v29 = 0;
  ServicingStackDirectory = FindServicingStackDirectory(&v29);
  v5 = v29;
  if ( ServicingStackDirectory >= 0 )
    WdsLoad(v29, 0);
  LogAdapter::g_Logger = (struct LogAdapter::Logger *)&vWdsLogger;
  CBSWdsLogLight(0x4000000, 0, 0, "TI: --- Initializing Trusted Installer ---");
  LogBootTime();
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\TiRunning",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition);
  v7 = v6 < 0;
  if ( v6 )
  {
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = v6 < 0;
    }
    if ( v7 )
      CBSWdsLogLight(0x4000000, (unsigned int)v6, 1, "Unable to create TiRunning key.");
  }
  else if ( dwDisposition == 2 )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "TI: It looks like TI crashed or was interrupted last time it was started");
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v8 = MarkCbsTempContentForDeletion();
    if ( v8 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v8, 1, "Unable to mark CbsTemp content for deletion.");
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\RebootInProgress",
          0,
          1u,
          &v32) )
  {
    vbRebootInProgress = 1;
    CBSWdsLogLight(0x4000000, 0, 0, "TI: a client is starting TI after TI terminated due to a preshutdown notification");
    v10 = (RebootMark *)v32;
    if ( v32 )
    {
      RegCloseKey(v32);
      v32 = 0;
    }
  }
  IsRebootPending = RebootMark::IsRebootPending(v10, v9);
  if ( IsRebootPending < 0 )
    CBSWdsLogLight(
      0x4000000,
      (unsigned int)IsRebootPending,
      1,
      "Unable to query if reboot is pending, continuing anyway.");
  if ( vbRebootPending )
  {
    vbRequireReboot = 1;
    CBSWdsLogLight(0x4000000, 0, 0, "TrustedInstaller terminated with pending operations.");
  }
  if ( !vbStandalone )
  {
    *(_QWORD *)&vTiStatus.dwCurrentState = 2;
    *(_QWORD *)&vTiStatus.dwServiceSpecificExitCode = 0;
    vTiStatus.dwWaitHint = 0;
    vTiStatus.dwServiceType = 48;
    vTiStatus.dwWin32ExitCode = 0;
    vhTiService = RegisterServiceCtrlHandlerExW(L"TrustedInstaller", TiControlHandler, 0);
    if ( !vhTiService )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = (unsigned int)LastError;
      if ( (int)v14 < 0 )
        CBSWdsLogLight(
          0x4000000,
          v14,
          1,
          "Failed to register Trusted Installer with service control manager, Trusted Installer service will shutdown now.");
      ExitProcess(v13);
    }
  }
  if ( !vbRebootPending )
  {
    v15 = InitializeAnticipateShutdownProcessingNeeded();
    if ( v15 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v15, 1, "Unable to check for AnticipateShutdownProcessingNeeded");
  }
  v16 = CoInitializeEx(0, 0);
  v17 = v16;
  if ( v16 >= 0 )
  {
    v18 = 1;
    v19 = CoInitializeSecurity(0, -1, 0, 0, 5u, 2u, 0, 8u, 0);
    v17 = v19;
    if ( v19 >= 0 )
    {
      if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
      {
        v20 = GetLastError();
        v21 = v20 < 0;
        if ( v20 > 0 )
        {
          v20 = (unsigned __int16)v20 | 0x80070000;
          v21 = v20 < 0;
        }
        if ( v21 )
          CBSWdsLogLight(
            0x4000000,
            (unsigned int)v20,
            1,
            "Unable to enable termination on heap corruption, continuing anyway.");
      }
      v22 = CoCreateInstance(&CLSID_GlobalOptions, 0, 3u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
      v17 = v22;
      if ( v22 >= 0 )
      {
        v23 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
        if ( v23 < 0 )
          CBSWdsLogLight(
            0x4000000,
            (unsigned int)v23,
            1,
            "Failed to set COM GlobalOptions, exception handling still in place.");
        v24 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
        v17 = v24;
        if ( v24 >= 0 )
        {
          v25 = TiInitialize();
          v17 = v25;
          if ( v25 >= 0 )
            v17 = TiMainLoop(a1, a2);
          else
            CBSWdsLogLight(0x4000000, (unsigned int)v25, 1, "Failed to initialize Trusted Installer.");
        }
        else
        {
          CBSWdsLogLight(0x4000000, (unsigned int)v24, 1, "Failed to set COM unmarshaling policy to strong");
        }
      }
      else
      {
        CBSWdsLogLight(0x4000000, (unsigned int)v22, 1, "Failed to access COM GlobalOptions object");
      }
    }
    else
    {
      CBSWdsLogLight(0x4000000, (unsigned int)v19, 1, "Failed to initialize COM security.");
    }
  }
  else
  {
    v18 = 0;
    CBSWdsLogLight(0x4000000, (unsigned int)v16, 1, "Failed to initialize COM.");
  }
  TiFinalize();
  if ( v5 )
    operator delete(v5 - 4, v26);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v18 )
    CoUninitialize();
  v27 = RegDeleteKeyW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\TiRunning");
  v28 = v27 < 0;
  if ( v27 )
  {
    if ( v27 > 0 )
    {
      v27 = (unsigned __int16)v27 | 0x80070000;
      v28 = v27 < 0;
    }
    if ( v28 )
      CBSWdsLogLight(0x4000000, (unsigned int)v27, 1, "Unable to delete TiRunning key");
  }
  WdsUnload();
  if ( vhTiService )
  {
    vTiStatus.dwWin32ExitCode = v17;
    *(_QWORD *)&vTiStatus.dwCurrentState = 1;
    *(_QWORD *)&vTiStatus.dwServiceSpecificExitCode = 0;
    vTiStatus.dwWaitHint = 0;
    vTiStatus.dwServiceType = 48;
    if ( !SetServiceStatus(vhTiService, &vTiStatus) )
      ExitProcess(v17);
    vhTiService = 0;
  }
}

```

## disassembly

```asm
0x140009650  mov     [rsp-38h+arg_10], rbx
0x140009655  push    rbp
0x140009656  push    rsi
0x140009657  push    rdi
0x140009658  push    r12
0x14000965a  push    r13
0x14000965c  push    r14
0x14000965e  push    r15
0x140009660  mov     rbp, rsp
0x140009663  sub     rsp, 80h
0x14000966a  mov     rax, cs:__security_cookie
0x140009671  xor     rax, rsp
0x140009674  mov     [rbp+var_8], rax
0x140009678  xor     r12d, r12d
0x14000967b  mov     r14d, ecx
0x14000967e  lea     rcx, [rbp+var_30]
0x140009682  mov     [rbp+hKey], r12
0x140009686  mov     [rbp+dwDisposition], r12d
0x14000968a  mov     r15, rdx
0x14000968d  mov     [rbp+var_18], r12
0x140009691  mov     [rbp+ppv], r12
0x140009695  mov     [rbp+var_30], r12
0x140009699  call    FindServicingStackDirectory
0x14000969e  mov     rsi, [rbp+var_30]
0x1400096a2  test    eax, eax
0x1400096a4  js      short loc_1400096B0
0x1400096a6  xor     edx, edx; HINSTANCE
0x1400096a8  mov     rcx, rsi; wchar_t *
0x1400096ab  call    ?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z; WdsLoad(wchar_t const *,HINSTANCE__ *)
0x1400096b0  lea     rax, ?vWdsLogger@@3VWdsLogger@LogAdapter@@A; LogAdapter::WdsLogger vWdsLogger
0x1400096b7  mov     edi, 4000000h
0x1400096bc  mov     ecx, edi
0x1400096be  mov     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rax; LogAdapter::Logger * LogAdapter::g_Logger
0x1400096c5  lea     r9, aTiInitializing; "TI: --- Initializing Trusted Installer "...
0x1400096cc  xor     r8d, r8d
0x1400096cf  xor     edx, edx
0x1400096d1  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400096d6  call    ?LogBootTime@@YAXXZ; LogBootTime(void)
0x1400096db  lea     rax, [rbp+dwDisposition]
0x1400096df  mov     rbx, 0FFFFFFFF80000002h
0x1400096e6  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x1400096eb  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400096f2  lea     rax, [rbp+hKey]
0x1400096f6  xor     r9d, r9d; lpClass
0x1400096f9  mov     [rsp+80h+phkResult], rax; phkResult
0x1400096fe  xor     r8d, r8d; Reserved
0x140009701  mov     [rsp+80h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140009706  mov     rcx, rbx; hKey
0x140009709  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x140009711  mov     [rsp+80h+dwOptions], r12d; dwOptions
0x140009716  call    cs:__imp_RegCreateKeyExW
0x14000971c  mov     r13d, 1
0x140009722  test    eax, eax
0x140009724  jz      short loc_14000973D
0x140009726  jle     short loc_140009732
0x140009728  movzx   eax, ax
0x14000972b  or      eax, 80070000h
0x140009730  test    eax, eax
0x140009732  jns     short loc_140009785
0x140009734  lea     r9, aUnableToCreate_0; "Unable to create TiRunning key."
0x14000973b  jmp     short loc_140009779
0x14000973d  cmp     [rbp+dwDisposition], 2
0x140009741  jnz     short loc_140009785
0x140009743  lea     r9, aTiItLooksLikeT_0; "TI: It looks like TI crashed or was int"...
0x14000974a  xor     r8d, r8d
0x14000974d  xor     edx, edx
0x14000974f  mov     ecx, edi
0x140009751  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009756  mov     rcx, [rbp+hKey]; hKey
0x14000975a  test    rcx, rcx
0x14000975d  jz      short loc_140009769
0x14000975f  call    cs:__imp_RegCloseKey
0x140009765  mov     [rbp+hKey], r12
0x140009769  call    ?MarkCbsTempContentForDeletion@@YAJXZ; MarkCbsTempContentForDeletion(void)
0x14000976e  test    eax, eax
0x140009770  jns     short loc_140009785
0x140009772  lea     r9, aUnableToMarkCb; "Unable to mark CbsTemp content for dele"...
0x140009779  mov     r8d, r13d
0x14000977c  mov     edx, eax
0x14000977e  mov     ecx, edi
0x140009780  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009785  lea     rax, [rbp+var_18]
0x140009789  mov     r9d, r13d; samDesired
0x14000978c  xor     r8d, r8d; ulOptions
0x14000978f  mov     qword ptr [rsp+80h+dwOptions], rax; phkResult
0x140009794  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000979b  mov     rcx, rbx; hKey
0x14000979e  call    cs:__imp_RegOpenKeyExW
0x1400097a4  test    eax, eax
0x1400097a6  jnz     short loc_1400097D5
0x1400097a8  lea     r9, aTiAClientIsSta; "TI: a client is starting TI after TI te"...
0x1400097af  mov     cs:?vbRebootInProgress@@3HA, r13d; int vbRebootInProgress
0x1400097b6  xor     r8d, r8d
0x1400097b9  xor     edx, edx
0x1400097bb  mov     ecx, edi
0x1400097bd  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400097c2  mov     rcx, [rbp+var_18]; hKey
0x1400097c6  test    rcx, rcx
0x1400097c9  jz      short loc_1400097D5
0x1400097cb  call    cs:__imp_RegCloseKey
0x1400097d1  mov     [rbp+var_18], r12
0x1400097d5  call    ?IsRebootPending@RebootMark@@QEAAJPEAH@Z; RebootMark::IsRebootPending(int *)
0x1400097da  test    eax, eax
0x1400097dc  jns     short loc_1400097F1
0x1400097de  lea     r9, aUnableToQueryI; "Unable to query if reboot is pending, c"...
0x1400097e5  mov     r8d, r13d
0x1400097e8  mov     edx, eax
0x1400097ea  mov     ecx, edi
0x1400097ec  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400097f1  cmp     cs:?vbRebootPending@@3HA, r12d; int vbRebootPending
0x1400097f8  jz      short loc_140009814
0x1400097fa  lea     r9, aTrustedinstall_3; "TrustedInstaller terminated with pendin"...
0x140009801  mov     cs:?vbRequireReboot@@3HA, r13d; int vbRequireReboot
0x140009808  xor     r8d, r8d
0x14000980b  xor     edx, edx
0x14000980d  mov     ecx, edi
0x14000980f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009814  cmp     cs:?vbStandalone@@3HA, r12d; int vbStandalone
0x14000981b  jnz     loc_1400098A5
0x140009821  xor     r8d, r8d; lpContext
0x140009824  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS vTiStatus ...
0x14000982f  lea     rdx, ?TiControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x140009836  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, r12; _SERVICE_STATUS vTiStatus ...
0x14000983d  lea     rcx, ServiceName; "TrustedInstaller"
0x140009844  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, r12d; _SERVICE_STATUS vTiStatus ...
0x14000984b  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 30h ; '0'; _SERVICE_STATUS vTiStatus ...
0x140009855  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r12d; _SERVICE_STATUS vTiStatus ...
0x14000985c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140009862  mov     cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * vhTiService
0x140009869  test    rax, rax
0x14000986c  jnz     short loc_1400098A5
0x14000986e  call    cs:__imp_GetLastError
0x140009874  mov     ebx, eax
0x140009876  test    eax, eax
0x140009878  jg      short loc_14000987E
0x14000987a  mov     edx, eax
0x14000987c  jmp     short loc_140009887
0x14000987e  movzx   edx, bx
0x140009881  or      edx, 80070000h
0x140009887  test    edx, edx
0x140009889  jns     short loc_14000989C
0x14000988b  lea     r9, aFailedToRegist_0; "Failed to register Trusted Installer wi"...
0x140009892  mov     r8d, r13d
0x140009895  mov     ecx, edi
0x140009897  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000989c  mov     ecx, ebx; uExitCode
0x14000989e  call    cs:__imp_ExitProcess
0x1400098a5  cmp     cs:?vbRebootPending@@3HA, r12d; int vbRebootPending
0x1400098ac  jnz     short loc_1400098CA
0x1400098ae  call    InitializeAnticipateShutdownProcessingNeeded
0x1400098b3  test    eax, eax
0x1400098b5  jns     short loc_1400098CA
0x1400098b7  lea     r9, aUnableToCheckF; "Unable to check for AnticipateShutdownP"...
0x1400098be  mov     r8d, r13d
0x1400098c1  mov     edx, eax
0x1400098c3  mov     ecx, edi
0x1400098c5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400098ca  xor     edx, edx; dwCoInit
0x1400098cc  xor     ecx, ecx; pvReserved
0x1400098ce  call    cs:__imp_CoInitializeEx
0x1400098d4  mov     ebx, eax
0x1400098d6  test    eax, eax
0x1400098d8  jns     short loc_1400098F8
0x1400098da  mov     edi, r12d
0x1400098dd  lea     r9, aFailedToInitia; "Failed to initialize COM."
0x1400098e4  mov     r8d, r13d
0x1400098e7  mov     edx, eax
0x1400098e9  mov     ecx, 4000000h
0x1400098ee  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400098f3  jmp     loc_140009A34
0x1400098f8  mov     [rsp+80h+lpdwDisposition], r12; pReserved3
0x1400098fd  xor     r9d, r9d; pReserved1
0x140009900  mov     dword ptr [rsp+80h+phkResult], 8; dwCapabilities
0x140009908  xor     r8d, r8d; asAuthSvc
0x14000990b  mov     [rsp+80h+lpSecurityAttributes], r12; pAuthList
0x140009910  or      edx, 0FFFFFFFFh; cAuthSvc
0x140009913  mov     [rsp+80h+samDesired], 2; dwImpLevel
0x14000991b  xor     ecx, ecx; pSecDesc
0x14000991d  mov     [rsp+80h+dwOptions], 5; dwAuthnLevel
0x140009925  mov     edi, r13d
0x140009928  call    cs:__imp_CoInitializeSecurity
0x14000992e  mov     ebx, eax
0x140009930  test    eax, eax
0x140009932  jns     short loc_14000993D
0x140009934  lea     r9, aFailedToInitia_4; "Failed to initialize COM security."
0x14000993b  jmp     short loc_1400098E4
0x14000993d  xor     r9d, r9d; HeapInformationLength
0x140009940  xor     r8d, r8d; HeapInformation
0x140009943  mov     edx, r13d; HeapInformationClass
0x140009946  xor     ecx, ecx; HeapHandle
0x140009948  call    cs:__imp_HeapSetInformation
0x14000994e  test    eax, eax
0x140009950  jnz     short loc_14000997E
0x140009952  call    cs:__imp_GetLastError
0x140009958  test    eax, eax
0x14000995a  jle     short loc_140009966
0x14000995c  movzx   eax, ax
0x14000995f  or      eax, 80070000h
0x140009964  test    eax, eax
0x140009966  jns     short loc_14000997E
0x140009968  lea     r9, aUnableToEnable; "Unable to enable termination on heap co"...
0x14000996f  mov     r8d, r13d
0x140009972  mov     edx, eax
0x140009974  mov     ecx, 4000000h
0x140009979  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000997e  xor     edx, edx; pUnkOuter
0x140009980  lea     rax, [rbp+ppv]
0x140009984  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000998b  mov     qword ptr [rsp+80h+dwOptions], rax; ppv
0x140009990  lea     rcx, CLSID_GlobalOptions; rclsid
0x140009997  lea     r8d, [rdx+3]; dwClsContext
0x14000999b  call    cs:__imp_CoCreateInstance
0x1400099a1  mov     ebx, eax
0x1400099a3  test    eax, eax
0x1400099a5  jns     short loc_1400099B3
0x1400099a7  lea     r9, aFailedToAccess; "Failed to access COM GlobalOptions obje"...
0x1400099ae  jmp     loc_1400098E4
0x1400099b3  mov     rcx, [rbp+ppv]
0x1400099b7  mov     r8d, 2
0x1400099bd  mov     edx, r13d
0x1400099c0  mov     rax, [rcx]
0x1400099c3  mov     rax, [rax+18h]
0x1400099c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099cc  test    eax, eax
0x1400099ce  jns     short loc_1400099E6
0x1400099d0  lea     r9, aFailedToSetCom; "Failed to set COM GlobalOptions, except"...
0x1400099d7  mov     r8d, r13d
0x1400099da  mov     edx, eax
0x1400099dc  mov     ecx, 4000000h
0x1400099e1  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400099e6  mov     rcx, [rbp+ppv]
0x1400099ea  mov     r8, r13
0x1400099ed  mov     edx, 5
0x1400099f2  mov     rax, [rcx]
0x1400099f5  mov     rax, [rax+18h]
0x1400099f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099fe  mov     ebx, eax
0x140009a00  test    eax, eax
0x140009a02  jns     short loc_140009A10
0x140009a04  lea     r9, aFailedToSetCom_0; "Failed to set COM unmarshaling policy t"...
0x140009a0b  jmp     loc_1400098E4
0x140009a10  call    TiInitialize
0x140009a15  mov     ebx, eax
0x140009a17  test    eax, eax
0x140009a19  jns     short loc_140009A27
0x140009a1b  lea     r9, aFailedToInitia_9; "Failed to initialize Trusted Installer."
0x140009a22  jmp     loc_1400098E4
0x140009a27  mov     rdx, r15
0x140009a2a  mov     ecx, r14d
0x140009a2d  call    TiMainLoop
0x140009a32  mov     ebx, eax
0x140009a34  call    TiFinalize
0x140009a39  test    rsi, rsi
0x140009a3c  jz      short loc_140009A47
0x140009a3e  lea     rcx, [rsi-8]; void *
0x140009a42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009a47  mov     rcx, [rbp+ppv]
0x140009a4b  test    rcx, rcx
0x140009a4e  jz      short loc_140009A5C
0x140009a50  mov     rax, [rcx]
0x140009a53  mov     rax, [rax+10h]
0x140009a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a5c  test    edi, edi
0x140009a5e  jz      short loc_140009A66
0x140009a60  call    cs:__imp_CoUninitialize
0x140009a66  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140009a6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009a74  call    cs:__imp_RegDeleteKeyW
0x140009a7a  test    eax, eax
0x140009a7c  jz      short loc_140009AA2
0x140009a7e  jle     short loc_140009A8A
0x140009a80  movzx   eax, ax
0x140009a83  or      eax, 80070000h
0x140009a88  test    eax, eax
0x140009a8a  jns     short loc_140009AA2
0x140009a8c  lea     r9, aUnableToDelete; "Unable to delete TiRunning key"
0x140009a93  mov     r8d, r13d
0x140009a96  mov     edx, eax
0x140009a98  mov     ecx, 4000000h
0x140009a9d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009aa2  call    ?WdsUnload@@YAXXZ; WdsUnload(void)
0x140009aa7  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x140009aae  test    rcx, rcx
0x140009ab1  jz      short loc_140009AFC
0x140009ab3  movzx   ebx, bx
0x140009ab6  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x140009abd  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS vTiStatus ...
0x140009ac3  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, r13; _SERVICE_STATUS vTiStatus ...
0x140009aca  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, r12; _SERVICE_STATUS vTiStatus ...
0x140009ad1  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, r12d; _SERVICE_STATUS vTiStatus ...
0x140009ad8  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 30h ; '0'; _SERVICE_STATUS vTiStatus ...
0x140009ae2  call    cs:__imp_SetServiceStatus
0x140009ae8  test    eax, eax
0x140009aea  jnz     short loc_140009AF5
0x140009aec  mov     ecx, ebx; uExitCode
0x140009aee  call    cs:__imp_ExitProcess
0x140009af5  mov     cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, r12; SERVICE_STATUS_HANDLE__ * vhTiService
0x140009afc  mov     rcx, [rbp+var_8]
0x140009b00  xor     rcx, rsp; StackCookie
0x140009b03  call    __security_check_cookie
  ... truncated ...
```
